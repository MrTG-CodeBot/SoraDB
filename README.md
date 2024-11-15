# SoraDBlite

[![Python Versions](https://img.shields.io/pypi/pyversions/pymongo)](https://pypi.org/project/pymongo)  [![SoraDBlite latest Version](https://img.shields.io/pypi/v/SoraDBlite)](https://pypi.org/project/SoraDBlite)


## 🌐 contact me:

[![Telegram](https://img.shields.io/badge/Telegram-blue?logo=telegram)](https://t.me/MrTG_Coder)

## About

*SoraDBlite* is a Python class designed to simplify interactions with MongoDB databases. And the operation are similar to the mongodb, and it is easy to understand. It is just a lite version of mongodb. It providing the interface for performing essential CRUD (Create, Read, Update, Delete) operations. With SoraDBlite, developers can easily manage and manipulate data within their MongoDB collections, making it ideal for both simple and complex database tasks.

*SoraDefaultDB* is a easy Database Testing. *SoraDefaultDB* is a tool for designed to test the functionality of *SoraDBlite*. You don't need to input MongoDB URI and password, just specify the collection name. . After testing, drop the collections you created to ensure they are removed from the database.

### Key Features:
◘ *Easy Connection Management*: Simplifies connecting to MongoDB databases.

◘ CRUD Operations: Perform basic CRUD operations effortlessly.

* Insert single or multiple documents.

* Find single or multiple documents with flexible query options.

* Update single or multiple documents.

* Delete single or multiple documents.

* Collection Management: Drop collections with ease.

◘ Sorting Capabilities: Sort documents by specified fields in ascending or descending order.

◘ *Error Handling*: Custom exceptions for better error.

◘ *Sora AI integration*: for error detection and solution.


## How to get db url and collection

### Video Tutorial
For a detailed video tutorial, check out this link: [video](https://youtu.be/mD9veNL7KoE?si=nTb5GbfDINNy5TCQ)

## Differences Between `pymongo` and `SoraDBlite`

| Feature            | pymongo                                           | SoraDBlite                                       |
|--------------------|---------------------------------------------------|----------------------------------------------|
| **Library Type**   | Low-level MongoDB driver                          | High-level wrapper for `pymongo`             |
| **Usage**          | Directly interacts with MongoDB                   | Simplified methods for common operations     |
| **Flexibility**    | Complete control over MongoDB operations          | Abstracts complexity, less granular control  |
| **Error Handling** | Developers implement their own error handling     | Built-in error handling                      |
| **Code Complexity**| More complex and verbose                          | User-friendly and concise                    |


## Important 
<details>
<summary>𝐈𝐦𝐩𝐨𝐫𝐭𝐚𝐧𝐭</summary>
Use SoraDefaultDB to quickly test your database setup with just a collection name. And in your main projects, use SoraDBlite to leverage its full range of features and optimizations."

If you create a collection using SoraDefaultDB, remember to drop it after testing to avoid unnecessary data accumulation. Verify that the collection has been removed by checking the database.

```python
import SoraDBlite
from SoraDBlite import SoraDefaultDB, SoraDBLiteError, is_collection_available

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)
# your code
db.drop_collection("your_db_collection_name")

is_collection_available(db_collection) # Pass the db_collection_name only

```
</details>


## Installation

Make sure you have `SoraDBlite` installed. You can install it using pip if you haven't already:

```sh
pip install SoraDBlite
```
# Usage of SoraDBlite
<details>
<summary>𝗦𝗼𝗿𝗮𝗗𝗕𝗹𝗶𝘁𝗲</summary>

## Importing the Library

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError, is_collection_available 
```

## Checking the collection name is available or not

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError, is_collection_available
db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

is_collection_available(db_url, db_password, db_collection) # Pass the db_url, db_pass, db_collection_name

```

## Importing the Exception class

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()

try:
   db.connect(db_url, db_password, db_collection)
except SoraDBLiteError as e:
   print(e)
```

## Importing the Exception Class and Using sora_ai()

Sora_ai() will given how to solve the error/ give the solution.

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()

try:
   db.connect(db_url, db_password, db_collection)
except SoraDBLiteError as e:
   print(e)
   db.sora_ai(e) # Pass the error message to sora_ai() for a solution
```

## Connecting to the Database

To connect to your MongoDB database, use the `connect` method:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)
```

## Inserting Documents

Insert a single document:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

document = {"name": "Alice", "age": 30, "city": "New York"}
inserted_id = db.insert_one(document)
print("Inserted document with ID:", inserted_id)
```

Insert multiple documents:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

documents = [
    {"name": "Alice", "age": 30, "city": "New York"},
    {"name": "Bob", "age": 25, "city": "Los Angeles"},
    {"name": "Charlie", "age": 35, "city": "Chicago"}
]
inserted_ids = db.insert_many(documents)
print("Inserted document IDs:", inserted_ids)
```

## Finding Documents

Find a single document:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

query = {"name": "Alice"}
result = db.find_one(query)
print("Found document:", result)
```

Find multiple documents:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

query = {"age": {"$gt": 25}}
results = db.find_many(query)
print("Found documents:", results)
```

## Updating Documents

Update a single document:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

filter = {"name": "Alice"}
update = {"$set": {"city": "Los Angeles"}}
updated_count = db.update_one(filter, update)
print("Updated documents:", updated_count)
```

Update multiple documents:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

filter = {"city": "New York"}
update = {"$set": {"city": "New York City"}}
updated_count = db.update_many(filter, update)
print("Updated documents:", updated_count)
```

## Deleting Documents

Delete a single document:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

filter = {"name": "Alice"}
deleted_count = db.delete_one(filter)
print("Deleted documents:", deleted_count)
```

Delete multiple documents:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

filter = {"age": {"$lt": 25}}
deleted_count = db.delete_many(filter)
print("Deleted documents:", deleted_count)
```

## Sorting Documents

Sort documents by a field in ascending order:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

results = db.sort_by("age", True)
print("Sorted by age (ascending):", results)
```

Sort documents by a field in descending order:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

results = db.sort_by("name", False)
print("Sorted by name (descending):", results)
```

## Dropping a Collection

To drop a collection, use the drop_collection method:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError, is_collection_available

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

db.drop_collection("your_db_collection_name")

is_collection_available(db_url, db_password, db_collection) # Pass the db_url, db_pass, db_collection_name

```

## counting the documents

Get the count of the documents:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

count = db.count({"name":"Alice"})
print(count)
```

##  Fetch all values 

Fetch all values for a specific key name:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

d=db.fetch_values_by_key("name")
print(d)
```

##  Get the version

Get the version of pymongo and soradb:

```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

db.version()
```

## Example Code
```python
import SoraDBlite
from SoraDBlite import SoraDBlite, SoraDBLiteError

db_url = "your_mongodb_url"
db_password = "your_db_password"
db_collection = "your_db_collection_name"

db = SoraDBlite()
db.connect(db_url, db_password, db_collection)

# Insert a document
document = {"name": "Alice", "age": 30, "city": "New York"}
inserted_id = db.insert_one(document)
print("Inserted document with ID:", inserted_id)

# Find a document
query = {"name": "Alice"}
result = db.find_one(query)
print("Found document:", result)

# Find multiple documents
query = {"age": {"$gt": 25}}
results = db.find_many(query)
print("Found documents:", results)

# Update a document
filter = {"name": "Alice"}
update = {"$set": {"city": "Los Angeles"}}
updated_count = db.update_one(filter, update)
print("Updated documents:", updated_count)

# Delete a document
filter = {"name": "Alice"}
deleted_count = db.delete_one(filter)
print("Deleted documents:", deleted_count)

# Insert multiple documents
documents = [
    {"name": "Alice", "age": 30, "city": "New York"},
    {"name": "Bob", "age": 25, "city": "Los Angeles"},
    {"name": "Charlie", "age": 35, "city": "Chicago"}
]
inserted_ids = db.insert_many(documents)
print("Inserted document IDs:", inserted_ids)

# Find multiple documents
query = {"age": {"$gt": 25}}
results = db.find_many(query)
print("Found documents:", results)

# Update multiple documents
filter = {"city": "New York"}
update = {"$set": {"city": "New York City"}}
updated_count = db.update_many(filter, update)
print("Updated documents:", updated_count)

# Delete multiple documents
filter = {"age": {"$lt": 25}}
deleted_count = db.delete_many(filter)
print("Deleted documents:", deleted_count)

# Sort documents by age
results = db.sort_by("age", True)
print("Sorted by age (ascending):", results)

# Sort documents by name
results = db.sort_by("name", False)
print("Sorted by name (descending):", results)

# Count the documents
count = db.count({"name":"Alice"})
print(count)

# Fetch all values for a specific key
d = db.fetch_values_by_key("name")
print(d)

#Get the version of pymongo and soradb
db.version()

# Drop a collection
db.drop_collection(db_collection)

# Check the collection is dropped or not
is_collection_available(db_url, db_password, db_collection) # Pass the db_url, db_pass, db_collection_name

```
</details>


# Usage of SoraDefaultDB
<details>
<summary>𝗦𝗼𝗿𝗮𝗗𝗲𝗳𝗮𝘂𝗹𝘁𝗗𝗕</summary>

## Importing the Library

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError, is_collection_available
```

## Checking the collection name

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError, is_collection_available

db_collection = "your_db_collection_name"

is_collection_available(db_collection) # Pass the db_collection_name only 

```

## Importing the Exception class

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

try:
   db.connect(db_collection)
except SoraDBLiteError as e:
   print(e)
```

## Importing the Exception Class and Using sora_ai()

Sora_ai() will given how to solve the error/ give the solution.

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

try:
   db.connect(db_collection)
except SoraDBLiteError as e:
   print(e)
   db.sora_ai(e) # Pass the error message to sora_ai() for a solution
```

## Connecting to the Database

To connect to your MongoDB database, use the `connect` method:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)
```

## Inserting Documents

Insert a single document:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)

document = {"name": "Alice", "age": 30, "city": "New York"}
inserted_id = db.insert_one(document)
print("Inserted document with ID:", inserted_id)
```

Insert multiple documents:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)

documents = [
    {"name": "Alice", "age": 30, "city": "New York"},
    {"name": "Bob", "age": 25, "city": "Los Angeles"},
    {"name": "Charlie", "age": 35, "city": "Chicago"}
]
inserted_ids = db.insert_many(documents)
print("Inserted document IDs:", inserted_ids)
```

## Finding Documents

Find a single document:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)

query = {"name": "Alice"}
result = db.find_one(query)
print("Found document:", result)
```

Find multiple documents:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)

query = {"age": {"$gt": 25}}
results = db.find_many(query)
print("Found documents:", results)
```

## Updating Documents

Update a single document:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)

filter = {"name": "Alice"}
update = {"$set": {"city": "Los Angeles"}}
updated_count = db.update_one(filter, update)
print("Updated documents:", updated_count)
```

Update multiple documents:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)
filter = {"city": "New York"}
update = {"$set": {"city": "New York City"}}
updated_count = db.update_many(filter, update)
print("Updated documents:", updated_count)
```

## Deleting Documents

Delete a single document:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)
filter = {"name": "Alice"}
deleted_count = db.delete_one(filter)
print("Deleted documents:", deleted_count)
```

