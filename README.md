# Indexing
Indexing in database

In **SQL**, an **Index** is used to **speed up the retrieval of data from a table**. It works like the **index of a book** 📚 — instead of scanning every page, the database quickly finds the required data.

---

## 1. What is an Index in SQL?

An **index** is a **database object** that improves the **performance of SELECT queries** by allowing the database to find rows faster.

Without index → Database scans **entire table (Full Table Scan)**
With index → Database directly finds the **required rows**

Example table:

| id | name | city      |
| -- | ---- | --------- |
| 1  | Ravi | Delhi     |
| 2  | Amit | Mumbai    |
| 3  | Neha | Bangalore |

If we search:

```sql
SELECT * FROM users WHERE name = 'Neha';
```

Without index → Database checks **every row**
With index → Database quickly finds **Neha**

---

# 2. Create Index

Syntax:

```sql
CREATE INDEX index_name
ON table_name(column_name);
```

Example:

```sql
CREATE INDEX idx_name
ON users(name);
```

Now searching by **name** becomes faster.

---

# 3. Create Unique Index

A **unique index** ensures that values in a column are unique.

```sql
CREATE UNIQUE INDEX idx_email
ON users(email);
```

Example: No two users can have the same email.

---

# 4. Composite Index (Multiple Columns)

```sql
CREATE INDEX idx_name_city
ON users(name, city);
```

Used when queries use multiple columns.

Example:

```sql
SELECT * FROM users
WHERE name = 'Neha' AND city = 'Bangalore';
```

---

# 5. Drop Index

```sql
DROP INDEX idx_name;
```

---

# 6. Advantages of Index

✅ Faster data retrieval
✅ Improves SELECT query performance
✅ Efficient searching, sorting, filtering

---

# 7. Disadvantages of Index

❌ Takes extra storage
❌ Slows down **INSERT, UPDATE, DELETE** operations because index must also update

---

# 8. Example Real Industry Case

Table: `orders`

```sql
SELECT * FROM orders
WHERE order_id = 1023;
```

If `order_id` has an index, database finds it **very fast**.

---

✅ **Interview Definition (Best Answer):**

> An index in SQL is a database object used to improve the speed of data retrieval operations on a table. It works like a book index and helps the database locate rows quickly without scanning the entire table.

---

If you want, I can also explain:

* **Clustered vs Non-Clustered Index** (very important for interviews)
* **How indexes work internally (B-Tree)**
* **When NOT to use index**
* **Top 10 SQL indexing interview questions** 🚀

