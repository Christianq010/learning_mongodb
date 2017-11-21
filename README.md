# Learning MongoDB

## Description
> This is basically a project documenting the setup, instalation and key commands for Mongodb for Windows via the Traversy media Youtube tutorial series.

### *Installation*
* Download the free community server [here](https://www.mongodb.com/)

#### Setting up MongoDB
* During the installation process select `custom installation` and change the location to `c:/mongodb` for ease and simplicity.
* In the `mongodb` directory create the following folders - `data/db` and `log`.
* Run the following commands from `mongodb/bin` with admin access from the command prompt
```
mongod --directoryperdb --dbpath C:/mongodb/data/db --logpath C:/mongodb/log/mongo.log --logappend --rest --install
```

### MongoDB
> In the `c:/mongodb/bin` folder
* To start Mongo as a service run `net start mongodb`
* To Run our shell -  `mongo`
  * In the Shell - `cls` - to clear the screen
  * To show a list of db's - `show dbs`
  * Check the current db we are in - `db`
  * To create new db - `use databaseName`

### CRUD Operations
* Create a User

```json
use databaseName
db.createUser(
  {
    user: "Chris",
    pwd: "1234",
    roles: [ "readWrite", "dbAdmin"]
  }
);
```

* Create a collection

```json
db.createCollection('collectionName');
  {
      "ok": 1
  }
```

* Show collections with `show collections`.
* Insert into a collection. 
```json
db.customername.insert (
    {
        first_name: "John"
    },
    {
        first_name: "Jane",
        last_name: "Foster",
        gender: "Female",
    }
);
```

* Look at the data in a collection with  `db.customername.find().pretty();`
* Updating existing data with
```json
db.customers.update(
  {
        first_name: "John"
        last_name: "Smith"
        gender: "Male"
    }
);
```

```json
db.customers.update(
    {
        first_name: "Steven"
    },
    {
        $set: {
        gender: "male"
        }
    }
);
```

* Remove / Delete a row
```json
db.customers.update(
    {
        first_name: "John"
    },
    {
        $unset: {
            age: 1
        }
    }

);
```

### Database Queries
```json
    {
        first_name: "John",
        last_name: "Doe",
        memberships: ["mem1","mem2"],
        address: {
            street: "4 main st",
            city: "Boston"
        }
        contacts: [
            {name: "Brad", relationship: "friend"},
        ]
    }
```