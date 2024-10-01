# Actors
- Common Users: County Clerks, Election Officials - County clerks record inventory and check certificates and local or state-level election workers who ensure that voting processes run smoothly and are properly supported
- System Administrators - System admins manage system and accounts, troubleshooting any mishap, and logging issues and updates.
- VSTOP personnel - Software Developers maintaining and modifying our everyone

# Use Cases

### UC1: User Authentication and Authorization
- Description: All users must be authenticated before accessing the system before proceeding in the system. This would also let the system determine what permission you have and display data or provide action accordingly.
- Actors: Common users, system admin, VSTOP personnel
- Flow: User will be on the login page if they haven't done so, or it expired. Enters their email address and password. It will authenticate the user with backend and give back its authorization status with a token that expire every 15 minutes so user only able to see data or perform action they are allowed to. If email doesn't exist in the system it will ask if they want to register and take them to the registration page.
- BR1

### UC2: Basic Inventory Management
- Description: Users must manage election equipment and certificates by creating, reading, modifying, and deleting entries in the system. This ensures all equipment is tracked accurately.
- Actors: Common users, system admin, VSTOP personnel
- Flow: After logged into the system, user navigate to the inventory section. Selects an option to create, read, modify, or delete an entry. Creates a new entity or modifies an existing entity with relevant inputs. Confirms the action to save or delete the entry. System validates the entry and updates the database.
- BR1

### UC3: Bulk Inventory Management
- Description: This allows county clerks to perform bulk actions (e.g., adding, updating, or deleting multiple items simultaneously), which increases efficiency and reduces the time spent on managing inventory.
- Actors: Common users, system admin, VSTOP personnel
- Flow: Once a user logged in for the site, they can select bulk management section. Applies bulk actions like "Add," "Edit," or "Delete" to the selected item. User can add more than one type of entity for entry. Once confirmed, the system processes the updates and refreshes the view. A success message or error message is displayed.
- BR1

### UC4: Descriptive Error Messages
- Description: Provides users with detailed error messages that help identify and fix issues during interaction with the system. This enhances user experience by clearly outlining what went wrong and offering troubleshooting guidance.
- Actors: County Clerks, Election Officials, System Admins
- Flow: When user performs an invalid operation (missing a required field, entering incorrect data). The system validates the input and detects the error. A descriptive error message appears on the screen, explaining the issue.
- BR2

### UC5: At-a-glance Dashboard
- Description: Provides a user-friendly dashboard with quick access to the most important functions, such as inventory management, reporting, and user settings. The dashboard is designed for fast loading and easy navigation.
- Actors: County Clerks, Election Officials
- Flow: After user logs into the system, they will see the dashboard widgets or menus provide access to various sections: "Inventory," "Bulk Management," or  "Reports", etc. User clicks on the desired section to be taken to the relevant functionality. The system provides shortcuts or notifications for items requiring urgent attention
- BR2

### UC6: Static Reporting
- Description: Generates reports summarizing inventory information in a predefined, non-interactive format
- Actors: County Clerks, System Admins, Election Officials
- Flow: After user logs into the system and navigates to the type of the report they would like to see. System processes the request and generates a static report in a table format.
- BR2

### UC7: Dynamic Tables
- Description: Provides dynamic, sortable, and filterable tables to manage election equipment. Users can adjust table length, and apply filters, improving overall management efficiency.
- Actors: County Clerks, System Admins, Election Officials
- Flow: User access a dynamic table that can be sorted and filtered by various criteria, such as equipment type or status. They can adjust the table length, apply specific filters to narrow down results, and use these features to streamline equipment inventory management for audits and certification purposes.
- BR2

### UC8: Audit Report
- Description: During an audit, the system should be able to pull data randomly that fits the audit requirement. Randomly selected components totaling 1/10th of 1% of the total election equipment in the state of Indiana.
- Actors: System admin, VSTOP personnel
- Flow: User with permission can select the audit button and select the entity or entities they need for the audit and hit generate button. It will get data through backend endpoint and form into a static report. 
- BR2

### UC9: Page Demos
- Description: A help function on one of the corners of the page to give new users a quick tutorial on how to manage the vault.
- Actors: County Clerks, System Admins, Election Officials
- Flow: User opens any page after logging in. The user clicks on the tutorial button on the corner of the page In accordance to the page the user is currently on, the demo given will change to match it with description of how each part of the page does.
- BR2

### UC10: User Management
- Description: Allows system administrators to approve, modify, and delete user accounts, manage user roles, and set permissions, ensuring proper access control and system security.
- Actors: System Administrators, VSTOP personnel
- Flow: A system administrator navigates to the user management section after logging in. They will be able to see a list of user who registered, or modify existing user data (such as roles or permissions), or delete a user account. The system validates the changes, updates the database, and reflects the new permissions or user status immediately.
- BR1