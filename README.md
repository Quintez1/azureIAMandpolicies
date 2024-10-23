<p align="center">
<img src="https://imgur.com/ldEKU5o.jpeg" alt="Azure logo"/>
</p>

Project: Set Up an Azure Environment and Implement IAM Roles for Access Control

This project focuses on creating an Azure environment and configuring Identity and Access Management (IAM) roles to control access to Azure resources. This will provide you with practical experience in managing access, securing resources, and understanding the structure of Azure IAM. The format follows the structure from your IAM roles and policies project on GitHub.

- Step 1: Set Up an Azure Subscription
If you don’t have an Azure subscription, you’ll need to create one:

1. Create an Azure account by visiting the Azure website.
2. You can use the Free Tier to access Azure services for free for a limited time. Azure offers $200 in credits for the first 30 days.
3. Once you have your account, sign in to the Azure Portal at portal.azure.com.

<img src="https://i.imgur.com/kdSkNDA.png" alt="Azure"/>
</p>

- Step 2: Navigate to Azure Active Directory (Azure AD)
Azure Active Directory (Azure AD) is the cloud-based identity and access management service that provides access to Azure resources.

1. In the Azure Portal, type Azure Active Directory into the search bar at the top.
2. Click on Azure Active Directory from the dropdown to open the dashboard.

<img src="https://i.imgur.com/8io9vC8.png" alt="Azure"/>
</p>

- Step 3: Create a New User in Azure Active Directory (Microsoft Entra)
Azure AD users are identities that can authenticate and access resources in the Azure environment.

1. In the Azure AD dashboard, go to Users under Manage on the left-hand side.
2. Click on New user at the top.
3. For User Type, choose Create user.
4. Fill out the required information:
- User Name: Enter a unique username (e.g., testuser@yourdomain.onmicrosoft.com).
- Name: Give a descriptive name (e.g., Test User).
- Password: Select Let me create the password and assign a temporary password.
5. Leave the default values for Groups and Roles for now.
6. Click Create to create the user.

<img src="https://i.imgur.com/AVG7hkT.png" alt="Azure"/>
</p>
  
- Step 4: Assign a Role to the User
Azure uses Role-Based Access Control (RBAC) to assign roles and permissions to users.

1. Return to the Azure Active Directory dashboard.
2. Click Users again and find the user you just created (Test User).
3. Select the user and navigate to the Assigned roles section under Manage.
4. Click Add assignment and choose a role:
- Reader: Grants read-only access to Azure resources.
- Contributor: Allows users to manage resources but not assign permissions.
- Owner: Full access, including the ability to assign permissions to others.
5. Select the Reader role for this project.
6. Click Assign.
Now, this user has been assigned the Reader role, which provides read-only access to Azure resources. You’ll test the permissions later.

<img src="https://i.imgur.com/eUbNJzn.png" alt="Azure"/>
</p>

- Step 5: Create a Resource Group in Azure
A Resource Group in Azure acts as a container that holds related resources for an Azure solution.

1. From the Azure Portal dashboard, click Create a resource.
2. In the search bar, type Resource Group and select it from the results.
3. Click Create and fill out the following details:
- Subscription: Choose the subscription under which you want to create the resource group.
- Resource Group Name: Enter a name like TestResourceGroup.
- Region: Choose a region close to you for performance reasons.
4. Click Review + Create, then Create to provision the resource group.

<img src="https://i.imgur.com/NfUccld.png" alt="Azure"/>
</p>

- Step 6: Assign Access to the Resource Group
Now that you have a resource group, you can assign the user you created to this group.

1. Go to your newly created TestResourceGroup in the Resource Groups section of the portal.
2. In the left-hand menu, click on Access Control (IAM).
3. Click Add Role Assignment.
4. Select the Reader role again and click Next.
5. Under Assign access to, choose User, group, or service principal.
6. Search for the user (Test User) you created earlier and select them.
7. Click Review + Assign.

Now, this user has Reader access specifically to the TestResourceGroup.

<img src="https://i.imgur.com/N5j0xbg.png" alt="Azure"/>
</p>

- Step 7: Test the User’s Permissions
To verify that the user has the correct access permissions:

1. Sign out of the Azure Portal and log in as the newly created Test User.
- Use the credentials you set up earlier (username and temporary password).
2. After logging in, you’ll be prompted to change the temporary password.
3. Once logged in, navigate to Resource Groups in the Azure portal.
4. Check if the user can view the TestResourceGroup but cannot create or delete any resources inside it. This confirms that the Reader role has been applied correctly.

<img src="https://i.imgur.com/ujfLPXn.png" alt="Azure"/>
</p>

- Step 8: Secure the Azure Environment
To further secure your environment, it’s best to follow security best practices.

- Enable Multi-Factor Authentication (MFA)
1. Go back to the Azure Active Directory dashboard.
2. Under Users, find the user (Test User) and click on Multi-Factor Authentication.
3. Select Enable MFA for this user.
4. When the user logs in next, they will be prompted to set up MFA using an authenticator app or phone.

<img src="https://i.imgur.com/I6zLrMC.png" alt="Azure"/>
</p>

- Implement the Principle of Least Privilege
1. Review all users and roles in your Azure Active Directory.
2. Ensure that each user has only the permissions necessary for their role—avoid assigning overly broad roles like Owner unless required.
3. Periodically audit user roles and remove any unnecessary access.

- Step 9: Clean Up Resources
Once you've completed testing and verification, clean up any resources to avoid unnecessary charges.

1. Delete the Test Resource Group:

- Go to Resource Groups in the Azure portal.
- Select the TestResourceGroup and click Delete Resource Group.
- Confirm the deletion by typing the resource group’s name.

<img src="https://i.imgur.com/ubxGg96.png" alt="Azure"/>
</p>

2. Delete the User:

- Go back to Azure Active Directory > Users.
- Find Test User and click Delete.

<img src="https://i.imgur.com/uDt6COw.png" alt="Azure"/>
</p>

Project Summary
By the end of this project, you will have:

- Created an Azure Active Directory (Azure AD) user.
- Assigned IAM roles to the user using RBAC.
- Created a Resource Group and applied access control to the group.
- Tested the permissions of the user to ensure the role assignment was correct.
- Enhanced security by enabling Multi-Factor Authentication (MFA).

This project demonstrates how to manage access to Azure resources, a fundamental task for any cloud administrator or engineer. You’ve gained hands-on experience with Azure IAM, user management, role assignments, and best security practices.
