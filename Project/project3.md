# Unit 3 Project: Sofi's Elite Candy Shop
![candy](https://user-images.githubusercontent.com/100017195/221410724-a3321f80-15a8-4819-a2be-ee8a332b651b.jpeg)

## Criteria A: Planning

## Problem definition(Client identification)
Sofi is planning to open an elite candy shop and is in need of a professional inventory management platform. The platform must be secure and allow multiple worker accounts to update the candy inventory. Additionally, the platform should include the functionality to view charts that display portions of candies from different companies.

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

![er](https://user-images.githubusercontent.com/100017195/222114177-2b34017e-7f74-4826-9dae-1965ea68eb30.jpeg)

**Fig.1** This is the ER diagram showing the relationship between candy table and user table. In the candy table, there are 7 different columns including type, taste, company, amount, date_added, and id (shown above) which each column will have the specific data type after the column name. The second table has 4 columns which are username, id, email and password. This diagram also shows that 1 user can have multiple diary. The underlined column name is the primary key which have to be unique and for these 2 tables the primary key will be the id.

## System Diagram
![system_diagram_U3_project](https://user-images.githubusercontent.com/100017195/223145333-bf3211e2-a595-4fb0-a6ab-6faaee06cc12.png)


## Wireframe Diagram
![wiafram](https://user-images.githubusercontent.com/100017195/223319608-d2a6ea07-90b5-477b-b0c3-d032cc49e098.jpeg)


## Flow Diagrams
to be added*3


## UML Diagram

![Project 3 UML](https://user-images.githubusercontent.com/100017195/223145631-091e178b-5bc9-420d-bb77-fa6085ae5e26.png)

## Test Plan
Add!!


## Record of Tasks
to be added! 


# Criteria C: Development


## Existing Tools

Add



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
