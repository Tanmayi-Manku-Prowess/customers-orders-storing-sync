# customers-orders-storing-sync
This mule project uses Database and Salesforce resources to store data after transforming the data based on required conditions

## ⚙️ Technologies Used
- **MuleSoft**
- **FreeDB Cloud Database**
- **Salesforce**
- **SMTP**
- **Postman**
## 🏗️ Database Setup Instructions

### 1️⃣ Database Tables creation commands
1. Cloud Database Used: https://freedb.tech/dashboard/
2. Connect to the database with created user
   
```sql

CREATE TABLE orders (
  orderId VARCHAR(20) PRIMARY KEY,
  customerId VARCHAR(20),
  orderDate DATE,
  totalAmount DECIMAL(10,2)
);

CREATE TABLE products_summary (
  productId VARCHAR(20),
  productName VARCHAR(100),
  totalPrice DECIMAL(10,2)
);


```

## Key Features
- Transform customers data using DataWeave.
- Updates data to Salesforce and Database accordingly.
- Sends email notification with simple sentance as body of the email
-   for successful implementation of data sync sends email as `Customers and orders data successfully inserted into Salesforce and database`.
-   for failed implementation, sends email as `Data insertion to Cloud Database and Salesforce failed. Please check error logs`.
