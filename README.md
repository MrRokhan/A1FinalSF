# A1FinalSF
# Repository Layout and Version Control Approach
## Repository Layout
The repository is structured to facilitate easy navigation and efficient development. Within the src/ directory, the primary folder is app/, which contains all core application components and modules. This folder includes subdirectories for different functionalities: channel-management/ handles channel-related features, chat/ covers chat functionalities, and dashboard/ contains components for the dashboard view. Other important directories include group-management/ for group-related features, login/ for login page components, services/ for data and authentication services, and user-management/ for user-related functionalities. Additionally, the user-profile/ directory contains components associated with user profiles. The repository also includes important files like auth.guard.ts for route guarding, auth.service.ts for authentication services, and data.service.ts for data operations. Data.json is supposed to be there but did not get around to do that.

## Version Control Approach
My version control strategy involved committing changes directly to the main branch. This approach simplifies the workflow by eliminating the need for multiple branches and merges. Each change or update is committed with a descriptive message that clearly indicates the nature of the change, such as "Added user authentication" or "Added a login page".

# Data Structures
The application uses several key data structures to manage users, channels, and groups:

Users: Defined by the User interface, which includes properties like id, username, email, and role. Roles can be 'Super Admin', 'Group Admin', or 'User', which determine the user's access level. Users are associated with arrays for groups and channels, indicating their memberships.

Channels: Represented by the Channel interface with properties for id, name, description, and a users array. The users array contains IDs of users participating in the channel, facilitating the organization of discussions.

Groups: Defined by the Group interface, including id, name, and description. Groups have arrays for channels and users, listing associated channels and members, respectively.

These structures allow the application to effectively manage and persist data related to users, channels, and groups, ensuring smooth operation and user management.

# Rest API

In my current setup, I use Angular’s DataService to interact with local storage rather than a REST API. The DataService handles saving, loading, and deleting data from local storage, which simulates data persistence but is not ideal for a scalable application. To improve this, I should integrate REST API calls using Angular’s HttpClient to communicate with a Node.js server. This would involve creating endpoints on the server for managing users, groups, and channels, and then modifying my Angular services to make HTTP requests to these endpoints. This approach would ensure that data is managed on the server, providing a more robust and scalable solution.

# Angular Architecture 

In my Angular application, the architecture is organized into several standalone components, each with a specific role. The LoginComponent handles user authentication, checks credentials against mock data, and redirects users based on their roles, managing the login state via local storage. The DashboardComponent is responsible for displaying user-specific data, such as channels and groups, using mock data and providing methods to filter these based on user ID. The ChannelManagementComponent allows for the management of channels and user permissions, supporting operations like adding, editing, and deleting channels, and managing user memberships, with data persisted in local storage. Finally, the UserManagementComponent focuses on user management tasks, such as adding and deleting users, with a form for creating new users and ensuring unique usernames. Each component is designed to handle distinct aspects of the application, interacting with local storage to persist and reflect data changes.







