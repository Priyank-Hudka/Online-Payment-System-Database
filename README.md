# Online Payment System Database

## Author
**Priyank Hudka**

## 📌 Objective
The goal of this project is to design and implement a **secure and user-friendly online payment system database** to support an E-Commerce platform. This system efficiently manages users, products, transactions, orders, reviews, and refunds using a structured relational schema.

---

## 📄 Description

This database design supports the following key functionalities:

- **User Registration**: Stores user information such as name, email, age, and credentials.
- **Transaction Handling**: Tracks transaction details including payment methods and statuses.
- **Order Management**: Captures order status, shipping info, coupon applications, and detailed breakdown of costs.
- **Product Catalog**: Maintains product descriptions, availability, pricing, and stock levels.
- **Admin Control**: Admins can monitor transaction and order activity.
- **Review System**: Allows users to review and rate purchased products.
- **Refund Module**: Manages refund details including reason, date, and amount.

---

## 🗃️ Key Tables & Relationships

- `USER_INFO`: User credentials and profile.
- `TRANSACTIONS`: Payment transactions with timestamps.
- `ORDER_ITEM`: Orders placed by users, connected to fees, coupons, and shipping.
- `PRODUCT`: Items listed on the platform.
- `REVIEW`: User feedback associated with products and orders.
- `RETURN_ITEM`: Refund information tied to specific transactions.
- `ADMIN_MAIN`: Admins linked to the transactions they supervise.

---

## 🔑 Functional Dependencies (Minimal Set)

- `UserID → Full Name, Email, Phone, ...`
- `TransactionID → Time, Amount, Payment Method, Refunds, OrderID`
- `OrderID → Order Status, ShippingID, FeeID, CouponID, Total`
- `ShippingID → Address Info`
- `FeeID → GST, Delivery Fee, Order Total`
- `CouponID → Code, Discount Type, Discount Amount`
- `{OrderID, ProductID} → Quantity, Total Price`
- `ProductID → Product Details`
- `{OrderID, ProductID, ReviewID} → Rating, Feedback`

---

## 🧩 ER Diagram and Schema

- The ER diagram defines the relationships between users, products, orders, and transactions.
- All entities are implemented in PostgreSQL with proper primary and foreign keys.

---

## 🧱 Database Setup (DDL)

The schema is initialized using `CREATE SCHEMA Online_Payment_System;` and includes detailed table definitions with appropriate constraints, such as:

```sql
CREATE TABLE USER_INFO (
  user_id VARCHAR(30) PRIMARY KEY,
  name1 VARCHAR(30),
  email VARCHAR(30),
  user_name VARCHAR(30) NOT NULL UNIQUE,
  passwd VARCHAR(30),
  phone_no INTEGER,
  age INTEGER
);
