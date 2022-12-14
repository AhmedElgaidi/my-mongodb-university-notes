# MongoDB Basics (Course 1):

#### What is a database?

- A structured way to store and access data.

#### What is NoSQL database?

- A database for storing data in an organized way but not in rows and columns as in SQL databases.

#### What is MongoDB database?

- It's a NoSQL database for storing data in the form of documents, which are stored in a form called collection.

#### What are MongoDB documents?

- A way to organize and store the data as a set of field-value pairs.

```
    {
        <field>: <value>
        <field>: <value>
    }
```

<br>

**Note:** field: A unique identifier for datapoint, value: data related to a given identifier.

#### What are MongoDB collections?

- An organized store of documents in MongoDB, usually with common fileds between documents.

#### What is Atlas Cloud MongoDB database?

- It's a fully managed database built for a wide range of applications with MongoDB as a it's core.

#### What is Cluster Deployment?

- Clusters are a group of servers storing your data. these servers are congigured as replica sets.
- Replica set: A few connected MongoDB instances that store the same data (Any chnage/ update in our document change in all our replica sets!).
- Instance: Its' a single machine (Running locally or in cloud) running a certain software.
- The idea of replica sets, is when one server goes down for any reason, the other replica sets do the work for us.

**[Note:]** Atlas manages the details of creating clusters for us ,which is really good for us, instead of doing all the databse deployment configurationsetup and choosing the cloud service provider (Amazon, etc..) on our own.

#### JSON (Javascript standard Object Notation):

- Pros:
  - Friendly.
  - Readable.
  - Familiar
- Cons:
  - Text-based (Text parsing is slow).
  - Space consuming.
  - Data types limitation.

#### BSON (Binary JSON):

- Fixed the drawback of JSON.
- Optimized for:
  - Speed.
  - Space.
  - Flexibility.
- High performance.
- General- purpose focus.

#### [BSON vs. JSON](https://www.mongodb.com/json-and-bson)

|              |              JSON              |                                     BSON                                      |
| :----------: | :----------------------------: | :---------------------------------------------------------------------------: |
|   Encoding   |          UTF-8 String          |                                    Binary                                     |
| Data Support | String, Boolean, Number, Array | String, Boolean, Number(Integer, Float, Long, etc...),Array, Date, Raw Binary |
|  Redability  |       Human and Machine        |                                 Machines Only                                 |

**[Note:]** MongoDB stores data in BSON format which makes it faster and more flexible and we can see it in JSON and this is tha magic!.
<br>
**Stored BSON and viewed JSON**

#### Interacting with the Atlas cluster:

- Export cluster data to a local machine.
- Export to a different system.
- Backup cloud data locally.
- Import from a local machine.
- Import from a different system.

### Import and Export in MongoDB:

- In JSON fromat (Human readable, slow):
  - mongoimport command.
  - mongoexport command.
- In BSON format (Not human readable, fast):
  - mongorestore command.
  - mongodump command.

<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/4.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/3.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/1.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/2.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/5.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/6.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/7.png"/> <br/>

#### \_id field:

<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/8.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/9.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/10.png"/> <br/>

#### Updating:

- updateOne(): It updates only the first document that matches the query.
- updateMany(): Updates all docs that match the query.
  <br/>
  <img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/11.png"/> <br/>
  <img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/12.png"/> <br/>

#### Deleting:

<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/13.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/14.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/15.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/16.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/17.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/18.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/19.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/20.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/21.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/22.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/23.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/24.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/25.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/26.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/27.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/28.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/29.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/30.png"/> <br/>

```
// We are passing the fields name with the $ operator, to tell mongodb to
// do the query on the values of the specified field not to a fixed field value
db.trips.find(
{
  "$expr": {
    "$eq": [
      "$start station id",
      "$end station id"
    ]
  }
}
).count()
```

<br/>

```
// Another example
// Here, we are adding two conditions with the $add operator, and since we are using 
// the field value to do logic, we used "$expr" operator
db.trips.find({
  "$expr": {
    "$and": [
      {"$gt": ["$tripduration", 1200]},
      {"$eq": ["$start station id", "$end station id"]}
    ]
  }
}).count()
```
**[Note: ]** The MQL stands for "MongodDb query language", it's just like SQL (Structured Query Language) 
used to query data from relational databases
<br/>
<br/>

<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/31.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/32.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/33.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/34.png"/> <br/>

#### Query a value in an array:
- We could a simple query such ```find({<field>: <value`})```` and it willl return all the docs that have this string, and this approach is not good as it may return docs with this value and only present as a string not an arary.
- We could use this weak query ``` find({<field>: [<value>]})```` this will return al lthe docs that have only this value in it's aray.
- we couls use multiple values ```find({<field>: [<value1>, <value2>, etc..]})``` this will return all the docs in the given order of values **The order matters!!!**
- **The best approach when dealling with array field using MQL** ``` find({"$all": [<value1>, <value2>, <value3>, etc...]}) ``` **Here the order doesn't matter!**
- Sometimes, we would decrease the number of search in our DB, by issuing the array size to look into!!

```
// Only return docs that their amenities field value is only 20 value!!
// And those 20 values has to include the given strings!!

