# CalorieTracker
A Calorie Tracker app/software that I made for a course at Louisiana State University, Shreveport. The project requiredwe used C# in Visual Studio and Microsoft SQL Server Manager

Installation and Run Guide
-----------------------------------------------------------------
1. Make sure to import the .bacpac file to Microsoft SQL Server Manager; name it however you want
2. Start running your SQL server
3. Open up CalorieTracker and add a new data connection
4. Make sure the connection is a Microsoft SQL Server, and use the SQL server you just started running
5. Choose the imported database
5. On the newly created data connection, open up properties and find the connection string which you should then copy
6. Under Login.cs, Register.cs, and Home.cs you should see functions named Login_Load(Line 30), Register_Load(Line 39), and Home_Load(Line 61)
7. In which you should see a SqlConnection variable called "cn";(look something like  cn = new SqlConnection(@"Data Source=datasource")
8. In between the QUOTATION MARKS paste over whatever is there; this should be done for all three
	- Make sure to include MultipleActiveResultSets=true for Home_Load
9. Make to save the changes and the progam should run if the server is running



Login Form
-----------------------------------------------------------------
- The login form is the first thing the user sees when running the program
- Within this form there are four main objects, users will interact with, the username textbox, the password textbox, the registration button, and the login button

Username and password textboxes
	- Used for the user to input a registered username and password

Registration button
	- Takes users to the registration form where they can registered and closes this form
	
Login button
	- Uses a SQL database to store user information
	- If the user has inputed registered username and password in the correct textboxes, their data is compared to the SQL database data, the user is taken to the home form and the login form is closed
	- If the user has inputed an unregistered name or password, an error message appears telling the user so
	- If the user has left a field blank, an error message appears telling the user so

Registration Form
-----------------------------------------------------------------
	- The registration form only appears if the user clicks on the appropriate button in the login form
	- Here users can register an account
	- Five main objects, username textbox, password textbox, confirm password textbox, register account button, and the login screen button
	
Username, password, and confirm password textboxes
	- Used to input and confirm acccount information
	
Register Button
	- Registers username and password into SQL database along with a hidden randomly generated user ID using Guid along with a base calorie goal(0)
	- If their is already an account with that username, or the passwords don't match up, or a textbox is left blank, an appropriate error message shows appears
	- Otherwise a message pops up telling them that their account was made

Home Form
-----------------------------------------------------------------
- In this section objects descriptions will be grouped together in groups

Calorie Goal Settings
	- Text box allows a user to set a calorie goal, which unfortunately is not tracked at this time
	- Users can click on a set calorie goal button which makes the text box uneditable and it's background invisible
	- The clear calorie goal button reverts these changes and clears the text in the textbox
	- The daily calorie goal is copied to a seperate variable
	
Calorie Manager
	- Allows users to add or subtract calories through the appropriate NumericUpDown object
	- The [Enter] key is used to submit these changes 
	- Daily calories are tracked in a label to the left
	- Attempting to make the daily calories negative results in a error message
