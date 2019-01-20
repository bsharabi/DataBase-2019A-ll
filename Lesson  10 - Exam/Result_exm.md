# Create DB

## use mongo_practice
```javascript
* switched to db mongo_practice
```



# Create Collection
```
## db.createCollection("movie")
```javascript
* { "ok" : 1 }

```


# Insert Documents
```
db.movie.insert([{title : "Fight Club",
writer : "Chuck Palahniuk",
year : 1999,
actors : [
 "Brad Pitt",
 "Edward Norton"
]},

{title : "Pulp Fiction",
writer : "Quentin Tarantino",
year : 1994,
actors : [
 "John Travolta",
 "Uma Thurman"
]},

{title : "Inglorious Basterds",
writer : "Quentin Tarantino",
year : 2009,
actors : [
 "Brad Pitt",
 "Diane Kruger",
 "Eli Roth"
]},

{
	title : "The Hobbit: An Unexpected Journey",
writer : "J.R.R. Tolkein",
year : 2012,
franchise : "The Hobbit"},

{title : "The Hobbit: The Desolation of Smaug",
writer : "J.R.R. Tolkein",
year : 2013,
franchise : "The Hobbit"},

{title : "The Hobbit: The Battle of the Five Armies",
writer : "J.R.R. Tolkein",
year : 2012,
franchise : "The Hobbit",
synopsis : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."},

{title : "Pee Wee Herman's Big Adventure"},

{title : "Avatar"}])
```javascript
BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 8,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})
```
```
# Query / Find Documents
```
db.getCollection('movie').find({})
db.movie.find().pretty()
// 2
db.movie.find({writer:"Quentin Tarantino"}).pretty()
// 3
db.movie.find({actors:{$in: ["Brad Pitt"]}}).pretty()
// 4
db.movie.find({franchise:"The Hobbit"}).pretty()
// 5
db.movie.find({year: { $gte :  1900, $lte : 1999}}).pretty()
// 6
db.movie.find({year: { $gte :  2000, $lte : 2010}}).pretty()
```
# Update Documents
```
//1
db.movie.findAndModify({
    query: { title: "The Hobbit: An Unexpected Journey" },
	update: {
    $set: {synopsis: "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."}
	}
})

// 2
db.movie.findAndModify({
    query: { title: "The Hobbit: The Desolation of Smaug" },
	update: {
    $set: {synopsis: "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}
	}
})
// 3
db.movie.findAndModify({
    query: { title: "Pulp Fiction" },
	update: {
    $push: {actors: "Samuel L. Jackson"}
	}
})
```
# Text Search
```

// 1
db.movie.find({synopsis: {$regex: /Bilbo/}}).pretty()
// 2
db.movie.find({synopsis: {$regex: /Gandalf/}}).pretty()
// 3
db.movie.find({synopsis: /(?=^.*Bilbo)(?!^.*Gandalf).*/}).pretty()
// 4
db.movie.find({$or:[{synopsis: /dwarves/ },{synopsis:/hobbit/}]}).pretty()
// 5
db.movie.find({$and:[{synopsis: /gold/ },{synopsis:/dragon/}]}).pretty()
```
# Delete Documents
```
//1
db.movie.remove({title: "Pee Wee Herman's Big Adventure"})
// 2
db.movie.remove({title: "Avatar"})
```