db.listingsAndReviews.find({
  "amenities": {
    "$size": 20, // condition 1
    "$all": [ // condition 2
      "Wifi",
      "Internet"
    ]
  }
}).count()

```

<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/35.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/36.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/37.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/38.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/39.png"/> <br/>


<br/>

```
// Query docs with two conditions (one on string field and other on array field) with oridnary MQL

db.listingsAndReviews.find({
    "property_type": "House",
    "amenities": {
      "$all": ["Changing table"]
    }
}).count()

```

<br/>

#### Projection:
- It tells MongoDB which field we want to see (We use it when we want only to see specific value, not the whole document)

```
// Another query with projection:

db.listingsAndReviews.find({
  "amenities": {
    "$size": 20,
    "$all": [
      "Internet",
      "Wifi"
    ]
  }
}, { // This is for projection => Only return the price field or returned docs.
  "price": 1,
})

```
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/40.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/41.png"/> <br/>


```
// Another query with projection (sub-document)
// Here we are returning all the studends assigned to this class and returning only
// the score of a certain subject if it's greater than 85

db.trips.find({
  {"class_id": 431},
  {"scores": {
    "$elemMatch": {
      "score": {
        "$gt": 85
      }
    }
  }
  }
})

```
<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/42.png"/> <br/>


```
// Here we are only returning the count of docs that have city "Seattle" value 
db.companies.find(
  {"offices": {
    "$elemMatch": {
      "city": "Seattle"
    }
  }})
  .count()
```

<br/>

#### Dot notation for dealling with sub-documents:
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/43.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/44.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/45.png"/> <br/>


```
// We can pass multiple expressions to the the elemMatch array operator

db.companies.find(
  {
    "relationships": {
      "$elemMatch": {
        "is_past": true, // expression 1
        "person.first_name": "Mark" // expression 2
      }
    }
  },
  {
    name: 1
  }
)

```
<br/>

<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/46.png"/> <br/>


```
db.trips.find({
  "start station location.coordinates.0": {
    "$lt": -74
  }
}).count()
```

```
db.inspections.find(
  {"address.city": "NEW YORK"},
  {}
).count()
```


#### MongoDB Aggregation Framework:

<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/47.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/48.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/49.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/50.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/51.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/52.png"/> <br/>

```
// Simple aggregation query
// Here we are returning how many docs in each country
db.listingsAndReviews.aggregate([
  {
    "$project": {
      "address.country": 1
    }
  },
  {
    "$group": {
      "_id": "$address.country", // the field you want to play with
      "count": { // the field you want to add to the document in the pipeline
        "$sum": 1
      }
    }
  }
])

```


```
// Result of query

[
  { _id: 'Brazil', count: 606 },
  { _id: 'Hong Kong', count: 600 },
  { _id: 'China', count: 19 },
  { _id: 'United States', count: 1222 },
  { _id: 'Spain', count: 633 },
  { _id: 'Portugal', count: 555 },
  { _id: 'Canada', count: 649 },
  { _id: 'Turkey', count: 661 },
  { _id: 'Australia', count: 610 }
]

```
<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/53.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/54.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/55.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/57.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/58.png"/> <br/>

**[Note:]** the aggregation framework doesn't modify the data!! It's all just playing with the form of returned data!!!

```
// Another aggregation query

db.listingsAndReviews.aggregate([
  {
    "$project": {
      "room_type": 1
    }
  },
  {
    "$group": {
      "_id": "$room_type",
      "type": {
        "$sum": 1
      }
    }
  }
])

```

```
// Result of query:
[
  { _id: 'Shared room', type: 83 },
  { _id: 'Entire home/apt', type: 3489 },
  { _id: 'Private room', type: 1983 }
]

```

<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/basics/59.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/basics/60.png"/> <br/>

<br/>

```
// This query super helpful for top 10 documents etc...
// this returns the doc with the highest population field
db.zips.find().sort({"pop": =1}).limit(2)

```

```
// Get the youngest user document

db.trips.find({"birth year": {
  "$ne": ""
}}).sort({"birth year": 1}).limit(1)
```
<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/61.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/62.png"/> <br/>


#### Indexes:
<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/63.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/64.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/65.png"/> <br/>


#### Data Modeling:
<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/66.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/67.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/68.png"/> <br/>



#### Updating:

<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/69.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/70.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/71.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/72.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/73.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/74.png"/> <br/>


#### MongoDB Compass:

<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/75.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/basics/76.png"/> <br/>
