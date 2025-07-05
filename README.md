
# 🌌 Celestial Bodies & ⚽ World Cup Databases

This repository contains two complete PostgreSQL database projects developed as part of the [freeCodeCamp Relational Database Certification](https://www.freecodecamp.org/learn/relational-database/). Each project demonstrates database design, table relationships, data insertion, and SQL query writing.

---

## 📁 Projects Overview

### 1. 🌠 Celestial Bodies Database

A structured PostgreSQL database representing celestial bodies such as galaxies, stars, planets, and moons.

#### 🔧 Project Steps

All commands are available in [`solution.txt`](./solution.txt):

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

## 🧠 Author

**By Saad Mehamdi**

These projects were built as part of my journey through the freeCodeCamp certification. They reflect practical SQL skills, including schema design, data normalization, and query optimization.

Feel free to explore the source files or fork the repo for your own learning.

---

## 📌 Related Skills

* PostgreSQL
* SQL querying and aggregation
* Bash scripting
* ER modeling and normalization
* Data export/import via CLI

---

## 📸 Screenshots 

<img width="327" alt="Screenshot 2025-07-06 at 00 10 46" src="https://github.com/user-attachments/assets/acb9e2c2-4dca-4f57-83dc-ff91509db9ab" />

---

## 🔗 License

This project is open-source and free to use under the [MIT License](LICENSE).


---
