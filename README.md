# 🛎️ SQL Triggers Practice – Lucky Shrub Database

## 🚀 Project Overview
This project demonstrates the use of **SQL triggers** in the **Lucky Shrub** landscaping & garden supply business database.  
Triggers are automated routines that fire in response to database events (`INSERT`, `UPDATE`, `DELETE`).  
Here, triggers are applied to the `Products` table to enforce **data integrity** and send **automated notifications** to the `Notifications` table whenever business rules are violated.

---

## 📊 Dataset
The database includes two core tables:

- **Products** → Stores product details like `ProductID`, `ProductName`, `BuyPrice`, `SellPrice`, and `NumberOfItems`.  
- **Notifications** → Stores automatically generated alerts when triggers fire.

**Snippet of Products Table:**
ProductID	ProductName	BuyPrice	SellPrice	NumberOfItems
P1	Artificial grass bag	40.00	50.00	100
P2	Wood panels	15.00	20.00	250
P3	Patio slates	35.00	40.00	60

---

## 🧑‍💻 SQL Tasks

### ✅ Task 1: Insert Trigger
**Trigger Name:** `ProductSellPriceInsertCheck`  
- Fires **AFTER INSERT** on `Products`.  
- Checks if `SellPrice <= BuyPrice`.  
- If true → adds a notification for the sales department.  

**Expected Output Example (Notifications table):**
NotificationID	Notification	DateTime
1	A SellPrice same or less than the BuyPrice was inserted for P7	2025-08-26 12:34:56

---

### ✅ Task 2: Update Trigger
**Trigger Name:** `ProductSellPriceUpdateCheck`  
- Fires **AFTER UPDATE** on `Products`.  
- Validates that updated products do not have a `SellPrice <= BuyPrice`.  
- If violated → inserts a warning notification.  

**Expected Output Example:**
NotificationID	Notification	DateTime
2	P3 was updated with a SellPrice of 30 which is the same or less...	2025-08-26 12:40:11

---

### ✅ Task 3: Delete Trigger
**Trigger Name:** `NotifyProductDelete`  
- Fires **AFTER DELETE** on `Products`.  
- Inserts a notification confirming deletion of a product.  

**Expected Output Example:**
NotificationID	Notification	DateTime
3	The product with a ProductID P2 was deleted	2025-08-26 12:45:21

---

## 📌 Why Does This Matter?
- Helps **maintain business rules** directly inside the database.  
- Prevents incorrect product pricing (`SellPrice < BuyPrice`).  
- Provides an **audit trail** for product modifications and deletions.  
- Improves **data reliability** for the Lucky Shrub sales team.  

---

## 🛠️ SQL Techniques Used
- `CREATE TRIGGER` with `AFTER INSERT`, `AFTER UPDATE`, `AFTER DELETE`  
- Conditional logic with `IF ... THEN`  
- Using `NEW` and `OLD` references inside triggers  
- `NOW()` for timestamp logging  
- `CONCAT()` for dynamic notification messages  

---

## 📬 Contact
If you have any questions about this project, feel free to reach out:  
- [LinkedIn](https://www.linkedin.com/in/dominik-vyleta-mba-a566511b2/)  
- 📧 vyleta.dom@gmail.com
