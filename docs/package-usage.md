# Package Usage

When using the `project_build_package`, you have the option to make direct requests within your code. This method is suitable for developers who prefer integrating request functionalities directly into their applications or scripts. Here's how you can use the package for direct requests:

## Installation

First, install the `project_build_package` using npm:

```bash
npm install project_build_package
```

## Authentication

Use the request function from the package to send project requests. Ensure that you provide valid parameters such as email, GitHub link, project requirements, and project language. Upon successful authentication and request submission, you will receive a project key.

## Checking Status

You can periodically check the status of your request using the provided functions like followup or details. This allows you to track the progress of your request directly from your code.

## Notifications

Note that direct requests made through the package are not linked to any external dashboard. While you can check the status of your request programmatically, notifications will not be sent, and your request will not be visible on any dashboard.

## Alternative: Classic Dashboard

If you prefer not to use the package for direct requests, you can use the Classic Dashboard available at https://sabry134.github.io/website_requests/#/. The Classic Dashboard provides a user-friendly interface for making and managing project requests. It allows users to submit requests, track their status, and receive notifications when there are updates. This method is suitable for users who prefer a graphical interface over programmatic access.

## Conclusion

The project_build_package offers a convenient way to make direct requests within your codebase. However, if you prefer a graphical interface with notifications, you can opt for the Classic Dashboard. Choose the method that best suits your workflow and preferences.

