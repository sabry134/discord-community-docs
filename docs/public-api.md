# Project Management API Documentation

This documentation provides an overview of the public endpoints available in the Project Management API. These endpoints allow for creating, retrieving, and managing projects.

## Base URL

The base URL for accessing the API is:

```json
https://website-requests-api.onrender.com
```


## Endpoints

### 1. Create a New Project Request

**Endpoint**: `/new-request`

**Method**: `POST`

**Description**: Creates a new project request.

**Headers**:
- `Authorization`: Bearer token required for authentication.

**Request Body**:

```json
{
  "githubLink": "https://github.com/example/example-project",
  "projectRequirement": "Description of project requirements",
  "projectLanguage": "JavaScript"
}
```

## Responses:

- 200 OK: Request sent successfully.
- 400 Bad Request: Missing or invalid request body or authentication key.
- 404 Not Found: Authentication key not found.
- 500 Internal Server Error: Error processing public request.

### 2. Get Project Information

**Endpoint:** `/project-info/:projectKey`

**Method:** `GET`

**Description:** Retrieves detailed information about a specific project.

**Headers:**

`Authorization`: Bearer token required for authentication.

**Parameters:**

`projectKey`: The unique key of the project to retrieve information for.

## Responses:

- 200 OK: Returns detailed project information.
- 400 Bad Request: Missing authorization header.
- 403 Forbidden: Project key does not belong to the authenticated user.
- 404 Not Found: Invalid authentication token or project key not found.
- 500 Internal Server Error: Error retrieving project info.


## Responses:

- 200 OK: Returns the email associated with the project key.
- 404 Not Found: Project key not found.
- 500 Internal Server Error: Error finding email.

### 3. Find Projects by Email

**Endpoint:** `/find-projects/:email`

**Method:** `GET`

**Description:** Retrieves all projects associated with a specific email.

**Headers:**

`Authorization`: Bearer token required for authentication.

**Parameters:**

`email`: The email address of the user whose projects are to be retrieved.

## Responses:

- 200 OK: Returns an array of project keys associated with the specified email.
- 400 Bad Request: Missing authorization header.
- 403 Forbidden: Authorization token does not match the provided email.
- 404 Not Found: Invalid authentication token or email not found.
- 500 Internal Server Error: Error finding projects.

### 4. Delete All Projects by Email

**Endpoint:** `/drop/:email`

**Method:** `DELETE`

**Description:** Deletes all projects associated with a specific email.

**Headers:**

`Authorization`: Bearer token required for authentication.

**Parameters:**

`email`: The email address of the user whose projects are to be deleted.

## Responses:

- 200 OK: All keys associated with the email have been deleted.
- 400 Bad Request: Missing authorization header.
- 403 Forbidden: Token does not match the provided email.
- 404 Not Found: No keys found for the provided email.
- 500 Internal Server Error: Error deleting keys by email.

### 5. Delete Specific Projects
**Endpoint:** `/drop-project`

**Method:** `POST`

**Description:** Deletes one or more specified projects.

**Headers:**

`Authorization`: Bearer token required for authentication.

**Request Body:**

```json
{
  "projects": ["proj-1fed99a712a16813"]
}
```

## Responses:

- 200 OK: Specified projects have been deleted.
- 400 Bad Request: Missing or invalid request body or authentication key.
- 403 Forbidden: Project does not belong to the authenticated user.
- 404 Not Found: No matching projects found for the provided email.
- 500 Internal Server Error: Error deleting projects.

### 6. Root Route

**Endpoint:** `/`

**Method:** `GET`

**Description:** A simple root route to verify that the server is running.

## Responses:

- 200 OK: Welcome to the root route!


## Rate Limiting
The API is rate-limited to 150 requests per minute per IP address. If the limit is exceeded, the following response will be returned:

**Response:**

429 Too Many Requests: Too many requests from this IP, please try again later.


## Error Handling

In case of errors, the API returns appropriate HTTP status codes along with error messages to indicate the nature of the error.

## Notes

- Ensure that the Authorization header is included where required.
- Replace localhost:3000 with the actual base URL of your deployed API.
- This concludes the public API documentation. For private routes, additional authentication and validation mechanisms are required.