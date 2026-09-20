

Roll No: 2k23/CSM/113	
Sprint 1 – System Architecture & Scope Definition
Introduction
Student Information
Field	Details
Course    :                         	
                                                    E-Commerce
Sprint  :	                                                   Sprint 1
Project Title  :	                                                   Tech Store – Online Electronics Shopping System
Assignment  :	SDLC Sprint 1

Project Deliverables
1. Target Audience & Market Focus  
Items	            Description
Primary Persona :	Retail consumers aged 18–45 who purchase electronic products online.
Core Pain Point :	Customers struggle to compare products, prices, and availability across multiple stores. They also want a secure and simple checkout experience.
Market Vertical :	Consumer Electronics
Target Products :	Smartphones, Laptops, Smart Watches, Headphones, Gaming Accessories, Computer Accessories

2. MVP Feature Scope
Category  	Feature	Description	Priority
Authentication   	                             User Registration  and   login                             	                                                   Users can register, log in, and securely authenticate using password hashing and  JWT                     .	High (MVP)
Catalog	                      Product Listing & Search	                                                   Browse products, search by name, and filter by category.	High (MVP)
Cart	    Shopping Cart	                                                   Add, update, and remove products from the shopping cart.	High (MVP)
Checkout	       Order Processing	         Place orders using a mock payment gateway and generate order records.	High (MVP)
Admin	                  Inventory Management	                                                   can add, edit, delete, and update product inventory.	Medium
User	 Order History	                                                   Users can view previous orders and their order status.	Medium

3. Tech Stack Selection & Justification
Component	Technology	Justification
Frontend	        React.js	                            React provides reusable UI components, fast rendering using the Virtual DOM, and a large developer community.
Backend	        Node.js + Express.js	                            Express is lightweight, scalable, and ideal for building REST APIs. Using JavaScript for both frontend and backend simplifies development.
Database	       PostgreSQL 	                            PostgreSQL is a reliable relational database with strong support for transactions, foreign keys, and data integrity.
		

4. Entity Detail
USERS
Attribute    	  Data Type	                      Key
id	INT	PK
full_name             	                                       VARCHAR	
email	                                       VARCHAR	
password_hash	                                      VARCHAR	
phone	                                      VARCHAR	
created_at                	                   TIMESTAMP	

CATEGORIES
Attribute	         Data Type	             Key
Id                          	            INT	             PK
category_ name	            VARCHAR	

PRODUCTS
Attribute	Data Type	Key
       id	INT	PK
Category _id	INT	FK
Product _name    	                   VARCHAR            R	
description	TEXT	
price	DECIMAL	
Stock _quantity	INT	
Image _  url	VARCHAR	

Order
Attribute	Data Type	        Key
id	       INT	        PK
user_ id	       INT	        FK
Total _amount	       DECIMAL	
Order _status	       VARCHAR	
Created _at	       TIMESTAMP	

ORDER_ITEMS
Attribute	            Data Type	            Key
id	             INT	           PK
order_ id	             INT	           FK
Product_ id	             INT	            FK
Quantity	            INT	
unit_ price    	            DECIMAL	

CART
Attribute	                     Data Type                     	        Key
id	                    INT	       PK
User _id	                    INT	       FK
Created _at	                    TIMESTAMP	

CART_ITEMS
Attribute	              Data Type	         Key
id	             INT	      PK
cart_  id	             INT	      FK
Product _id	             INT	      FK
quantity	             INT	

Entity Relationship Diagram (ERD)
 Erd   Diagram

USERS         ORDERS         : places
USERS         CART           : owns
CATEGORIES    PRODUCTS       : categorizes
ORDERS        ORDER ITEMS    : contains
PRODUCTS      ORDER ITEMS    :  ordered_ in
CART          CART  ITEMS    : includes
PRODUCTS      CART  ITEMS    : added_ to

USERS {
INT id     PK
VARCHAR   full_ name
VARCHAR   email
VARCHAR   password_ hash
VARCHAR   phone
TIMESTAMP created_ at
}

CATEGORIES {
INT id PK
VARCHAR category_ name
}

PRODUCTS {
INT        id PK
INT        category_ id FK
VARCHAR    product_ name
TEXT       description
DECIMAL    price
INT        stock_ quantity
VARCHAR    image_ url
}

ORDERS {
INT        id PK
INT        user_ id FK
DECIMAL    total_ amount
VARCHAR    order_ status
TIMESTAMP  created_ at
}

ORDER_ITEMS {
INT      id PK
INT      order_ id FK
INT      product_ id FK
INT      quantity
DECIMAL  unit_ price
}

CART {
INT          id PK
INT          user_ id FK
TIMESTAMP    created_ at
}

CART_ITEMS {
INT     id PK
INT     cart_ id FK
INT     product_ id FK
INT     quantity
}

Repository Structure
Folder/File	Purpose
ecommerce- [RollNo]/	Project Root
docs/SPRINT_1.md	Sprint 1 Documentation
frontend/	React Application
backend/	Express API
README.md	Project Overview

