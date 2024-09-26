
# API Documentation

## Table of Contents
- [API Documentation](#api-documentation)
  - [Table of Contents](#table-of-contents)
  - [API Management](#api-management)
  - [Scopes](#scopes)
  - [API Endpoints method](#api-endpoints-method)
  - [API Endpoints](#api-endpoints)
    - [/user/hello](#userhello)
    - [/users/new-announcement](#usersnew-announcement)
    - [/users/staff-list](#usersstaff-list)
    - [/users/community-rules](#userscommunity-rules)
    - [/users/staff-list](#usersstaff-list-1)
    - [/users/community-rules](#userscommunity-rules-1)
    - [/users/new-position](#usersnew-position)
    - [/users/delete-position/:position\_name](#usersdelete-positionposition_name)
    - [/users/shop-setup](#usersshop-setup)
    - [/users/points/:userId](#userspointsuserid)
    - [/users/add-points](#usersadd-points)
    - [/users/remove-points](#usersremove-points)
    - [/users/shop-setup](#usersshop-setup-1)
    - [/users/buy-role](#usersbuy-role)
    - [/users/is-running](#usersis-running)
    - [/users/start-bot](#usersstart-bot)
    - [/users/stop-bot](#usersstop-bot)
    - [/users/disable-command/:commandName](#usersdisable-commandcommandname)
    - [/users/enable-command/:commandName](#usersenable-commandcommandname)
    - [/users/logs](#userslogs)
    - [/users/warn-user](#userswarn-user)
    - [/users/mute-user](#usersmute-user)
    - [/users/kick-user](#userskick-user)
    - [/users/unmute-user](#usersunmute-user)
    - [/users/discord-ban-user](#usersdiscord-ban-user)
    - [/users/discord-unban-user](#usersdiscord-unban-user)

## API Management

On your API settings page, you can enable or disable your API along with editing your scopes.
<br><br>
![image](https://cdn.discordapp.com/attachments/1023567577831718963/1288673294148567070/image.png?ex=66f60a07&is=66f4b887&hm=614ba2b1686acf0cef4ed348143a12bb017d0c0360d11104d9613a1a5ed13024&)

!!! warning 
	A token is also necessary to use the public endpoint, otherwise you will receive an error.

## Scopes

???+ tldr "API Scopes usage"

	| Scope name | Usage | Manual |
	| :--- | :--- | :--- |
	| api.admin | When enabled, this scope will whitelist all admin permission endpoints | ✅ |
	| api.moderate | When enabled, this scope will whitelist all the moderation permission endpoints | ✅ |
	| api.community | When enabled, this scope will whitelist all the permission endpoints for the "Community" page | ✅ |
	| api.position | When enabled, this scope will whitelist all the position permission endpoints | ✅ |
	| api.roleShop | When enabled, this scope will whitelist all the shop permission endpoints | ✅ |
	| api.maintain | When enabled, this scope will whitelist all the bot management permission endpoints | ✅ |


Each of the public endpoints require specific scopes, the list can be found below

???+ tldr "Scopes needed for endpoints"

	| Endpoint | api.admin | api.moderate | api.community | api.position | api.roleShop | api.maintain |
	| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
	| /users/hello | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ 
	| /users/new-announcement | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ 
    | /users/staff-list (POST) | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ 
    | /users/community-rules (POST) | ✅ | ❌ | ❌ | ❌ | ❌ | ❌
    | /users/logs | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ 
    | /users/warn-user | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ 
    | /users/mute-user | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ 
    | /users/unmute-user | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ 
    | /users/kick-user | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ 
    | /users/discord-ban-user | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ 
    | /users/discord-unban-user | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ 
    | /users/new-post | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ 
    | /users/staff-list (GET) | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ 
    | /users/community-rules (GET) | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ 
    | /users/new-position | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ 
    | /users/delete-position | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ 
    | /users/shop-setup | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ 
    | /users/points/{userId} | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ 
    | /users/add-points | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ 
    | /users/remove-points | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ 
    | /users/buy-role | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ 
    | /users/is-running | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ 
    | /users/start-bot | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ 
    | /users/stop-bot | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ 
    | /users/disable-command/{commandName} | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ 
    | /users/enable-command/{commandName} | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ 


## API Endpoints method

???+ tldr "Scopes needed for endpoints"


	| Public Endpoint | GET | POST | PUT | DELETE
	| :--- | :--- | :--- | :--- | :--- |
	| /users/hello | ✅ | ❌ | ❌ | ❌ |
	| /users/new-announcement | ✅ | ❌ | ❌ | ❌ |
    | /users/staff-list | ✅ | ✅ | ❌ | ❌ |
    | /users/community-rules | ✅ | ✅ | ❌ | ❌ |
    | /users/logs | ✅ | ❌ | ❌ | ❌ |
    | /users/warn-user | ❌ | ✅ | ❌ | ❌ |
    | /users/mute-user | ❌ | ✅ | ❌ | ❌ |
    | /users/unmute-user | ❌ | ✅ | ❌ | ❌ |
    | /users/kick-user | ❌ | ✅ | ❌ | ❌ |
    | /users/discord-ban-user | ✅ | ❌ | ❌ | ❌ |
    | /users/discord-unban-user | ✅ | ❌ | ❌ | ❌ |
    | /users/new-position | ❌ | ✅ | ❌ | ❌ |
    | /users/delete-position | ❌ | ❌ | ❌ | ✅ |
    | /users/shop-setup | ✅ | ✅ | ❌ | ✅ |
    | /users/points/{userId} | ✅ | ❌ | ❌ | ❌ |
    | /users/add-points | ❌ | ✅ | ❌ | ❌ |
    | /users/remove-points | ❌ | ✅ | ❌ |
    | /users/buy-role | ❌ | ✅ | ❌ | ❌ |
    | /users/is-running | ✅ | ❌ | ❌ | ❌ |
    | /users/start-bot | ✅ | ❌ | ❌ | ❌ |
    | /users/stop-bot | ✅ | ❌ | ❌ | ❌ |
    | /users/disable-command/{commandName} | ❌ | ✅ | ❌ | ❌ |
    | /users/enable-command/{commandName} | ❌ | ✅ | ❌ | ❌ |


## API Endpoints


### /user/hello
- **Method:** GET
- **Description:** Returns a greeting message.
- **Response:**
  - `200 OK`: 'Hello world'

---

### /users/new-announcement
- **Method:** POST
- **Description:** Creates a new announcement.
- **Payload:** { title, content, image }
- **Response:**
  - `201 Created`: { message: 'Announcement created successfully', announcement: { ... } }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { message: 'Title is required' } or { message: 'Either content or image must be provided' }
  - `500 Internal Server Error`: { message: 'Failed to create announcement' }

---

### /users/staff-list
- **Method:** POST
- **Description:** Updates the staff list.
- **Payload:** { content }
- **Response:**
  - `201 Created`: { message: 'Staff list updated successfully' }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'Content is required' }
  - `500 Internal Server Error`: { error: 'Failed to update staff list' }

---

### /users/community-rules
- **Method:** POST
- **Description:** Updates the community rules.
- **Payload:** { content }
- **Response:**
  - `201 Created`: { message: 'Community rules updated successfully' }
  - `400 Bad Request`: { error: 'Content is required' }
  - `500 Internal Server Error`: { error: 'Failed to update community rules' }

---

### /users/staff-list
- **Method:** GET
- **Description:** Retrieves the latest staff list.
- **Response:**
  - `200 OK`: { staffList: { ... } }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `404 Not Found`: { message: 'Staff list not found' }
  - `500 Internal Server Error`: { message: 'Failed to retrieve staff list' }

---

### /users/community-rules
- **Method:** GET
- **Description:** Retrieves the latest community rules.
- **Response:**
  - `200 OK`: { communityRules: { ... } }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `404 Not Found`: { message: 'Community rules not found' }
  - `500 Internal Server Error`: { message: 'Failed to retrieve community rules' }

---

### /users/new-position
- **Method:** POST
- **Description:** Creates or updates a position.
- **Payload:** { position_name, questions, discord_channel, position_image, position_description, status }
- **Response:**
  - `201 Created`: { message: 'Position created successfully', position: { ... } }
  - `200 OK`: { message: 'Position updated successfully', position: { ... } }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { message: 'You can only create up to 10 positions' }
  - `500 Internal Server Error`: { message: 'Failed to create or update position' }

---

### /users/delete-position/:position_name
- **Method:** DELETE
- **Description:** Deletes a position by name.
- **Response:**
  - `200 OK`: { message: 'Position deleted successfully' }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `404 Not Found`: { message: 'Position not found' }
  - `500 Internal Server Error`: { message: 'Failed to delete position' }

---

### /users/shop-setup
- **Method:** POST
- **Description:** Sets up a new role in the shop.
- **Payload:** { role_name, price, role_id }
- **Response:**
  - `201 Created`: { message: 'Role added successfully', role: { ... } }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'role_name, price, and role_id are required' } or { error: 'Role name already exists' }
  - `500 Internal Server Error`: { error: 'Failed to validate role_id with Discord' }

---

### /users/points/:userId
- **Method:** GET
- **Description:** Retrieves the points for a specific user.
- **Response:**
  - `200 OK`: { user_id, points }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'userId is required' }
  - `500 Internal Server Error`: { error: 'Internal Server Error' }

---

### /users/add-points
- **Method:** POST
- **Description:** Adds points to a user.
- **Payload:** { user_id, points }
- **Response:**
  - `200 OK`: { message: 'Points added successfully', user: { ... } }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'user_id and points are required' }
  - `500 Internal Server Error`: { error: 'Internal Server Error' }

---

### /users/remove-points
- **Method:** POST
- **Description:** Removes points from a user.
- **Payload:** { user_id, points }
- **Response:**
  - `200 OK`: { message: 'Points removed successfully', user_id, points }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'user_id and points are required' }
  - `404 Not Found`: { error: 'User not found' }
  - `500 Internal Server Error`: { error: 'Internal Server Error' }

---

### /users/shop-setup
- **Method:** DELETE
- **Description:** Deletes a role from the shop.
- **Payload:** { role_name }
- **Response:**
  - `200 OK`: { message: 'Role deleted successfully', role: { ... } }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'role_name is required' }
  - `404 Not Found`: { error: 'Role not found' }
  - `500 Internal Server Error`: { error: 'Internal Server Error' }

---

### /users/buy-role
- **Method:** POST
- **Description:** Allows a user to buy a role.
- **Payload:** { user_id, role_name }
- **Response:**
  - `200 OK`: { message: 'Role purchased and assigned successfully', role: role_name }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'user_id and role_name are required' } or { error: 'Not enough points to buy this role' } or { error: 'User already has this role on Discord' }
  - `404 Not Found`: { error: 'Role not found' } or { error: 'User not found' }
  - `500 Internal Server Error`: { error: 'Failed to fetch user roles from Discord' } or { error: 'Failed to assign role on Discord' } or { error: 'Failed to send DM with embed' }

### /users/is-running
- **Method:** GET
- **Description:** Checks if the bot is currently running.
- **Response:**
  - `200 OK`: { isRunning: true, message: 'Bot is running.' } or { isRunning: false, message: 'Bot is not running.' }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `500 Internal Server Error`: { message: 'Internal Server Error' }

### /users/start-bot
- **Method:** GET
- **Description:** Starts the bot if it is not already running.
- **Response:**
  - `200 OK`: { message: 'Bot started successfully.' }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `500 Internal Server Error`: { error: 'Failed to start bot.' }

### /users/stop-bot
- **Method:** GET
- **Description:** Stops the bot if it is currently running.
- **Response:**
  - `200 OK`: { message: 'Bot stopped successfully.' }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `500 Internal Server Error`: { error: 'Failed to stop bot.' }

### /users/disable-command/:commandName
- **Method:** POST
- **Description:** Disables a specific command.
- **Response:**
  - `200 OK`: { message: 'Command <commandName> disabled.' }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `404 Not Found`: { error: 'Command not found' }
  - `500 Internal Server Error`: { message: 'Internal Server Error' }

### /users/enable-command/:commandName
- **Method:** POST
- **Description:** Enables a previously disabled command.
- **Response:**
  - `200 OK`: { message: 'Command <commandName> enabled.' }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `404 Not Found`: { error: 'Command not found' }
  - `500 Internal Server Error`: { message: 'Internal Server Error' }

### /users/logs
- **Method:** GET
- **Description:** Retrieves logs of actions performed by moderators.
- **Response:**
  - `200 OK`: [{ title, moderator, actionType, reason, details, timestamp }]
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `500 Internal Server Error`: { error: 'Internal Server Error' }

### /users/warn-user
- **Method:** POST
- **Description:** Issues a warning to a user.
- **Payload:** { user_id, reason, evidence, moderator }
- **Response:**
  - `201 Created`: { message: 'WARN action recorded successfully', moderation: { ... } }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'user_id, reason, and moderator are required' }
  - `500 Internal Server Error`: { error: 'Internal Server Error' }

### /users/mute-user
- **Method:** POST
- **Description:** Mutes a user for a specified duration.
- **Payload:** { user_id, duration, reason, evidence, moderator }
- **Response:**
  - `201 Created`: { message: 'MUTE action recorded successfully', moderation: { ... } }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'user_id, duration, reason, and moderator are required' }
  - `500 Internal Server Error`: { error: 'Internal Server Error' }

### /users/kick-user
- **Method:** POST
- **Description:** Kicks a user from the server.
- **Payload:** { user_id, reason, evidence, moderator }
- **Response:**
  - `201 Created`: { message: 'KICK action recorded successfully', moderation: { ... } }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'user_id, reason, and moderator are required' }
  - `500 Internal Server Error`: { error: 'Internal Server Error' }

### /users/unmute-user
- **Method:** POST
- **Description:** Unmutes a previously muted user.
- **Payload:** { user_id, moderator }
- **Response:**
  - `200 OK`: { message: 'User has been unmuted successfully' }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'user_id and moderator are required' }
  - `404 Not Found`: { error: 'Muted role not found' }
  - `500 Internal Server Error`: { error: 'Internal Server Error' }

### /users/discord-ban-user
- **Method:** POST
- **Description:** Bans a user from the server.
- **Payload:** { user_id, duration, reason, evidence, moderator }
- **Response:**
  - `201 Created`: { message: 'BAN action recorded successfully', moderation: { ... } }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'user_id, duration, reason, and moderator are required' }
  - `500 Internal Server Error`: { error: 'Internal Server Error' }

### /users/discord-unban-user
- **Method:** POST
- **Description:** Unbans a previously banned user.
- **Payload:** { user_id, moderator }
- **Response:**
  - `200 OK`: { message: 'User has been unbanned successfully' }
  - `403 Forbidden`: { message: 'API is currently disabled' }
  - `400 Bad Request`: { error: 'user_id and moderator are required' }
  - `500 Internal Server Error`: { error: 'Internal Server Error' }
