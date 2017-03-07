# meteor-native-mongo

It is a very simple package for Meteor that extends mongodb commands.
There is no some magic, just one line of code, but It is very handy to import from node_module, not from a related path.

# Installation
```
$ npm install --save meteor-native-mongo
```

# Usage
```
import db from 'meteor-native-mongo';

db.collection('nameCollection').find({}).toArray((err, result) => {
	console.log(result);
});
```
# List of access methods

* find - Creates a cursor for a query that can be used to iterate over results from MongoDB
* insertOne - Inserts a single document into MongoDB.
* insertMany - Inserts an array of documents into MongoDB.
* bulkWrite -  Perform a bulkWrite operation without a fluent API
  Legal operation types are:

  { insertOne: { document: { a: 1 } } }

  { updateOne: { filter: {a:2}, update: {$set: {a:2}}, upsert:true } }

  { updateMany: { filter: {a:2}, update: {$set: {a:2}}, upsert:true } }

  { deleteOne: { filter: {c:1} } }

  { deleteMany: { filter: {c:1} } }

  { replaceOne: { filter: {c:3}, replacement: {c:4}, upsert:true}}
* insert - Inserts a single document or a an array of documents into MongoDB.
* updateOne - Update a single document on MongoDB.
* replaceOne - Replace a document on MongoDB.
* updateMany - Update multiple documents on MongoDB.
* update - Updates documents.
* deleteOne - Delete a document on MongoDB.
* removeOne - Delete a document on MongoDB.
* deleteMany - Delete multiple documents on MongoDB.