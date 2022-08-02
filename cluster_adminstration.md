## Sharding:
- Until now, It's super easy to store an entire data set on one server, but that's not got if this instance failed at some point!!
- That's why they invented the term "Replica Set" which is actually a bunch of servery containing the same data set, it one failed the others do the work!!
- When our application grows, the entire data set in each server grows and at this point we will have to increase the power of server hardware (Vertical scalling). But, at some point the hardware scalling can't increase more(There is limit, right?) and of course it's super expensive.
- That's why there is another approach called "Horizontal Scalling" and MongoDB actually follows that approach, instead of making the individual machine better, we just add more machines and distrubute the data set among those machines!
- The way we distrubute data in MongoDB is called "Sharding", so, sharding is actually a way of storing our data set without worrying of storing it all in one machine/ server.
- MongoDB shardes/ divides the data set into pieces and distrubute those pieces into differenct machines.
- In order to ensure the viability of those pieces, we distrubute them into shared cluster (Group of servers)

<br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/1.png"/> <br/>
<img src="https://raw.githubusercontent.com/AhmedElgaidi/my-mongodb-university-notes/main/public/cluster_adminstration/2.png"/> <br/>
