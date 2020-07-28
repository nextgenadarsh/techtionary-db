- [MongoDB](#mongodb)
  - [Getting Started](#getting-started)
    - [Structure](#structure)
    - [Installation & Shell](#installation--shell)
    - [Characteristics](#characteristics)
      - [Schemaless](#schemaless)
      - [No / Few Relation](#no--few-relation)
    - [Connecting to MongoDb from](#connecting-to-mongodb-from)
    - [Mongo Shell](#mongo-shell)
    - [CRUD Operation](#crud-operation)
      - [Create](#create)
      - [Read](#read)
      - [Update](#update)
      - [Delete](#delete)
    - [Playing with Data](#playing-with-data)
      - [lookUp()](#lookup)
      - [Schema Validation](#schema-validation)
    - [Create Collection](#create-collection)
    - [Points To Remember](#points-to-remember)


# MongoDB

- Convert JSON(BSON) to binary format before storing on disk

## Getting Started

### Structure

- Database
  - Collections
    - Documents

### Installation & Shell

- [Installation on OSX](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)
- Configure the mongodb/bin path in `.base_profile` file
- Basic Commands
  - Start mongodb server: `mongod -dbpath /usr/local/var/mongodb/data/db  --port 27018`
  - Start mongodb shell: `mongo --port 27018`
  - Show databases: `show dbs`
  - Use database: `use shopdb`
  - Insert record to product collection in shopdb database: 
    `db.products.insertOne({name: "Cindrella", price: 34.56})`
  - Find records: `db.products.find().pretty()`
  - Drop collection: `db.products.drop()`

### Characteristics

#### Schemaless

- Give flexibility
- It is responsibility of developer to enforce schema

#### No / Few Relation

- Relational data needs to be merged manually

### Connecting to MongoDb from
  - Application
    - MongoDb Driver
    - [Download Drivers](https://docs.mongodb.com/drivers/)
  - Analytics/BI Tools
    - BI connector / Shell
  - Admin
    - Shell `mongo`

### Mongo Shell

- [mongo Shell Quick Reference](https://docs.mongodb.com/manual/reference/mongo-shell/)
- [mongo Shell Reference Cards](https://info-mongodb-com.s3.amazonaws.com/ReferenceCards15-PDF.pdf)

### CRUD Operation

#### Create

- `insertOne(data, options)`
- `insertMany(data, options)`

#### Read

- `find(filter, options)` gives cursor
- `find(filter, options).toArray()` gives all results, not cursor
- `findOne(filter, options)`
- Eg: 
  - `db.city.find().pretty()`
  - `db.city.find({}, {_id: 0, name: 1})` returns records with only `name` field

#### Update

- `update(filter, data, options)` is suggested not be used.
- `updateOne(filter, data, options)` merges data
- `updateMany(filter, data, options)` merges data
- `replaceOne(filter, data, options)` overrides whole data
- Examples: 
  - `db.city.update({name: "Hyderabad"}, {pollutionLevel: "Good"})` overrides whole data
  - `db.city.update({name: "Hyderabad"}, {$set: {pollutionLevel: "Good"}})` merges data
  - `db.city.updateOne({name: "Hyderabad"}, {$set: {pollutionLevel: "Good"}})` merges data
  - `db.city.updateMany({}, {$set: {pollutionLevel: "AllBad"}})`

#### Delete

- `deleteOne(filter, options)`
- `deleteMany(filter, options)`
- Eg: `db.city.deleteOne({name: "Hyderabad"})`

### Playing with Data

#### lookUp()

- Used to join two collections
- Eg:
  - `db.books.aggregate()`

#### Schema Validation

### Create Collection

```js
  db.createCollection("posts", {
    validator: {
      $jsonSchema: {
        bsonType: "object", 
        required: ["title", "text", "creator", "comments"],
        properties: {
          title: {
            bsonType: "string",
            description: ""
          },
          comments: {
            bsonType: "string",
            description: ""
          }
        }
      }
    }
  })
```

### Points To Remember

- You can override the `_id` field of inserted record as `{_id: "overridden-id-1", insertedId: "overridden-id-1"}`
