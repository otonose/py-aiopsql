# Asynchronous PostgreSQL Database Interaction
**An asynchronous Python database application that leverages SQLAlchemy ORM for seamless interaction with PostgreSQL databases.**

## Installation
To install this package, clone the repository and install the required dependencies:
```bash
git clone https://github.com/otonose/aiopsql.git
cd aiopsql
pip install -r requirements.txt
```

## Usage
### Configuration
```py
from async_db_postgresql import AsyncDatabase

db = AsyncDatabase(
    dialect="postgresql",
    user="yourusername",
    password="yourpassword",
    host="localhost",
    port=5432,
    database_name="yourdatabase"
)
```
### Basic Examples
#### Selecting Data
```py
from async_db_postgresql import db

async def fetch_data():
    results = await db.select(SomeModel, where_clause=SomeModel.column == 'value')
    print(results)
```
#### Inserting Data
```py
from async_db_postgresql import db

async def insert_data():
    await db.insert(SomeModel, values_params=[{"column1": "value1", "column2": "value2"}])
```
#### Updating Data
```py
from async_db_postgresql import db

async def update_data():
    await db.update(SomeModel, where_clause=SomeModel.id == 1, value_params={"column": "new_value"})
```
#### Deleting Data
```py
from async_db_postgresql import db

async def delete_data():
    await db.delete(SomeModel, where_clause=SomeModel.id == 1)
```
