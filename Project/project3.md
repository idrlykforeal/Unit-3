# Unit 3 Project: Sofi's Elite Candy Shop
![candy](https://user-images.githubusercontent.com/100017195/221410724-a3321f80-15a8-4819-a2be-ee8a332b651b.jpeg)

## Criteria A: Planning

## Problem definition(Client identification)
Sofi is planning to open an elite candy shop and is in need of a professional inventory management platform. The platform must be secure and allow multiple worker accounts to update the candy inventory. All the employees should be able to create a unique account, and able to login to the platform and update the inventory details for the sales of the company. Additionally, the platform should include the functionality to view charts that display portions of candies from different companies to check which company is occupying the most stock in the candy shop in order to work together with external investments.

## Proposed Solution
An appropriate solution would include a localized computer application with a GUI (Graphical User Interface) that can save data into a database, taking the client's requirements into consideration. Python is a suitable programming language for the solution since it is open source, established, and supported across several platforms, including macOS, Windows, and Linux. SQLite would be a suitable option for the database because it is an embedded, serverless relational database, allowing both the software and the database to be translated.

Since SQLAlchemy supports ORM, it is the preferred method for interacting with the SQLite database (Object Relational Mapper). An ORM is a layer of database abstraction that acts as a go-between for the code and the database engine, simplifying queries and streamlining the code. For its simplicity and elegance, KivyMD's Interface was selected. Development is simple because to the object-oriented structure of this GUI framework. 

**Design statement**  

I will design a Python application running on the KivyMD GUI framework which stores data in a SQLite database for Sofi. This application lets Sofi and her employees manually manage the inventories from the database, and able to show the log in history for them to keep track of who has been working. 
The application also displays a chart of the portion of candy from different companies. Everything is secured under a hashed login system to separate the employee's work. It will take approximately 1 month to complete and will be evaluated according to criteria below:


## Success Criteria

1. Application has secure login and registration system
2. The password for users are secure (hashed).
3. Users able to view login history of all users.
4. There will be a candy database that stores the inventories records the candy name, company, amount, taste, and expiration date.
5. Users able to view, add, remove candy inventories from the candy database.
6. Users able to view a diagram that showcases the porportion of candy from different companies.
7. Users able to view details of items that are expiring in 5 days.


# Criteria B: Design


## ER diagram
![IMG_1ADD4D2801D8-1](https://user-images.githubusercontent.com/100017195/223334871-549f3154-0a1e-4e4b-a381-82fdef3b405f.jpeg)


**Fig.1** This is the ER diagram showing objects in candy table and user table. In the candy table, there are 7 different columns including type, taste, company, amount, date_added, and id (shown above) which each column will have the specific data type after the column name. The second table has 4 columns which are username, id, email and password. This diagram also shows that 1 user can have multiple diary. The underlined column name is the primary key which have to be unique and for these 2 tables the primary key will be the id. The two objects do not have any relations since all the users are able to modify the object database. 

## System Diagram
![system_diagram_U3_project](https://user-images.githubusercontent.com/100017195/223145333-bf3211e2-a595-4fb0-a6ab-6faaee06cc12.png)
**Fig 2** shows the system diagram from the input(keyboard) to the output which includes different systems being used in this project such as version of coding language(python and KivyMD) and application(PyCharm), computer version and detail(Processor,version, memory, etc.), module and database and the output screen(application interface on the computer screen).

## Wireframe Diagram
![wiafram](https://user-images.githubusercontent.com/100017195/223319608-d2a6ea07-90b5-477b-b0c3-d032cc49e098.jpeg)
**Fig 3** shows the wireframe diagram or a prototype of the application's GUI. In this diagram, different screen that will be in the application will be put with different buttons. Arrows from one button to screen show which screen the button will open when it is pressed and released.

## Flow Diagrams

### Login
![Flow chart Login](https://user-images.githubusercontent.com/100017195/223455727-9a1d1c98-66ce-45c5-9b22-882a481d55c4.jpeg)
**Fig 4** shows the flow diagram for the method of try_login which validates the username and password and logs in the user if the data is correct.


### Update Homescreen Expiring-soon Table
![flow-homescreeen_update](https://user-images.githubusercontent.com/100017195/223455903-7625307c-ccf0-458f-b97a-9430aafc1c3a.jpeg)
**Fig 5** shows the flow diagram for getting candy informaton from the database puts all items expiring in 5 days into another list, and displays them.

### Add item
![Flow chart add item](https://user-images.githubusercontent.com/100017195/223455958-a8d6558c-4768-4c4c-845a-69d4eaeab32e.jpeg)
**Fig 6** shows the flow diagram for adding an item of candy to the database.

## UML Diagram

![Project 3 UML](https://user-images.githubusercontent.com/100017195/223145631-091e178b-5bc9-420d-bb77-fa6085ae5e26.png)
**Fig 7** This shows the UML diagram for the all the classes use in this project with methods in each class. There are 2 main parents class which are MDScreen and MDApp which all the other class inherited methods and attributes from them. The inheritance is shown by the arrow.


## Test Plan
| Type                | Description                                  | Process                                                                                                                                                                                                                             | Anticipated Outcome                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | completion date | criterion |
|---------------------|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|-----------|
| Unit Testing        | User Registration                            | 1. Run candy_shop.py file 2. Click the Sign Up button on the application screen 3. Input the appropriate information in each textfield following the hint text 4. Click Register                                                    | After clicking the register button, if the user already exists, the username textfield is going on error and a hint text will be shown letting the user know that the username already exists. If the password entered and the confirm password don't match, a red message will appear and notify the user that the passwords do not match. If emails do not include @ or includes space, error message will also appear. If the password is less than 5 characters, error message will appear to inform the users that the password is too short. If all instructions were correctly followed it will take the user back to the Login screen followed with another pop up dialog indicating that the user is successfully created. |           Feb 7 | A         |
| Unit Testing        | User Login                                   | 1. Run candy_shop.py file 2. Input the appropriate information in each textfield following the hint text 3. Click Login                                                                                                             | After clicking the login, if the user doesn't exist, a hint text will appear letting the user know that the username doesn't exist in the database, with an error in the textfield. Likewise, if the password and username do not math, error message and error in the textfield will also appear. If the user and password exists and matches the records in the database, the application should move to the Home Screen.                                                                                                                                                                                                                                                                                                         |          Feb 15 | A         |
| Unit Testing        | Logout                                       | 1. Login 2. Click Logout button                                                                                                                                                                                                     | A pop up screen will show up and ask if the user is sure to log out. If yes is pressed, application should move to Login Screen, if no is pressed, application stays at Home Screen                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |          Feb 19 | A         |
| Integration Testing | Login and Registration                       | 1. Run candy_shop.py file 2. Click the Register button on the application screen 3. Input the appropriate information in each textfield following the hint text 4. Click Register 5. Try login with the same credentials registered | If the user followed the on screen instructions properly and registered for a user, then the user able to login with the same username and password that was just registered. If not, responsible errors will be shown as User Login and User Registration stated                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |          Feb 19 | B         |
| Unit Testing        | Adding Candy Item                            | 1. Run candy_shop.py file 2. Login with previously registered information 3. Click "Add Item" on the home screen 4. Input into the appropriate fields 5. click "add"                                                                | If the fields are inputted correctly and the program, the user will be receiving a pop up screen that informs them that candy item is successfully added. If not, error message will be displayed on the screen according to the Value errors or missing inputs.                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |          Feb 20 | B         |
| Integration Testing | Deleting Candy Item in View Inventory Screen | 1. Run candy_shop.py file 2. Login with previously registered information 3. Click "Inventory" on the home screen 4. Select row to delete 5. Click delete, and confim delete                                                        | After delete is clicked, a pop up screen will show up to warn the users that once deleted, the item will not be recoverable. Once user clicks confirm delete, the item will be deleted from the database, and it will also be gone from the displayed list in the same screen                                                                                                                                                                                                                                                                                                                                                                                                                                                       |          Feb 20 | B         |
| Integration Testing | Add Candy Item, view inventory               | "1. Run candy_shop.py file 2. Login with previously registered information 3. Click ""Add Item"" on the home screen 4. Input into the appropriate fields 5. click "add" 6. click "view inventory"                                   | If the fields are inputted correctly and the program, the user will be receiving a pop up screen that informs them that candy item is successfully added. After entering the inventory viewing screen, they will be able to see the new added inventory. If not, error message will be displayed on the screen according to the Value errors or missing inputs.                                                                                                                                                                                                                                                                                                                                                                     |          Feb 21 | B         |
| Code Review         | Reviewing Code                               | Going through the code and making sure unused parts are removed, variables are named properly and comments are placed appropriated                                                                                                  | Easy to understand and easy to debug code for future development.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |          Feb 21 | B         |


## Record of Tasks
| task no | planned action                                   | Planned Outcome                                                                                                   | time estimate | completion date | criterion |
|---------|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|---------------|-----------------|-----------|
|       1 | Planning: First Meeting with client              | Start collecting the context of the problem                                                                       | 6 mins        |           Feb 7 | A         |
|       2 | Planning: Defining problem and proposed solution | Start on refining client's requirements and tools needed                                                          | 1 h           |          Feb 15 | A         |
|       3 | Meet the client again                            | come up with a list of approved success criteria                                                                  | 10 mins       |          Feb 19 | A         |
|       4 | diagram planning                                 | wiafram diagrams finished                                                                                         | 20 mins       |          Feb 19 | B         |
|       5 | diagram planning                                 | System diagram,                                                                                                   | 20 mins       |          Feb 20 | B         |
|       6 | diagram planning                                 | wireframe,                                                                                                        | 20 mins       |          Feb 20 | B         |
|       7 | diagram planning                                 | flow diagram,                                                                                                     | 20 mins       |          Feb 21 | B         |
|       8 | diagram planning                                 | ER diagram,                                                                                                       | 20 mins       |          Feb 21 | B         |
|       9 | diagram planning                                 | UML diagram                                                                                                       | 20 mins       |          Feb 22 | B         |
|      10 | UI development                                   | create the login and register page UI                                                                             | 25 mins       |          Feb 23 | C         |
|      11 | app development                                  | finish login page                                                                                                 | 45 mins       |          Feb 24 | C         |
|      12 | app development                                  | finish register page                                                                                              | 45 mins       |          Feb 24 | C         |
|      13 | UI development                                   | create the show login history page UI                                                                             | 20 mins       |          Feb 25 | C         |
|      14 | app development                                  | connect to databases for register and login, able to display login history                                        | 45 mins       |          Feb 25 | C         |
|      15 | app development                                  | finish show login history page                                                                                    | 2 h           |          Feb 25 | C         |
|      16 | app development                                  | Learn SQL alchemy                                                                                                 | 45 mins       |     February 27 | C         |
|      17 | UI development                                   | Finish the UI of manage inventory                                                                                 | 30 mins       |         March 1 | C         |
|      18 | app improvment                                   | validate email input in registration page, validate amount in candy inventory                                     | 30 mins       |         March 1 | C         |
|      19 | app development                                  | making sql alchemy object of candy                                                                                | 50 mins       |         March 1 | C         |
|      20 | app improvment                                   | create validation for password length: at least 5 characters                                                      | 10 mins       |         March 2 | C         |
|      21 | UI development                                   | create UI for add item and view inventory                                                                         | 30 mins       |         March 2 | C         |
|      22 | app development                                  | create methods for adding items and viewing inventory, linking to databases                                       | 1 h           |         March 2 | C         |
|      23 | app development                                  | creating methods to calculate porportions of different candy companies and plot with matplotlib's pie chart       | 40 mins       |         March 3 | C         |
|      24 | app development                                  | establish functionality of logout button                                                                          | 5 mins        |         March 3 | C         |
|      25 | app development                                  | check box determine if the passwords are protected                                                                | 10 mins       |         March 3 | C         |
|      26 | app development                                  | if user already exists, show error in registration in username                                                    | 10 mins       |         March 3 | C         |
|      27 | app development                                  | clear all errors and texts shown in text fields when changing pages out of text fields                            | 10 mins       |         March 3 | C         |
|      28 | app development                                  | finish date picker, able to store in db files, update the view inventory so that expiration date is also viewable | 50 mins       |         March 4 | C         |
|      29 | app development                                  | finish creating pop up screens to confirm if the user would like to logout and delete objects                     | 45 mins       |         March 5 | C         |
|      30 | app development                                  | when user submit adding one object of candy, text field clears, and error clears.                                 | 10 mins       |         March 5 | C         |
|      31 | app development                                  | create dropdown list for candy taste input                                                                        | 40 mins       |         March 5 | C         |
|      32 | refine documentation                             | refine criteria A, put figure lables and captions for figures uploaded                                            | 20 mins       |         March 6 | A, B      |
|      33 | test plans                                       | establish and carry out test plans                                                                                | 1 h           |         March 7 | B         |
|      34 | upload and justify critera C                     | upload and justify critera C                                                                                      | 2 h           |         March 8 | C         |
|      35 | video timestamp planning                         | video timestamp planning                                                                                          | 1 h           |         March 8 | D         |
|      36 | video record and upload                          | video record and upload                                                                                           | 45 mins       |         March 8 | D         |


# Criteria C: Development


## Existing Tools

| Software/Development Tools | Coding Structure Tools          | Libraries      |
|----------------------------|---------------------------------|----------------|
| OOP paradigm               | for loops                       | KivyMD Library |
| Relational databases       | Objects, attributes and methods | sqlite3        |
| SQLite, ORM                |                                 | matplotlib     |
| Python                     |                                 | sqlalchemy     |
| Kv                         |                                 |                |


## List of techniques used

1. 

## Computational Thinking

#### Decomposition



#### Pattern recognition, generalization and abstraction



#### Algorithms


## Development

#### OOP

#### MVP - Minimum Viable Product

In order to validate our concept of creation, we created a MVP as a prototype to make sure our concept is reliable and
achievable. 

## Criteria D: Functionality

## Demonstration Video

4 mins
last 30 secs how the code is well organized so that future developers can extend it
