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