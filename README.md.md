# Power BI Week 2 — Data Modeling & Relationships

## Project Overview
This repository contains the **Week 2: Data Modeling & Relationships** Power BI assignment. It implements a **Star Schema** data model connecting a central `Orders` fact table to dimension tables (`Customers`, `Products`, `Regions`, and a DAX-generated `Calendar` table).

---

## Star Schema Data Model & Relationships

```text
   +-----------------+          +-----------------+
   |    Customers    |          |    Products     |
   |  (Customer ID)  |          |  (Product ID)   |
   +--------+--------+          +--------+--------+
            | 1                          | 1
            |                            |
            | *                          | *
            +------------+---------------+
                         |
                         v
              +---------------------+
              |       Orders        |  <--- Fact Table
              |   (Order Date, ID)  |
              +----------+----------+
                         ^
            +------------+---------------+
            | *                          | *
            |                            |
            | 1                          | 1
   +--------+--------+          +--------+--------+
   |     Regions     |          |    Calendar     |
   |   (Region ID)   |          |     (Date)      |
   +-----------------+          +-----------------+