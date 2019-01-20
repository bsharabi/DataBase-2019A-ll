# Create DB
```javascript
* use mongo_practice
```
### Result
```javascript
* switched to db mongo_practice
```


# Create Collection
```javascript
 * db.createCollection("movie")
```
### Result
```javascript
* { "ok" : 1 }
```


# Insert Documents
```
* db.movie.insert(
[{title : "Fight Club",
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
```
### Result
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

# Query / Find Documents
```
* db.getCollection('movie').find({}).pretty()
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839a"),
        "title" : "Fight Club",
        "writer" : "Chuck Palahniuk",
        "year" : 1999,
        "actors" : [
                "Brad Pitt",
                "Edward Norton"
        ]
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839b"),
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
                "John Travolta",
                "Uma Thurman"
        ]
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839c"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
        ]
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839d"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839e"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839f"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
{
        "_id" : ObjectId("5c44670abbae7baecf6983a0"),
        "title" : "Pee Wee Herman's Big Adventure"
}
{ "_id" : ObjectId("5c44670abbae7baecf6983a1"), "title" : "Avatar" }
```

```javascript
* db.movie.find().pretty()
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839a"),
        "title" : "Fight Club",
        "writer" : "Chuck Palahniuk",
        "year" : 1999,
        "actors" : [
                "Brad Pitt",
                "Edward Norton"
        ]
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839b"),
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
                "John Travolta",
                "Uma Thurman"
        ]
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839c"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
        ]
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839d"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839e"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839f"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
{
        "_id" : ObjectId("5c44670abbae7baecf6983a0"),
        "title" : "Pee Wee Herman's Big Adventure"
}
{ "_id" : ObjectId("5c44670abbae7baecf6983a1"), "title" : "Avatar" }
```

```javascript
* db.movie.find({writer:"Quentin Tarantino"}).pretty()
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839b"),
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
                "John Travolta",
                "Uma Thurman"
        ]
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839c"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
        ]
}
```

```javascript
* db.movie.find({actors:{$in: ["Brad Pitt"]}}).pretty()
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839a"),
        "title" : "Fight Club",
        "writer" : "Chuck Palahniuk",
        "year" : 1999,
        "actors" : [
                "Brad Pitt",
                "Edward Norton"
        ]
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839c"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
        ]
}
```

```javascript
* db.movie.find({franchise:"The Hobbit"}).pretty()
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839d"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839e"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839f"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
```
```javascript
* db.movie.find({year: { $gte :  1900, $lte : 1999}}).pretty()
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839a"),
        "title" : "Fight Club",
        "writer" : "Chuck Palahniuk",
        "year" : 1999,
        "actors" : [
                "Brad Pitt",
                "Edward Norton"
        ]
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839b"),
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
                "John Travolta",
                "Uma Thurman"
        ]
}
```

```javascript
* db.movie.find({year: { $gte :  2000, $lte : 2010}}).pretty()
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839c"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
        ]
}
```
### Result
```javascript

```

# Update Documents
```javascript
* db.movie.findAndModify(
{
    query: { title: "The Hobbit: An Unexpected Journey" },
	update: {
    $set: {synopsis: "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."}
	}
})
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839d"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
```

```javascript
* db.movie.findAndModify(
{
    query: { title: "The Hobbit: The Desolation of Smaug" },
	update: {
    $set: {synopsis: "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}
	}
})
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839e"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit"
}
```

``` javascript
* db.movie.findAndModify(
{
    query: { title: "Pulp Fiction" },
	update: {
    $push: {actors: "Samuel L. Jackson"}
	}
})
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839b"),
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
                "John Travolta",
                "Uma Thurman"
        ]
}
```

# Text Search
```
* db.movie.find({synopsis: {$regex: /Bilbo/}}).pretty()
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839d"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839e"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit",
        "synopsis" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839f"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
```
```javascript
* db.movie.find({synopsis: {$regex: /Gandalf/}}).pretty()
```

### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839e"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit",
        "synopsis" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
}
```
```javascript
* db.movie.find({synopsis: /(?=^.*Bilbo)(?!^.*Gandalf).*/}).pretty()
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839d"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839f"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
```
```javascript
* db.movie.find({$or:[{synopsis: /dwarves/ },{synopsis:/hobbit/}]}).pretty()
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839d"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
{
        "_id" : ObjectId("5c44670abbae7baecf69839e"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit",
        "synopsis" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
}
```
```javascript
* db.movie.find({$and:[{synopsis: /gold/ },{synopsis:/dragon/}]}).pretty()
```
### Result
```javascript
{
        "_id" : ObjectId("5c44670abbae7baecf69839d"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
```
### Result
```javascript

```

# Delete Documents
```javascript
* db.movie.remove({title: "Pee Wee Herman's Big Adventure"})
```
### Result
```javascript
WriteResult({ "nRemoved" : 1 })
```

```javascript
* db.movie.remove({title: "Avatar"})
```
### Result
```javascript
WriteResult({ "nRemoved" : 1 })
```
