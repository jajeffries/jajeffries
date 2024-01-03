---
title: 'An Overview of MongoDB'
date: Sat, 23 Jun 2012 14:21:49 +0000
draft: false
tags: ['software', ]
---

This week I attended my first conference: MongoDB UK. It was an interesting experience, both because of the technology and the people I met. MongoDB is one of the NoSQL breed of databases. This means that instead of storing data in rows in tables, which are linked by relations, all the data is stored in documents in a collection. A document is similar to a row in a table, but has a JSON like structure of key-value pairs. A collection is similar to a table in a relational database, but has no fixed schema and no relationship with other collections. This means that document's structures can differ. It's easy to install MongoDB on a Debian based system. In Ubuntu just use

> sudo apt-get install mongodb

Then to connect to the database and start an interactive session use the following command

> jim@jim-netbook:~$ mongo MongoDB shell version: 2.0.4 connecting to: test >

First we need to make a new collection. We'll call ours "foo".

> \> db.createCollection( "foo" ) { "ok" : 1 }

First thing you'll probably notice is that this looks pretty different to SQL. That's because the mongoDB shell uses JavaScript to query the database, which returns JSON like documents. Here it has returned { "ok" :1} to signify that it has successfully created our "foo" collection. Now we can start adding some documents.

> \> db.foo.save({ a: 2, b: "Hello" }) > db.foo.save({ a: "WORLD", b: "Hello", c: false }) > db.foo.save({ a: 42, c: false })

As you can see we can add documents with completely different structures. This gives us a lot of flexibility compared to a relational database. Lets see if we can find all of the documents where "b" exists.

> \> db.foo.find( {b: {$exists: true}}) { "\_id" : ObjectId("4fe5c77d0ecc9452d649d4fd"), "a" : 2, "b" : "Hello" } { "\_id" : ObjectId("4fe5c7a20ecc9452d649d4fe"), "a" : "WORLD", "b" : "Hello", "c" : false }

Lets see if we can find every document when "a" is 2

> \> db.foo.find( {a:2}) { "\_id" : ObjectId("4fe5ca6d0ecc9452d649d500"), "a" : 2, "b" : "Hello" }

Simple. What about if we want to update "a" to 3 if "a" is currently 2?

> \> db.foo.find( {a: 3}) { "\_id" : ObjectId("4fe5cb1a0ecc9452d649d501"), "a" : 3, "b" : "Hello" }

Suppose "b" is a greeting and we want it to change from "Hello" to "Salut".

> \> db.foo.update( {b: "Hello"}, {$set : {b:"Salut"}}) > db.foo.find( {b: "Salut"}) { "\_id" : ObjectId("4fe5cb1a0ecc9452d649d501"), "a" : 3, "b" : "Salut" }

We can see from the "\_id" that the document is the same, but we have updated "b". Lets looks at update in a bit more detail. The first parameter is the query is similar to the "WHERE" part of an update command in SQL. We are selecting which documents we want to update. The second part is the update modifier. This acutally updates the documents we have selected. "$set" is used to set a particular value. If instead we were to use

> \> db.foo.update( {b: "Hello"}, {b:"Salut"}) > db.foo.find( {b: "Salut"}) { "\_id" : ObjectId("4fe5cb1a0ecc9452d649d501"), "b" : "Salut" }

it updates the contents of the document to be {"b": "Salut"} instead of just updating "b". A useful tip for troubleshooting the performance of your queries is to add ".explain()".

> \> db.foo.find( {b: "Salut"}).explain() { "cursor" : "BasicCursor", "nscanned" : 8, "nscannedObjects" : 8, "n" : 1, "millis" : 0, "nYields" : 0, "nChunkSkips" : 0, "isMultiKey" : false, "indexOnly" : false, "indexBounds" : { } }

This gives us some basic information about the performance of the query and how it was executed. I won't go into to much detail about this here but might at a later date. If we found that a query was too slow we could create an index using the "ensureIndex" command.

> \> db.foo.ensureIndex({ b: 1}) > db.foo.find( {b: "Salut"}).explain() { "cursor" : "BtreeCursor b\_1", "nscanned" : 3, "nscannedObjects" : 3, "n" : 1, "millis" : 1, "nYields" : 0, "nChunkSkips" : 0, "isMultiKey" : false, "indexOnly" : false, "indexBounds" : { "b" : \[ \[ "Salut", "Salut" \] \] } }

As you can see this has added something to the indexBounds in the information available from ".explains()". Over the few documents we have so far this won't really make too much of a difference to performance, but if we had millions or even billions of records a carefully placed index could speed up queries significantly. A word of warning however: don't add too many indexes or the effects could be detrimental on performance. While I've not touched on some of the cool administrative features of MongoDB (such as sharding, replication and MMS) hopefully this will be a decent overview and enough to give you a basic understanding of MongoDB.