Delete multiple documents:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)

filter = {"age": {"$lt": 25}}
deleted_count = db.delete_many(filter)
print("Deleted documents:", deleted_count)
```

## Sorting Documents

Sort documents by a field in ascending order:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)
results = db.sort_by("age", True)
print("Sorted by age (ascending):", results)
```

Sort documents by a field in descending order:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)

results = db.sort_by("name", False)
print("Sorted by name (descending):", results)
```

## Dropping a Collection

To drop a collection, use the drop_collection method:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError, is_collection_available

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)

db.drop_collection("your_db_collection_name")

is_collection_available(db_collection) # Pass the db_collection_name only

```

## counting the documents

Get the count of the documents:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)

count = db.count({"name":"Alice"})
print(count)
```

##  Fetch all values 

Fetch all values for a specific key name:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)

d=db.fetch_values_by_key("name")
print(d)
```

##  Get the version

Get the version of pymongo and soradb:

```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)

db.version()
```

## Example Code
```python
import SoraDefaultDB
from SoraDefaultDB import SoraDefaultDB, SoraDBLiteError, is_collection_available

db_collection = "your_db_collection_name"

db = SoraDefaultDB()

db.connect(db_collection)

# Insert a document
document = {"name": "Alice", "age": 30, "city": "New York"}
inserted_id = db.insert_one(document)
print("Inserted document with ID:", inserted_id)

# Find a document
query = {"name": "Alice"}
result = db.find_one(query)
print("Found document:", result)

# Find multiple documents
query = {"age": {"$gt": 25}}
results = db.find_many(query)
print("Found documents:", results)

# Update a document
filter = {"name": "Alice"}
update = {"$set": {"city": "Los Angeles"}}
updated_count = db.update_one(filter, update)
print("Updated documents:", updated_count)

# Delete a document
filter = {"name": "Alice"}
deleted_count = db.delete_one(filter)
print("Deleted documents:", deleted_count)

# Insert multiple documents
documents = [
    {"name": "Alice", "age": 30, "city": "New York"},
    {"name": "Bob", "age": 25, "city": "Los Angeles"},
    {"name": "Charlie", "age": 35, "city": "Chicago"}
]
inserted_ids = db.insert_many(documents)
print("Inserted document IDs:", inserted_ids)

# Find multiple documents
query = {"age": {"$gt": 25}}
results = db.find_many(query)
print("Found documents:", results)

# Update multiple documents
filter = {"city": "New York"}
update = {"$set": {"city": "New York City"}}
updated_count = db.update_many(filter, update)
print("Updated documents:", updated_count)

# Delete multiple documents
filter = {"age": {"$lt": 25}}
deleted_count = db.delete_many(filter)
print("Deleted documents:", deleted_count)

# Sort documents by age
results = db.sort_by("age", True)
print("Sorted by age (ascending):", results)

# Sort documents by name
results = db.sort_by("name", False)
print("Sorted by name (descending):", results)

# Count the documents
count = db.count({"name":"Alice"})
print(count)

# Fetch all values for a specific key
d = db.fetch_values_by_key("name")
print(d)

#Get the version of pymongo and soradb
db.version()

# Drop a collection
db.drop_collection(db_collection)

# Check the collection is dropped or not
is_collection_available(db_collection)

```

</details>
