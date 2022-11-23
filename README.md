# Interview-Creation-Portal

To run this project you need to install NodeJS (npm) and MySQL server on your machine.

To setup the web server:

Go to the project directory and run the terminal command as follows:
```
cd interview
cd server
npm install
```
To setup the MySQL database:

1. Create a Database/Schema name as "InterviewPortal" or run the following SQL queries.
```
CREATE DATABASE InterviewPortal;
```
```
USE InterviewPortal;
```
2. Add two tables "users", to hold data of the available users and "interviews", to hold the data of the upcoming interviews. Run the following SQL query.
  ```
  CREATE TABLE users (
    name VARCHAR(100) NOT NULL,
    email_id VARCHAR(100) NOT NULL,
    PRIMARY KEY (email_id));
  ```
Add some random names with email addresses to the users tables. Run the following SQL query.
```
INSERT INTO users (name, email_id) VALUES ('Disha Srivastava', 'dishasrivastava@gmail.com');
INSERT INTO users (name, email_id) VALUES ('Shreya pandey', 'pandey.shreya03@gmail.com');
INSERT INTO users (name, email_id) VALUES ('Pawan Kumar', 'pawan7yadav@gmail.com');
INSERT INTO users (name, email_id) VALUES ('Suraj kumar', 'surajkumar@gmail.com');
INSERT INTO users (name, email_id) VALUES ('Pragati', 'pragati.singh@gmail.com');
INSERT INTO users (name, email_id) VALUES ('Madhulika Singh', 'Madhulika.singh@gmail.com');
```
Create the table interviews with fields id, email1, email2, startTime, endTime, resume. Run the following SQL query.
```
CREATE TABLE interviews (
  id INT NOT NULL AUTO_INCREMENT,
  email1 VARCHAR(100) NOT NULL,
  email2 VARCHAR(100) NOT NULL,
  startTime DATETIME NOT NULL,
  endTime DATETIME NOT NULL,
  resume VARCHAR(255),
  PRIMARY KEY (id));
```
You may or may not any data into the interviews table. The data will be added automatically when you schedule a new interview.

Change the following in ```server/dbServicejs``` if your MySQL server is setup on different port or has different credentials.
![MySQL credentials](https://i.paste.pics/9WL5X.png)

Now when everything is setup. Run the server:
```
cd interview
cd server
nodemon app
```
If everything is successful you will the see the text "app is running" and "db is connected" on your terminal.
Then open go to client and open index.html. 