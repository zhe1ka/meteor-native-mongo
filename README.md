# meteor-native-mongo

It is a very simple package for Meteor that extends mongodb commands.
There is no some magic, just one line of code, but It is very handy to import from node_module, not from a related path.

# Requirement
Meteor >= 1.4

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

Be attention: not all methods are supported (native mongodb).
The full list are present below.

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
* removeMany - Delete multiple documents on MongoDB.
* remove - Remove documents.
* save - Save a document. Simple full document replacement function. Not recommended for efficiency, use atomic
  operators and update instead for more efficient operations.
* findOne - Fetches the first document that matches the query.
* rename - Rename the collection.
* drop - Drop the collection from the database, removing it permanently. New accesses will create a new collection.
* options - Returns the options of the collection.
* isCapped - Returns if the collection is a capped collection.
* createIndex - Creates an index on the db and collection collection.
* createIndexes - Creates multiple indexes in the collection.
* dropIndex - Drops an index from this collection.
* dropIndexes - Drops all indexes from this collection.
* dropAllIndexes - Drops all indexes from this collection.
* reIndex - Reindex all indexes on the collection
  Warning: reIndex is a blocking operation (indexes are rebuilt in the foreground) and will be slow for large collections.
* listIndexes - Get the list of all indexes information for the collection.
* ensureIndex - Ensures that an index exists, if it does not it creates it.
* indexExists - Checks if one or more indexes exist on the collection, fails on first non-existing index.
* indexInformation - Retrieves this collections index info.
* count - Count number of matching documents in the db to a query.
* distinct - The distinct command returns returns a list of distinct values for the given key across a collection.
* indexes - Retrieve all the indexes on the collection.
* stats - Get all the collection statistics.
* findOneAndDelete - Find a document and delete it in one atomic operation, requires a write lock for the duration of the operation.
* findOneAndReplace - Find a document and replace it in one atomic operation, requires a write lock for the duration of the operation.
* findOneAndUpdate - Find a document and update it in one atomic operation, requires a write lock for the duration of the operation.
* findAndModify - Find and update a document.
* findAndRemove - Find and remove a document.
* aggregate - Execute an aggregation framework pipeline against the collection.
* parallelCollectionScan - Return N number of parallel cursors for a collection allowing parallel reading of entire collection. There are
  no ordering guarantees for returned results.
* geoNear - Execute the geoNear command to search for items in the collection.
* geoHaystackSearch - Execute a geo search using a geo haystack index on a collection.
* group - Run a group command across a collection.
* mapReduce - Run Map Reduce across a collection. Be aware that the inline option for out will return an array of results not a collection.
* initializeUnorderedBulkOp - Initiate a Out of order batch write operation. All operations will be buffered into insert/update/remove commands executed out of order.
* initializeOrderedBulkOp - Initiate an In order bulk write operation, operations will be serially executed in the order they are added, creating a new operation for each switch in types.
