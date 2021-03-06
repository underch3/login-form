Task

Create a registration / login form, where the user can enter an email (as login), name and password.

Registration form should have validation on password - at least 6 symbols, 
should contain at least 1 uppercase letter and a special sign (i.e. !@#$%^&*()_).

After sign up - send a confirmation email “Welcome, <username>”.

After login - save session (i.e. refreshing browser or opening same site in new tab should keep you signed in). 
Show a welcome message “Hello, <username>”.

For sign in and sign up create your own CUSTOM API (i.e. not standard included in Laravel).

You can use MSSQL/MySQL or SQLite for database. Please, try to keep code readable, comments will be welcome. 
Using REST standards for API is preferrable. +It is OK to use any third-party libraries if needed. 
Don’t spend too much time for edge-cases (i.e. error scenarios), we can discuss them separately if needed.

Bonus:
Forgot password functionality. User should be able to enter email and receive a password reset link. 
The link should be valid for 60 minutes. 
Only the last reset link should be working (if resetting password multiple times)
---------------------------------------------
Table structure for table `users`

create table users
(
   id int auto_increment,
   name varchar(100) not null,
   email varchar(100) not null,
   password varchar(100) not null,
   created_at datetime not null,
   token varchar(100) not null,
   tokenExpire_at datetime not null,
   constraint users_pk
      primary key (id)
);

create unique index users_email_uindex
	on users (email);
	
Change creditentials in RegistrationController.php and PasswordController.php to your creditentials in Mailtrap.io
$mail->Username = 'YOUR_USERNAME';   //username
$mail->Password = 'YOUR_PASSWORD';   //password
	
------------------------------------------------
