# Report

>  IT5007: Software Engineering on Application Architecture
>
>  Tutorial-5: Hotel California International Waitlist System 
>
> Author: Hu Xuan (A0228578M)

**Git Repository Link**: https://github.com/syuan00/hotel-waitlist-system

Below is the output of executing Mongo commands for Q2.

```shell
root@b978eec7ff01:/hotel-waitlist-system# mongo waitlistdb scripts/init.mongo.js
MongoDB shell version v4.4.10
connecting to: mongodb://127.0.0.1:27017/waitlistdb?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("9d43ab91-41c3-4ac4-872e-48228f3d92eb") }
MongoDB server version: 4.4.10
Inserted 2 customers
root@b978eec7ff01:/hotel-waitlist-system# node scripts/trymongo.js
(node:1558) [MONGODB DRIVER] Warning: Current Server Discovery and Monitoring engine is deprecated, and will be removed in a future version. To use the new Server Discover and Monitoring engine, pass option { useUnifiedTopology: true } to the MongoClient constructor.
Connected to MongoDB
--- CREATE ---
Result of insert:
 61794c74bb26a5061637eb15
--- READ ---
Result of find:
 [ { _id: 61794c65084e343d2bde9630,
    id: 1,
    name: 'Jeul',
    phone: '83918492',
    timestamp: 2021-09-30T00:00:00.000Z },
  { _id: 61794c65084e343d2bde9631,
    id: 2,
    name: 'Yang',
    phone: '31094583',
    timestamp: 2021-10-01T00:00:00.000Z },
  { _id: 61794c74bb26a5061637eb15,
    id: 3,
    name: 'Paul',
    phone: '45389625' } ]
--- UPDATE ---
After updating the customer with id of 2:
 [ { _id: 61794c65084e343d2bde9631,
    id: 2,
    name: 'UPDATE NAME',
    phone: '31094583',
    timestamp: 2021-10-01T00:00:00.000Z } ]
--- DELETE ---
After deleting the customer with id of 2:
 [ { _id: 61794c65084e343d2bde9630,
    id: 1,
    name: 'Jeul',
    phone: '83918492',
    timestamp: 2021-09-30T00:00:00.000Z },
  { _id: 61794c74bb26a5061637eb15,
    id: 3,
    name: 'Paul',
    phone: '45389625' } ]
```