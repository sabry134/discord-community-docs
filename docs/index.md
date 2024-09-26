# Installation

## Requirements

- **Node.js Version**: You must use Node.js version 18 or higher. To install and switch to Node.js v18, use the following commands:
<!-- termynal -->

```
> nvm install 18
v18.20.4 is already installed.
Now using node v18.20.4 (npm v10.8.3)
> nvm use 18
Now using node v18.20.4 (npm v10.8.3)
```
<br>
- **Github SSH KEY**: It is not mandatory, but in this guide, the repository clone will be done using the SSH key method.

<!-- termynal -->

```
> git clone git@github.com:sabry134/Discord-Community-Dashboard.git
Cloning into 'Discord-Community-Dashboard'...
remote: Enumerating objects: 573, done.
remote: Counting objects: 100% (54/54), done.
remote: Compressing objects: 100% (45/45), done.
remote: Total 573 (delta 36), reused 20 (delta 8), pack-reused 519 (from 1)
Receiving objects: 100% (573/573), 142.76 MiB | 7.00 MiB/s, done.
Resolving deltas: 100% (106/106), done.
```

## Getting Started

### With Docker

To start the application using Docker, run:

```bash
./start.sh
```

To stop the Docker, please run:

```bash
./stop.sh
```


### Without Docker

To start the application without Docker, open a terminal and run:

<!-- termynal -->

```
> cd discord_community_front && ./start_no_docker.sh
Compiled successfully!

You can now view discord-community-dashboard in the browser.

  Local:            http://localhost:8080/discord-community-dashboard
  On Your Network:  http://[NETWORK IP]:8080/discord-community-dashboard

Note that the development build is not optimized.
To create a production build, use npm run build.

webpack compiled successfully
```


In another terminal, start the backend server:

<!-- termynal -->

```
> cd discord_community_server && node server.js
(node:173369) [MONGODB DRIVER] Warning: useNewUrlParser is a deprecated option: useNewUrlParser has no effect since Node.js Driver version 4.0.0 and will be removed in the next major version
(Use `node --trace-warnings ...` to show where the warning was created)
(node:173369) [MONGODB DRIVER] Warning: useUnifiedTopology is a deprecated option: useUnifiedTopology has no effect since Node.js Driver version 4.0.0 and will be removed in the next major version
Server is listening on port 8081
MongoDB connected successfully
AllowedAccess with ID: 495265351270137883 already exists
AdminWhitelist with ID: 495265351270137883 already exists
```

<br>
## Environment Variables

You need to create a .env file in the discord_community_server directory to configure your application. The following variables must be included in your .env file:

```env
MONGODB_URI=
DISCORD_CLIENT_ID=
DISCORD_CLIENT_SECRET=
DISCORD_BOT_TOKEN=
DEFAULT_ID=
ADMIN_DEFAULT_ID=
GUILD_ID=
DISCORD_EVERYONE_ROLE_ID=
COOKIE_SECRET=
DISCORD_REDIRECT_URI=http://localhost:8081/discord-oauth-callback
```


Make sure to fill in the values appropriately. Do not share sensitive information publicly.

<br>
## Discord setup

Besides oauth which will be explained later. Here's how you can get a few .env data.


COOKIE_SECRET:

<!-- termynal -->

```
> node
Welcome to Node.js v18.20.4.
Type ".help" for more information.
> crypto.randomUUID()
'YOUR_CRYPTO_SECRET'
```


**DEFAULT_ID & ADMIN_DEFAULT_ID:** Your discord ID
<br>
**GUILD_ID:** Your server ID
<br>
**DISCORD_EVERYONE_ROLE_ID:** The ID for the @everyone role (same as your Guild ID)

<br>
## Discord Oauth setup

### Overview

To integrate Discord OAuth into your application, follow these steps to create an application in the Discord Developer Portal and obtain your credentials.

#### Step 1: Create a Discord Application

1. **Go to the Discord Developer Portal**: Visit [Discord Developer Portal](https://discord.com/developers/applications).
2. **Log In**: Sign in with your Discord account.
3. **Create a New Application**:
   - Click on the "New Application" button.
   - Enter a name for your application and click "Create".

#### Step 2: Set Up OAuth2

1. **Navigate to the OAuth2 Tab**:
   - Select your application from the list.
   - Click on the "OAuth2" tab in the left sidebar.
   
2. **Configure OAuth2 Settings**:
   - **Redirects**: Under "Redirects," add your redirect URI. This should be your backend endpoint that handles the OAuth callback (e.g., `http://localhost:8081/discord-oauth-callback`).
   - **Scopes**: Select the scopes your application requires. For basic user authentication, select:
     - `identify`
     - `join`
   - **Bot**: If your application requires bot functionality, you can also generate a bot token under the "Bot" tab.

3. **Generate the OAuth2 URL**:
   - Scroll down to "OAuth2 URL Generator."
   - Select the scopes you configured earlier.
   - Copy the generated URL.

#### Step 3: Set Up Your `.env` File

Add the following lines to your `.env` file in the `discord_community_server` directory, filling in the placeholders with your application's values:

```env
DISCORD_CLIENT_ID=your_client_id
DISCORD_CLIENT_SECRET=your_client_secret
DISCORD_REDIRECT_URI=http://localhost:8081/discord-oauth-callback
```
<br>
## MongoDB Database Setup

To set up a MongoDB database, follow these steps:

- Create an Account on MongoDB Atlas: Go to MongoDB Atlas and sign up for an account.
- Create a New Cluster: After logging in, click on "Build a Cluster" and follow the prompts to create a new cluster.
- Connect to Your Cluster: Once your cluster is created, click on "Connect" and follow the instructions to add your IP address and create a database user.
- Get the Connection String: After setting up your user, you will be provided with a connection string. Replace the placeholder username and password in the string with your MongoDB user credentials.
<br>
