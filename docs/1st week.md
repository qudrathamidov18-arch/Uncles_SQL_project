# Week 1: Requirements Analysis - MallMaster

## 1. Introduction
The goal of this phase is to define the boundaries of the MallMaster system and identify the specific needs of shopping mall stakeholders.

MallMaster is a Shopping Mall Management System designed to manage products, stores, sales transactions, staff accounts, and reporting processes within a mall environment.

---

## 2. Functional Requirements (FR)
These requirements define the specific behaviors and functions of the system.

| ID | Requirement Name | Description |
|:---|:---|:---|
| **FR-01** | **Product Inventory Control** | The system must allow users to add, update, and delete product records (Product Name, Category, Brand, Price, Stock, Store Location). |
| **FR-02** | **Stock Level Monitoring** | The system must automatically highlight products that fall below the minimum stock threshold. |
| **FR-03** | **Sales & Billing Processing** | The system must process transactions via barcode scanning and calculate totals, discounts, and taxes. |
| **FR-04** | **Report Generation** | The system must generate daily, weekly, and monthly sales reports in PDF/Excel formats. |
| **FR-05** | **User & Store Management** | Admins must be able to create accounts for Store Managers and Cashiers and assign permissions. |

---

## 3. Non-Functional Requirements (NFR)
These define the quality attributes of the system.

- **Usability:** The interface should be intuitive enough for a cashier to learn within 30 minutes.
- **Performance:** All search queries must return results in less than 1 second.
- **Security:** Passwords must be encrypted using SHA-256.
- **Availability:** The system should be accessible 99.9% of the time.

---

## 4. User Personas

1. **Mall Admin (Owner):**
   Needs full visibility of total revenue, store performance, and overall mall operations.

2. **Store Manager:**
   Needs access to product inventory, sales tracking, and staff management tools.

3. **Cashier:**
   Needs a fast and reliable checkout system to process customer purchases efficiently.

4. **Inventory Supervisor:**
   Needs accurate stock data to prevent overstocking and stock shortages.

---

*Last Updated: February 12, 2026*
