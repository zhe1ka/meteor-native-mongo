# meteor-native-mongo

It is a very simple package for Meteor that extends mongodb commands.
There is no some magic, just one line of code, but It is very handy to import from node_module, not from a related path.

# Usage
```
import db from 'meteor-native-mongo';

db.collection('nameCollection').find({}).toArray((err, result) => {
	console.log(result);
});
```
# List of access methods
