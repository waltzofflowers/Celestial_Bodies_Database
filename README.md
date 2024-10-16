# Universe Database

This project involves creating a relational database named **universe** that encompasses the structure of galaxies, stars, planets, and moons, with defined relationships and data types.

## Database Structure

### Tables

The universe database contains the following tables:

1. **galaxy**
2. **star**
3. **planet**
4. **moon**

### Table Definitions

#### 1. Galaxy Table

- **Table Name**: galaxy
- **Primary Key**: galaxy_id (automatically increments)
- **Columns**:
  - galaxy_id (INT, PRIMARY KEY, NOT NULL)
  - name (VARCHAR, UNIQUE, NOT NULL)
  - distance_km (NUMERIC, NOT NULL)
  - is_spiral (BOOLEAN, NOT NULL)
  - number_of_stars (INT, NOT NULL)

#### 2. Star Table

- **Table Name**: star
- **Primary Key**: star_id (automatically increments)
- **Foreign Key**: galaxy_id references galaxy(galaxy_id)
- **Columns**:
  - star_id (INT, PRIMARY KEY, NOT NULL)
  - name (VARCHAR, UNIQUE, NOT NULL)
  - temperature (INT, NOT NULL)
  - luminosity (NUMERIC, NOT NULL)
  - is_bright (BOOLEAN, NOT NULL)

#### 3. Planet Table

- **Table Name**: planet
- **Primary Key**: planet_id (automatically increments)
- **Foreign Key**: star_id references star(star_id)
- **Columns**:
  - planet_id (INT, PRIMARY KEY, NOT NULL)
  - name (VARCHAR, UNIQUE, NOT NULL)
  - diameter_km (INT, NOT NULL)
  - distance_from_star (NUMERIC, NOT NULL)
  - has_ring_system (BOOLEAN, NOT NULL)

#### 4. Moon Table

- **Table Name**: moon
- **Primary Key**: moon_id (automatically increments)
- **Foreign Key**: planet_id references planet(planet_id)
- **Columns**:
  - moon_id (INT, PRIMARY KEY, NOT NULL)
  - name (VARCHAR, UNIQUE, NOT NULL)
  - diameter_km (INT, NOT NULL)
  - distance_from_planet (NUMERIC, NOT NULL)
  - is_ice (BOOLEAN, NOT NULL)

## Data Requirements

- Each table will contain at least three rows.
- The **galaxy** and **star** tables will each have at least six rows.
- The **planet** table will have at least 12 rows.
- The **moon** table will have at least 20 rows.
- At least two columns in each table will not accept NULL values.
- Each table will have at least one column that is required to be UNIQUE.
- All columns named **name** will be of type **VARCHAR**.
- Each primary key column will follow the naming convention `table_name_id`.

## Database Connection

To connect to the database, use the following command:

\c universe


## Summary

This database design captures the hierarchical relationship between galaxies, stars, planets, and moons while enforcing data integrity through primary and foreign keys, diverse data types, and uniqueness constraints.
