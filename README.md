# Task-7-Creating-Views-# Task 7 – Creating Views

**Objective**  
Learn how to create and use SQL views to simplify complex queries and provide reusable, secure abstractions over the raw tables.

**Tools**  
- DB Browser for SQLite / MySQL Workbench

---

## ✅ Description

In this task we create SQL views over a library database to:
- simplify frequently used joins
- hide table complexity from end users
- promote reuse of common query logic
- add a layer of security by exposing only the required columns

---

## 🧭 Hints / Mini Guide

| Hint | Description |
|------|----------------------------------------------|
| 1    | Use `CREATE VIEW` with complex `SELECT` queries |
| 2    | Use views for **abstraction** and **security**  |

---

## 🛠️ View Definitions

> ⚠️ Replace `a.AuthorName` with the **actual name column** from your `Authors` table (e.g., `a.Name`)  
> (use `DESCRIBE Authors;` if needed)

**1. BooksWithAuthors**

```sql
CREATE VIEW BooksWithAuthors AS
SELECT b.BookID,
       b.Title,
       a.AuthorName,     -- or a.Name
       b.PublishedYear
FROM Books b
JOIN Authors a
  ON b.AuthorID = a.AuthorID;
