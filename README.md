---

# 🌌 Celestial Bodies Database

This project is part of the [freeCodeCamp Relational Database certification](https://www.freecodecamp.org/learn/relational-database/build-a-celestial-bodies-database-project/build-a-celestial-bodies-database) and involves building a structured PostgreSQL database about celestial bodies in the universe.

---

## 🔧 Project Overview

You can follow all terminal commands and steps in the [`solution.txt`](./solution.txt) file. The work was completed in the following steps:

1. **Create the database** and connect to it using `psql`.
2. **Create the required tables** (`galaxy`, `star`, `planet`, `moon`) following the given schema rules.
3. **Insert data** according to specified requirements.
4. **Assign primary and foreign keys** to define relationships.
5. **Export the final solution** into a compact file: [`universe.sql`](./universe.sql).

---

## 🧪 How to Use

Start by logging into PostgreSQL with:

```bash
psql --username=freecodecamp --dbname=postgres
```

Then create and connect to the database:

```sql
\c universe
```

Your goal is to pass all the tests provided on freeCodeCamp. The key requirements are:

### 🗂️ Tables

* Create tables: `galaxy`, `star`, `planet`, `moon`
* Each table must have:

  * A primary key (`table_name_id`) that auto-increments
  * A `name` column (`VARCHAR`)
  * At least **3 columns**, including:

    * At least **2 columns** that are `NOT NULL`
    * At least **1 column** that is `UNIQUE`

### 📊 Data Types

Use a variety of SQL data types:

* `INT` (in at least two non-key columns)
* `NUMERIC` (at least once)
* `TEXT` (at least once)
* `BOOLEAN` (in at least two columns)

### 🔗 Relationships

* Each `star` must reference a `galaxy`
* Each `planet` must reference a `star`
* Each `moon` must reference a `planet`

### 📈 Minimum Data

* `galaxy` and `star`: at least **6 rows** each
* `planet`: at least **12 rows**
* `moon`: at least **20 rows**

---

## 💾 Saving and Restoring Your Work

Before exiting your virtual machine, you can **save your progress** using:

```bash
pg_dump -cC --inserts -U freecodecamp universe > universe.sql
```

To restore it later:

```bash
psql -U postgres < universe.sql
```

> 💡 Tip: Run this command in the **bash terminal**, not in `psql`.

---

## 💡 Suggested Extra Columns

Here are some ideas for additional columns:

* `description` (TEXT)
* `has_life`, `is_spherical` (BOOLEAN)
* `age_in_millions_of_years` (NUMERIC)
* `planet_types`, `galaxy_types` (TEXT)
* `distance_from_earth` (NUMERIC)

---

## ✅ Final Submission

Once all tests pass:

1. Export your database with `pg_dump`
2. Upload your `universe.sql` to a **public GitHub repo**
3. Submit the link on freeCodeCamp to complete the project

---
