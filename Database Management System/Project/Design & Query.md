### MediTracker: A Medicine Inventory Management System

#### Group: 08
#### Group Members:
| Name                  | ID        |
| --------------------- | --------- |
| MD. Arif Faysal Nayem | 011201194 |
| Mohaiminul Haque      | 011201072 |
| MD. Fazle Rabbi       | 011201280 |

### Project Features

#### Users
There will be mainly 2 types of users in the system.
1. Customer (Patient Table in the db)
2. Staff
Staff fall into 2 category-
1. Admin
2. Pharmacist
the categories will be defined in `role` field in the `employee` table.

#### SignUp and Login
Anyone can sign up as customer.
Only admins can add employees. Admins can also modify data of the employee e.g. salary, role.
Users can log in to the system with their email and password.

#### Drug Database
All known drug informations are stored in `drug` table. The quantity in stock for a specific drug is stored in `sroteddrug` table. the data of `storeddrug` table is auto generated as a new stock comes in and an employee creates a purchase invoice for the supplier. The data is updated whenever a sale or restock is made. 

#### Employee Features
An employee can create an invoice including multiple drugs.
Invoices can be 2 types- 
1. Purchase Invoie
2. Sale Invoice
Purchase invoice is generated when a new stock comes in to the store. 
Sale invoice is generated when a sale to the customer is made.
#### Customer Features
Customer can see a table containing all the drugs available in the store. User can search for a specific drug using drug name or it's manufacturer name. Customers can update their information e.g. name, address.

## Relational Schema
![[meditracker 2.png]]


### Queries Used in the Project

#### Signing Up
Checking if the given email already exists in the db.
```sql
SELECT * FROM patient  WHERE email='$email'
```
If the email does not exist, create the account by inserting data into patient table-
```sql
INSERT INTO patient (fname, lname, dob, bloodtype, gender, `password`,email)

        VALUES ('$fname', '$lname', '$dob', '$bloodtype', '$gender', '$password','$email')
```
#### Logging In
First we check if the account exists by checking the email the user providing is available or not in the db by executing  the previous query.
If exists, we check the password of the corresponding email by the following query-
```sql
INSERT INTO patient (fname, lname, dob, bloodtype, gender, `password`,email)

        VALUES ('$fname', '$lname', '$dob', '$bloodtype', '$gender', '$password','$email')
```
We use the similar steps for employee and admin login.
#### Updating profile information
Only customers can update their own information. In the update page, the data is auto filled in the input fields. We can achieve this by-
```sql
SELECT fname, lname, email, dob, gender, bloodtype

FROM patient

WHERE patientID = $id;
```
When they attempt to update their email, we check if the email is in the db excluding the user by executing-
```sql
SELECT COUNT(*) AS email_count

        FROM patient

        WHERE email = '$email'

        AND patientID <> '$id'
```
if not exists, we update their existing information by the following sql-
```sql
 UPDATE patient

    SET fname = '$fname',

        lname = '$lname',

        dob = '$dob',

        bloodtype = '$bloodtype',

        gender = '$gender',

        email = '$email'

    WHERE patientID = $id
```

#### Generating Purchase and sale invoice
**Purchase Invoice**
Purchase invoices can be saved as draft. So if an employee even logs out without saving an invoice, he can continue working with the invoice next time when he logs in. To create a invoice, 
First we check if a draft invoice is in the db corresponding to that employee available or not by-
```sql
SELECT *

        FROM invoice

        WHERE EmpID = $empID AND status = 'draft' AND type='purchase'
```
If a draft found corresponding to the employee, we create a new draft invoice for the user, and then show the data by the specific invoiceID-
```sql
SELECT o.drugID, d.drugName,d.scientificName,d.drugCategory,d.manufacturer,d.unitPrice, o.drugQuantity, o.drug_price_total

FROM onInvoice o

JOIN drug d ON o.drugID = d.drugID

WHERE o.InvoiceID = $invID;
```
If a draft is not found, we create a new draft for the customer and show the data(initially empty) by the above query.
If an employee adds drugs and quantities in the invoice, we add it to `oninvoice` table by-
```sql
INSERT INTO onInvoice (drugID, InvoiceID, drugQuantity, drug_price_total, batchNo, manufactureDate, expiryDate, date_of_entry)

            VALUES ($drugid, $invoiceID, $totalQuantity,$totalprice , 123, '2023-08-26', '2024-08-26', CURDATE());
```
The `oninvoice` table holds data for a specific drug and the quantity and the total price of a purchased drug.

>[!Note]
>The status of corresponding `InvoiceID` is still `draft`, as the user did not save the invoice. 

When an employee saves the invoice, we set the status from `draft` to `completed` by executing the following sql-
```sql
UPDATE invoice

        SET status = 'completed', newPrice=$totalprice

        WHERE invoiceID = $invID;
```

**Sale Invoice**
Sale invoice is generated when an employee sells some product to a customer.
We use the same queries for generating sale invoices for customer. The only difference is the `type` field of a invoice is set to `sale`
for sale invoices.
```sql
type='sale'
```

#### Showing Stored Drug Quantities
To do the job easier, we created a view using following command-
```sql
CREATE view stock AS

    SELECT

    sd.drugID,

    d.drugName,

    d.scientificName,

    d.drugCategory,

    d.manufacturer,

    d.unitPrice,

    SUM(sd.quantity) AS totalQuantity

FROM

    storedDrug sd

JOIN

    drug d ON sd.drugID = d.drugID

JOIN

    Invoice pi ON sd.InvoiceID = pi.InvoiceID

WHERE

    pi.type = 'purchase'

GROUP BY

    sd.drugID, d.drugName, d.scientificName, d.drugCategory, d.manufacturer, d.unitPrice;
```
Then we simply display the view table by-
```sql
SELECT * FROM stock
```
#### Searching the available drugs
Searching by name-
```sql
SELECT * FROM stock WHERE drugName LIKE '%$name%'
```
Searching by id-
```sql
SELECT * FROM stock WHERE drugID=$id
```

#### Updating stored drug quantities for each purchase/sale transaction
**Purchase**
we update the stored drug quantities only when an employee saves a invoice. We update the db by inserting data to stored drug table-
```sql
INSERT INTO storedDrug (InvoiceID, drugID, quantity)

        SELECT opi.InvoiceID, opi.drugID, opi.drugQuantity

        FROM onInvoice opi

        WHERE opi.InvoiceID = $invID;
```
**Sale**
After a sale, we decrease the available quantity of all the drugs in the invoice by-
```sql
UPDATE storedDrug
            SET quantity = quantity - $qty
            WHERE drugID = $id AND quantity >= $qty
            LIMIT 1
```

#### Viewing saved purchase/sale invoice 
View purchase/sale invoice for specific invoiceID-
```sql
SELECT o.drugID, d.drugName,d.scientificName,d.drugCategory,d.manufacturer,d.unitPrice, o.drugQuantity, o.drug_price_total

FROM onInvoice o

JOIN drug d ON o.drugID = d.drugID

WHERE o.purchaseInvoiceID = $purchaseinvID;
```
