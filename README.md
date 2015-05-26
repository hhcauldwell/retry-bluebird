This is the read me file.

### Example
```
var Promise = require('bluebird');
var retry = require('retry-bluebird');
var database = require(...);

retry({max: 5}, function(attemptCounter) {
  return Promise.fromNode(function(cb) {
    database.connect(cb);
  });
})
.then(function() {
  console.log('Connected to DB!');
}, function(err) {
  throw err;
});
```
