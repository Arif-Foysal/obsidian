#dbms #project #uiu #Computer-Science 
[[Features to implement]]
[[topic presentation]]
[[Design & Query]]

# Pharmacy Management
[[Paper_No_2.pdf]]








SCHEMA- https://itsourcecode.com/uml/pharmacy-management-system-er-diagram/?expand_article=1
![[pharmacy-management-erd-01.png]]
Table: Customer

| **Field**    | **Description**   | **Type** | **Length** |
| ------------ | ----------------- | -------- | ---------- |
| cust_ID (PK) | Customer ID       | Int      | 11         |
| fname        | First Name        | Varchar  | 255        |
| lname        | Last Name         | Varchar  | 255        |
| gender       | Gender            | Int      | 11         |
| age          | Age               | Int      | 11         |
| contact_add  | Contact Address   | Int      | 11         |
| cust_email   | Customer Email    | Varchar  | 255        |
| cust_pass    | Customer Password | Varchar  | 255        |


Table: pharmacist

| **Field**    | **Description** | **Type** | **Length** |
| ------------ | --------------- | -------- | ---------- |
| phar_ID (PK) | Pharmacist ID   | Int      | 11         |
| fname        | First Name      | Varchar  | 255        |
| lname        | Last Name       | Varchar  | 255        |
| gender       | Gender          | Int      | 11         |
| age          | Age             | Int      | 11         |
| contact_add  | Contact Address | Int      | 11         |
| phar_email   | Email           | Varchar  | 255        |
| phar_pass    | Password        | Varchar  | 255        |

Table: Medicines

| **Field**    | ****Description**** | **Type** | **Length** |
| ------------ | ------------------- | -------- | ---------- |
| med_ID (PK)  | Medicine ID         | Int      | 11         |
| med_category | Medicine Category   | Varchar  | 30         |
| name         | Name                | Varchar  | 30         |
| description  | Description         | Varchar  | 30         |
| price        | Price               | Varchar  | 30         |

Table: Purchasing

| **Field**                 | ****Description**** | **Type** | **Length** |
| ------------------------- | ------------------- | -------- | ---------- |
| purchase_ID (PK)          | Purchase ID         | Int      | 11         |
| cust_ID (FK) ref Customer | Customer ID         | Int      | 11         |
| med_ID (FK) ref Medicines | Medicine ID         | Int      | 11         |
| amount                    | Amount              | Varchar  | 255        |
| date                      | Date                | Date     |            |
| 
 
Table: Sales

| **Field**                       | ****Description**** | **Type** | **Length** |
| ------------------------------- | ------------------- | -------- | ---------- |
| sales_ID (PK)                   | Sales ID            | Int      | 11         |
| phar_ID (FK) ref Pharmacist     | Pharmacist ID       | Int      | 11         |
| cust_ID (FK) ref Customer       | Customer ID         | Int      | 11         |
| med_ID (FK) ref Medicines       | Medicine ID         | Int      | 11         |
| count                           | Medicine Count      | Int      | 11         |
| purchase_ID (FK) ref Purchasing | Purchase ID         | int      | 11         |
| date                            | Date of Sale        | Date     |            |
| total_amount                    | Total Amount        | Varchar  | 255        |
| 

Table: Reports

| **Field**                       | ****Description**** | **Type** | **Length** |
| ------------------------------- | ------------------- | -------- | ---------- |
| report_ID (PK)                  | Report ID           | Int      | 11         |
| purchase_ID (FK) ref Purchasing | Purchase ID         | Int      | 11         |
| sales_ID (FK) ref Sales         | Sales Id            | Int      | 11         |
| cust_ID (FK) ref Customer       | Customer ID         | Int      | 11         |
| date                            | Date of Report      | Date     |            |
| 

