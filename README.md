# openport

Finds open network ports.

## Installation

```bash
$ npm install openport
```

## Quick Examples

```javascript
var op = require('openport');

op.find(function(err, port) {
  if(err) { console.log(err); return; }
  // yea! we have an open port.
});

op.find(
  {
    ports: [ 1024, 1025, 1026, 1028 ],
    count: 2
  }
  function(err, ports) {
    if(err) { console.log(err); return; }
    // yea! we have two open ports.
  }
);

op.find(
  {
    startingPort: 1024,
    endingPort: 2000,
    avoid: [ 1025, 1500 ]
  }
  function(err, port) {
    if(err) { console.log(err); return; }
    // yea! we have an open port between 1024 and 2000.
  }
);
```
