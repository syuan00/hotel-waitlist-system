# hotel-waitlist-system

**In terminal:**

```shell
docker run -p 3000:3000 -dit IMAGE_NAME
```

**In the shell of the docker:**

1. Install MongoDB

```shell
apt install gnupg
apt install curl
curl -fsSL https://www.mongodb.org/static/pgp/server-4.4.asc | apt-key add -
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.4 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-4.4.list 
apt update
apt install mongodb-org
apt install screen
mkdir -p /data/db
screen mongod # Press Ctrl+a followed by d to return to terminal
mongo # This will open a mongoDB CLI
exit
```

2. Clone the repository inside docker container

```shell
git clone https://github.com/syuan00/hotel-waitlist-system.git
cd hotel-waitlist-system
npm install
```

3. Test Q2

```shell
mongo waitlistdb scripts/init.mongo.js
node scripts/trymongo.js
```

We can also use the CLI of mongo to check the data.

```
mongo
show databases
use waitlistdb
db.counters.find().pretty()
db.customers.find().pretty()
```

4. Run the sever

```shell
npm run compile
mongo waitlistdb scripts/init.mongo.js
npm start
```

**In the browser:**

Open http://localhost:3000/

Open http://localhost:3000/graphql

```javascript
query {
  customerList {
    id
    name
    phone
    timestamp
  }
}

mutation {
  customerAdd(customer:{
    name: "Paul"
    phone: "45389625"
  }) {
    id
    timestamp
  }
}

mutation {
  customerDelete(id:3)
}
```

