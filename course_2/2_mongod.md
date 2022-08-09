# Mongod:
- The daemon process of MongoDB.
<br/>
![test](https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/mongod/1.png)

### What is a daemon?
- It's a programs or a process that's meant to be run, but not interacted with directly.
- That's why we call it "mongod" (mongo + "d").

<br/>
![test](https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/mongod/2.png)

### What is mongod?
- It's the main daemon process for MongoDB.
- It's the core server of the database.
- Handles:
    - Connections.
    - Request.
    - Persisting our data.
- It contains all the configuraion options that we can use to make our DB more secure, distributed and consistent.

<br/>
![test](https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/mongod/3.png)


### Let's explain:
- Our data may be distributed in a replica set or across a sharded cluster.
- In this case, we run a separate mongod process for each server in our cluster.
- When we lunch "mongod", we are esstentially starting up a new database. But, we dont't interact with "mongod" directly.
- Instead, we use a database client that's progarammed to communicate with "mongod", we issue commands like: documents inserts, updates, etc... to the client and the client takes care of communicating with "mongod" to excuete those commands.
- **Note:** If our deployment has multiple servers, we can configure our "database client" to communicate with each "mongod" process as needed. So, we don't need to figure our which server to connect to ourselves. 
<br/>
![test](https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/mongod/4.png)
![test](https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/mongod/5.png)
