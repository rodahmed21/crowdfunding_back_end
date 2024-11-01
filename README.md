# Crowdfunding Back End
{{Roda Ahmed}}

## Planning:
### Concept/Name 
EmpowerEd - EduEmpower is a crowdfunding initiative dedicated to transforming lives through education in third-world countries. By pledging your support, you contribute directly to the educational journeys of individuals striving for a better future. 

### Intended Audience/User Stories
The intended audience for this initiative encompasses anyone interested in sponsoring and supporting an individual's educational journey. It invites all individuals who wish to contribute financially and have a genuine desire to uphold another person's right to education. Participants will have the opportunity to follow and engage with the progress of those they are helping along the way.ects through donations.

### Front End Pages/Functionality
Home Page / Hero Section: This will feature a navigation bar that includes links to About, Projects, Begin a Project, and user/login.

Begin a Project: This section will feature a form allowing users to enter various details, including:
•	The name of the project
•	A bio of the individual, detailing what their studies are and their age.
•	The target fundraising goal.
•	A timeline for the project.

Project Page section: Here, users will see a display of all projects. Each project will include:
•	A photo of the sponsored individual.
•	A brief biography.
•	The duration of their education.
•	The target fundraising goal.
•	The amount donated so far.
•	The deadline to reach the goal.
This structure provides a comprehensive view of each project, facilitating easy tracking and management while ensuring clarity for potential donors and stakeholders.

Pledges Section: This will include a form that allows users to:
•	Choose to remain anonymous or share their name.
•	Indicate the amount they wish to pledge.
•	Select the project they want to support.
•	Add comments.
•	Check a box to remain anonymous if they prefer.
This structure ensures a user-friendly experience while maintaining clarity and purpose throughout the site.

User Login Section Summary
The User Login section will include:
•	Username: A field for users to enter their chosen username for identification.
•	Projects: A list displaying the projects the user has created, allowing for easy navigation.
•	Comments: A section for users to view and manage comments related to their projects.
Once logged in, users will have the ability to:
•	Update Projects: Modify the details of their created projects to reflect any changes or updates.
•	Delete Projects: Remove projects they no longer wish to manage, ensuring their portfolio remains current.
This design enhances the user experience by providing straightforward access to account management and project oversight

### API Spec
|     HTTP   Method          |     URL                                      |     Purpose                             |     Request   Body      |     Successful   Response Code    |     Authentication/Authorisation             |
|----------------------------|----------------------------------------------|-----------------------------------------|-------------------------|-----------------------------------|----------------------------------------------|
|     GET                    |     http://127.0.0.1:8000/projects/          |     Provides   project list             |     N/A                 |     200                           |     N/A                                      |
|     POST                   |     http://127.0.0.1:8000/projects/          |     Makes a new   project               |     Project   object    |     201                           |     Must be   logged in                      |
|     GET                    |     http://127.0.0.1:8000/projects/1/        |     Provides   single project           |     N/A                 |     200                           |     Must be   logged in and project owner    |
|     GET                    |           http://127.0.0.1:8000/users/       |     Provides list   of users            |     User object         |     200                           |     N/A                                      |
|     POST                   |           http://127.0.0.1:8000/users/       |     Makes a new   user                  |     User object         |     201                           |     N/A                                      |
|     GET                    |     http://127.0.0.1:8000/api-token-auth/    |                                         |                         |     200                           |     Must be   logged in                      |
|     GET                    |     http://127.0.0.1:8000/pledges/           |     Provides list   of pledges          |     N/A                 |     200                           |     N/A                                      |
|     POST                   |     http://127.0.0.1:8000/pledges/           |     Makes a new   pledge                |     Pledge object       |     201                           |     Must be   logged in                      |


### DB Schema
"C:\Users\ahmed\OneDrive\Pictures\backend\DB S.png"

Creating Users in Insomnia
1. Choose a new HTTP Request 
2. Enter the url (https://empowered-c706f0b2c6b1.herokuapp.com/users/).
3. Set the method to POST.
4. Pick JSON as the content type and input the specified JSON fields:
{"username": "<your username>",
 "password": "<your password>",
 "first": <your first name>",
"last name": "<your last name>",
"email": "<your email>" 
}
5. Hit send.


Creating Projects on Insomnia:
1. Sign in as user.
2. Choose a new HTTP Request and set the method to POST.
3. Enter the following url (https://empowered-c706f0b2c6b1.herokuapp.com/projects/).
4. Pick JSON as the content type and input the specified following JSON fields:
{
	"title":"<>",
	"owner": "<>",
	"description":"<>",
	"image": "<>",
	"goal": "<>",
	"is_open": "<>",
	"date_created":"<>"
}
5. Navigate to the "Auth" section and select "Bearer Token."
6. Input the token number associated with the user who is setting up the project.
7. Where it says prefix, input “token”.
8. Hit send.

How to authorise users utilising token authentication on Insomnia:
1. Create a new HTTP Request.
2. Enter the url as (https://empowered-c706f0b2c6b1.herokuapp.com/api-token-auth/)
3. Set the method to POST.
4. Pick JSON as the content type and input the specified JSON fields:
{"username": "<your username>",
 "password": "<your password>"
}
5. Hit send.
6. The token should appear under Preview.
