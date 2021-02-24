Project: Lead Management System

Software and frameworks: 
1. Micosoft Visual Studio 2010 and higher
2. Asp. Net Framework must be install 
3. C# Programming Language
4. Mssql Server for database

step 1: Creation of DataBase and tables

Install Mssql server with windows authentication

create database name as LeadManagement
create table Account using following query
CREATE TABLE Account (
    Personid int IDENTITY(1,1) PRIMARY KEY,
    LastName varchar(50),
    FirstName varchar(50),
	Email varchar(50),
	Phone varchar(10),
	Empid varchar(50),
	Type varchar(10),
CONSTRAINT UK_Empid UNIQUE (Empid)
);

Insert a dummy admin account as

Insert into Account values('Admin','Admin','Admin@Admin.com','1234567890','1234','Admin');

in this query you can chnge all the fields as per your requirement but please not change the type field

Now create table Leads using following query

CREATE TABLE Leads (
   Leadid int IDENTITY(1,1) PRIMARY KEY,
    Name varchar(50),
    Organization varchar(50),
	Email varchar(50),
	Phone varchar(10),
	SourceLead varchar(50),
	CreatDate date,
	InteractionType varchar(50),
	DateTime datetime,
	Details nvarchar(max),
	Empid varchar(50),
	LeadScore varchar(5),
	 CONSTRAINT FK_Empid FOREIGN KEY (Empid)
    REFERENCES Account(Empid)
);

Step 2: Running the project using Visual Studio

Open the visual studio
 from file table click on open and select Web Site
select the project directory
open the web.config
and change the Data source name with your database server name
now click on debug 

