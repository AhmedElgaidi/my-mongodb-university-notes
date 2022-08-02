b## Sharding:
- Until now, It's super easy to store an entire data set on one server, but that's not got if this instance failed at some point!!
- That's why they invented the term "Replica Set" which is actually a bunch of servery containing the same data set, it one failed the others do the work!!
- When our application grows, the entire data set in each server grows and at this point we will have to increase the power of server hardware (Vertical scalling). But, at some point the hardware scalling can't increase more(There is limit, right?) and of course it's super expensive.
- That's why there is another approach called "Horizontal Scalling" and MongoDB actually follows that approach, instead of making the individual machine better, we just add more machines and distrubute the data set among those machines!
- The way we distrubute data in MongoDB is called "Sharding", so, sharding is actually a way of storing our data set without worrying of storing it all in one machine/ server.
- MongoDB shardes/ divides the data set into pieces and distrubute those pieces into differenct machines.
- In order to ensure the viability of those pieces, we distrubute them into shared cluster (Group of servers)

<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/1.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/2.png"/> <br/>

- Now we have several servers with different shards (pieces) of data!!, how could we query??????????/
- Here, MongoDB does some Router process to direct the query request to it's desired shared cluster to get docs.
- That router process is called "Mongos", So the client connects to the mongos instead of connecting to each shard individually.
- According to this we may have as many clients as we want to talk to "mongos" which redirects the client request to the appropiate shared cluster!!!
- But, how mongos knows which request should be directed to that cluster?
- Each shared cluster has a metadata and stored in a "config servers", But this metadata is used alot. So, we have to make it highly available, So how can we do that?
- We use "Replication"!!!
- MongoDB replicates the data on multiple config servers instead of one config server, "MongoDB deploys Config Server Replica Set"

So, in short:
- Shards: Store distrubuted collections.
- Config Server: Store metadata about each shard.
- Mongos: Routes queries to shards

### When we should consider to shard?
- We should shard if the Vertical scalling is no longer available (more CPU, RAM, DISK, Network).
- we need to know that the Horizontal scalling is is cheaper than the Vertical scalling (The point is the Horizontal scalling is not environment friendly)
- Another point to consider in Vertical scalling, is you increased the disk space to 15 Terabytes and you are using 75% of it, everything would be okay of saving new data and query data, etc... but the problem appears when making backups and using those backups later (Retrieving) or even when doing syncing with other replica sets **The more space the more time you need to backup/ retreive the data and the more consumpotion of newtwork bandwidth**

**[Note]:** When the data set gets bigger, the indexes increase, The performance of querying decrease. So, we will need to increase our RAM to increase our processing performance **Increasing size of disks lead to increasing in the size of RAM! => More Cost and at some point the hardware would appear and the bottle neck appears too** That's why sharding (Horizontal Scalling) is usually the better solution!!!!

- MongoDB reccommends that each server should have more thant 2 to 5 Terabytes of data!! if you need more, then scale horizontally!!


- So **"Paralization"** is really good (The Horizontal scalling approach):
- Backup
- Restore
- Sync among Replica set

## Sharding Architecture:

<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/3.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/4.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/5.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/6.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/7.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/8.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/9.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/10.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/11.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/12.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/13.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/14.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/15.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/16.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/17.png"/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/18.png"/><br/>

#### Explanation:
- The most importnat info of the sharded cluster is we can add any number of shards we want, and because of this, the client application can't communicate directly with the shards, that's whwere the benifit of "mongos" appears.
- A router process called "mongos" is established.
- The client (browser, etc...) connect with the mongos, then the mongose direct the query to the appropriate shard.
- But, how does mongose deliver the query to the correct shard?
- Let's say we divied/ sharded our data set into 3 shards according to the username alphapet (It's like indexing, to help in searching | metadata). 
- Mongos will need this data to direct the query to the correcct shard, let's say the client want to get the document with the usrname "Suarez", it started with "S", then mongos direct the query directly to teh cluster that have documents with usernames starts with "s"
- MongoDB offers high availability, so there may be different clients connecting to the mongose instances at the same time (and they just direct the query), of even absolute diffent application using our data set!!! just the smae logic
**[Note]:** The metadata is not stored on the mongos!! It's stored in a config server, so once the client connect to mongos, mongos check metadata from the "config server" and according to the result direct to the correct shard


**[Note]:** The config server is continously updated/ changed according to the data in the shards!!! But, why does it change in the first place? let's say we have big usernames starting with "S", so the shard number3 is really big and loaded and the shard 1,2 is not. The **config Server** decided which data should be moved => the metadata changed also to make room in the shard 3 for the users starting with "S"


**[Note]:** During aggregation, let's say that the client wants to get all the users with age 28-30. We are sharding our database/ data set according to the username, right? So, how could this query be done? Mongos direct the query to each shard and merge the all returned docs from all shards to the client and that's actually what happens behins the seens on every query!!!