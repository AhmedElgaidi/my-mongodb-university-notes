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

#### JSON vs. BSON
|         |   JSON         |           BSON          |
| :----:  | :------: | :----------:     |
| Encoding | UTF-8 String | Binary |
| Data Support | String, Boolean, Number, Array| String, Boolean, Number(Integer, Float, Long, etc...),Array, Date, Raw Binary|
| Redability| Human and Machine | Machines Only|


**[Note:]** MongoDB stores data in BSON format which makes it faster and more flexible.
[BSON vs. JSON comparison from mongodb.com](https://www.mongodb.com/json-and-bson)