# Football Ticket Booking System - Database Design & SQL Queries

A relational database system designed to manage football match ticket sales, user roles, stadium seating allocation, and transaction logs. This project covers Entity-Relationship Diagram (ERD) architecture, normalized table constraints, and intermediate-to-advanced SQL queries.

## 📌 Features & Business Logic
- **User Management:** Tracks platform administrative staff (`Ticket Manager`) and customers (`Football Fan`).
- **Match Logistics:** Catalogs tournament fixtures, stadium availability status (`Available`, `Selling Fast`, `Sold Out`, `Postponed`), and base pricing.
- **Transactional Bookings:** Handles individual ticket purchases mapping a specific user to a match with exact seat allocation and multi-state payment tracking.

---

## 🗺️ Database Architecture (ERD)

The database enforces relational integrity using **Crow's Foot Notation** with the following cardinality rules:
- **One-to-Many (`Users` → `Bookings`):** A single football fan can book multiple match tickets throughout the season.
- **Many-to-One (`Bookings` → `Matches`):** A high-profile derby match can be linked to thousands of individual booking records.
- **Data Integrity:** Cascading deletes (`ON DELETE CASCADE`) are enforced on all foreign keys to maintain systematic synchronization.

> 🔗 **ERD Tool Link:** [https://drive.google.com/file/d/1DwuNhNn9Yjz0y8SKQ3sNbvkAWlCTVsEu/view?usp=sharing]

---

## 🚀 Database Schema & DDL

The database configuration utilizes strong data types, named primary/foreign keys, and data validation rules using `CHECK` constraints.

### Relational Tables Structure:
1. **`Users` Table:** Enforces unique emails and strict role criteria.
2. **`Matches` Table:** Validates non-negative ticket pricing and standardized match statuses.
3. **`Bookings` Table:** Maps relational composite logic ensuring structural constraints.

---

## 🔍 SQL Analytics Queries Implemented

The `QUERY.sql` script contains advanced query patterns targeting real-world operations:

*   **Query 1 (Filtering):** Retrieves conditional tournament information based on category and current availability state.
*   **Query 2 (Pattern Matching):** Features case-insensitive search logic using string normalization (`LOWER` and `LIKE`).
*   **Query 3 (Null Handling):** Uses `COALESCE` for conditional fallback values on missing relational states.
*   **Query 4 (Data Aggregation via INNER JOIN):** Reconstructs relational rows into complete analytical invoices.
*   **Query 5 (Comprehensive Reporting via LEFT JOIN):** Audits comprehensive user patterns, including inactive users.
*   **Query 6 (Subqueries):** Uses dynamic inline subqueries to isolate records exceeding calculated averages.
*   **Query 7 (Pagination & Optimization):** Implements server-side pagination utilizing `LIMIT` and `OFFSET` bounds.

---

## 🛠️ How to Run Locally

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/football-ticket-booking-db.git](https://github.com/your-username/football-ticket-booking-db.git)
   cd football-ticket-booking-db