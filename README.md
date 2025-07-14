# 🌌 Celestial Bodies, ⚽ World Cup & 🧪 Periodic Table Databases
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Bash](https://img.shields.io/badge/Bash-4EAA25?logo=gnu-bash&logoColor=white)](https://www.gnu.org/software/bash/)
[![Git](https://img.shields.io/badge/Git-F05032?logo=git&logoColor=white)](https://git-scm.com/)

This repository contains **three complete PostgreSQL database projects** developed as part of the [freeCodeCamp Relational Database Certification](https://www.freecodecamp.org/learn/relational-database/).  
Each project demonstrates database design, table relationships, Bash scripting, data insertion, and SQL querying.

---

## 📁 Projects Overview

### 1. 🌠 Celestial Bodies Database

A structured PostgreSQL database representing celestial bodies such as galaxies, stars, planets, and moons.

#### 🔧 Project Steps

1. Created a PostgreSQL database named `universe`
2. Designed tables: `galaxy`, `star`, `planet`, `moon`
3. Inserted meaningful data for each body
4. Set up primary and foreign keys to establish relationships
5. Exported the full schema and data in [`universe.sql`](./universe.sql)

#### 🧱 Table Rules

Each table includes:
- A primary key (`table_name_id`) that auto-increments
- A `name` column (`VARCHAR`)
- At least 3 columns including:
  - ≥ 2 columns marked `NOT NULL`
  - ≥ 1 `UNIQUE` column

#### 🔗 Relationships

- `star.galaxy_id → galaxy.galaxy_id`
- `planet.star_id → star.star_id`
- `moon.planet_id → planet.planet_id`

#### 📊 Data Requirements

- `galaxy` and `star`: at least 6 rows each
- `planet`: at least 12 rows
- `moon`: at least 20 rows
- Data types used: `INT`, `NUMERIC`, `TEXT`, `BOOLEAN`

#### 💡 Extra Columns Suggested

- `description` (`TEXT`)
- `has_life`, `is_spherical` (`BOOLEAN`)
- `age_in_millions_of_years` (`NUMERIC`)
- `distance_from_earth`, `planet_types`, etc.

#### 💾 Backup & Restore

```bash
# Backup
pg_dump -cC --inserts -U freecodecamp universe > universe.sql

# Restore
psql -U postgres < universe.sql
````

---

### 2. ⚽ World Cup Database

A database to explore and analyze World Cup results using SQL.

#### 📂 Files

* `insert_data.sh`: script to populate tables
* `queries.sh`: contains SQL queries for data extraction
* `expected_output.txt`: correct output expected by freeCodeCamp

#### 🏗️ Database Setup

* Created database `worldcup`
* Defined:

  * `teams(team_id, name)`
  * `games(game_id, year, round, winner_id, opponent_id, winner_goals, opponent_goals)`
* Loaded CSV data into `teams` and `games`

#### 🧪 Key Queries Implemented (in `queries.sh`)

* Total and average goals
* Rounding averages to 2 decimals
* Highest scoring team in a game
* List of teams per round
* Year and team name of all champions
* Teams starting with "Co"

Example format:

```bash
echo "$($PSQL "SELECT SUM(winner_goals) FROM games")"
```

Each command outputs exactly one line, in the order required by `expected_output.txt`.

#### ✅ Output Validation

After running:

```bash
bash queries.sh > output.txt
diff output.txt expected_output.txt
```

All outputs matched the expected file, including number formats.

---
## 📸 Screenshots 

<img width="327" alt="Screenshot 2025-07-06 at 00 10 46" src="https://github.com/user-attachments/assets/acb9e2c2-4dca-4f57-83dc-ff91509db9ab" />

### 3. 🧪 Periodic Table Database & Bash Script

A SQL + Bash project that models elements of the periodic table and allows lookup via a command-line interface.

#### 🧰 Tasks Completed

1. **Database Fixes & Enhancements**

   * Renamed columns:

     * `weight` → `atomic_mass`
     * `melting_point` → `melting_point_celsius`
     * `boiling_point` → `boiling_point_celsius`
   * Set `NOT NULL` and `UNIQUE` constraints on `symbol`, `name`, and other columns
   * Added foreign key relationships and created a `types` table
   * Inserted new elements: Fluorine (9) and Neon (10)
   * Deleted invalid element with atomic\_number 1000
   * Cleaned `atomic_mass` decimals and capitalized all `symbol` values

2. **Git & Repo Structure**

   * Repository initialized with `git init`
   * Five commits with messages formatted (`Initial commit`, `fix:`, `feat:`, etc.)
   * Files:

     * `element.sh`: Bash script to search elements
     * `periodic_table.sql`: SQL dump of the final database

3. **Bash Script Behavior**

   * `./element.sh`: prompts user for argument if missing
   * Input can be atomic number, symbol, or element name
   * Returns element details (name, symbol, type, mass, melting/boiling points)
   * Returns a friendly error if element not found

#### 🔍 Sample Output

```bash
$ ./element.sh 1
The element with atomic number 1 is Hydrogen (H). It's a nonmetal, with a mass of 1.008 amu. Hydrogen has a melting point of -259.1 celsius and a boiling point of -252.9 celsius.

$ ./element.sh Xx
I could not find that element in the database.
```

#### 🛠️ Useful Commands

```bash
# Connect to the database
psql --username=freecodecamp --dbname=periodic_table

# Export DB to SQL file
pg_dump -cC --inserts -U freecodecamp periodic_table > periodic_table.sql

# Re-import
psql -U postgres < periodic_table.sql
```

---

## 📌 Related Skills

* PostgreSQL
* SQL querying and aggregation
* Bash scripting
* ER modeling and normalization
* Data export/import via CLI

---
## 📸 Screenshots 
<img width="1420" height="294" alt="Screenshot 2025-07-14 at 10 47 35" src="https://github.com/user-attachments/assets/dbdf065d-7317-4f5d-9806-3f7c078258ce" />

---

## 🧠 Author

**By Saad Mehamdi**

These projects were built as part of my journey through the freeCodeCamp certification. They demonstrate hands-on skills in database design, Bash scripting, and SQL querying.


Feel free to explore the source files or fork the repo for your own learning.

---

## 🔗 License

This project is open-source and free to use under the [MIT License](LICENSE).


---
