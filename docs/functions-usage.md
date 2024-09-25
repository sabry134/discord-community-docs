## Project Build Package Documentation

The **Project Build Package** is a npm package designed to facilitate interactions with a project management API. It provides functions to perform various actions such as creating, retrieving, updating, and deleting projects.

### Installation

To install the package, use the following npm command:

```bash
npm install project_build_package
```

### Functions

#### `request(bearerToken, requestBody)`

This function creates a new project by sending a POST request to the `/new-request` endpoint of the project management API.

- **Parameters**:
  - `bearerToken`: The authentication token required to access the API.
  - `requestBody`: An object containing the details of the project to be created, including `githubLink`, `projectRequirement`, and `projectLanguage`.

- **Returns**: A Promise that resolves to the response data from the API if the request is successful, or rejects with an error if the request fails.

#### `mykeys(bearerToken, email)`

This function retrieves all projects associated with a specific user by sending a GET request to the `/find-projects/:email` endpoint of the project management API.

- **Parameters**:
  - `bearerToken`: The authentication token required to access the API.
  - `email`: The email address of the user whose projects are to be retrieved.

- **Returns**: A Promise that resolves to an array of project keys associated with the specified user if the request is successful, or rejects with an error if the request fails.

#### `projectInfo(bearerToken, projectKey)`

This function retrieves detailed information about a specific project by sending a GET request to the `/project-info/:projectKey` endpoint of the project management API.

- **Parameters**:
  - `bearerToken`: The authentication token required to access the API.
  - `projectKey`: The unique key of the project whose information is to be retrieved.

- **Returns**: A Promise that resolves to an object containing detailed information about the specified project if the request is successful, or rejects with an error if the request fails.

#### `deleteOneProject(bearerToken, projects)`

This function deletes one or more projects by sending a POST request to the `/drop-project` endpoint of the project management API.

- **Parameters**:
  - `bearerToken`: The authentication token required to access the API.
  - `projects`: An array of project keys to be deleted.

- **Returns**: A Promise that resolves to a success message if the deletion is successful, or rejects with an error if the request fails.

#### `deleteAllProjects(bearerToken, email)`

This function deletes all projects associated with a specific user by sending a DELETE request to the `/drop/:email` endpoint of the project management API.

- **Parameters**:
  - `bearerToken`: The authentication token required to access the API.
  - `email`: The email address of the user whose projects are to be deleted.

- **Returns**: A Promise that resolves to a success message if the deletion is successful, or rejects with an error if the request fails.

### Example Usage

```javascript
const projectRequestsBuilder = require("project_build_package");
require("dotenv").config();

const bearerToken = process.env.BEARER_TOKEN;
const email = process.env.EMAIL;
const projectsToDelete = ["proj-1fed99a712a16813"];
const projectKey = process.env.PROJECT_KEY;
const requestBody = {
  githubLink: "https://github.com/example/example-project",
  projectRequirement: "Description of project requirements",
  projectLanguage: "JavaScript",
};

// Create a new project
projectRequestsBuilder
  .request(bearerToken, requestBody)
  .then((response) => {
    console.log("Project request successful:", response);
  })
  .catch((error) => {
    console.error("Project request failed:", error.message);
  });

// Retrieve all projects associated with a user
projectRequestsBuilder
  .mykeys(bearerToken, email)
  .then((response) => {
    console.log("Projects retrieved successfully:", response);
  })
  .catch((error) => {
    console.error("Error retrieving projects:", error.message);
  });

// Retrieve detailed information about a specific project
projectRequestsBuilder
  .projectInfo(bearerToken, projectKey)
  .then((response) => {
    console.log("Project info retrieved successfully:", response);
  })
  .catch((error) => {
    console.error("Error retrieving project info:", error.message);
  });

// Delete one or more projects
projectRequestsBuilder
  .deleteOneProject(bearerToken, projectsToDelete)
  .then((response) => {
    console.log("Project(s) deleted successfully:", response);
  })
  .catch((error) => {
    console.error("Error deleting project(s):", error.message);
  });

// Delete all projects associated with a user
projectRequestsBuilder
  .deleteAllProjects(bearerToken, email)
  .then((response) => {
    console.log("All projects deleted successfully:", response);
  })
  .catch((error) => {
    console.error("Error deleting all projects:", error.message);
  });
```


## Note

Replace process.env.BEARER_TOKEN, process.env.EMAIL, and process.env.PROJECT_KEY with actual values corresponding to your environment. Make sure to set up environment variables for these values before running the example.