# tagged-versions

> Get tagged semver-compatible project versions

## Usage

### All project versions
Return all the tagged project versions:
```
const taggedVersions = require('tagged-versions');
return taggedVersions.getList()
  .then(versions => console.log(versions));

// [
//   { version: '1.2.0', tag: 'v1.2.0', hash: 'f6bf448b02c489c8676f2eeaaac72ef93980baf2' },
//   { version: '1.1.1', tag: 'v1.1.1', hash: 'b656238b0fc2502b19bd0e803eb87447840dc52a' },
//   { version: '1.1.0', tag: 'v1.1.0', hash: '1d56b88b0fc2585ffaf43e416b87440667c3c53f' },
//   { version: '1.0.0', tag: 'v1.0.0', hash: '06743d3f902b19bd0e802e40462d87ba2b05740d' },
// ]
```

You can optionally filter versions with a [semver range](https://github.com/npm/node-semver#advanced-range-syntax):
```
const taggedVersions = require('tagged-versions');
return taggedVersions.getList('^1.1.0')
  .then(versions => console.log(versions));

// [
//   { version: '1.2.0', tag: 'v1.2.0', hash: 'f6bf448b02c489c8676f2eeaaac72ef93980baf2' },
//   { version: '1.1.1', tag: 'v1.1.1', hash: 'b656238b0fc2502b19bd0e803eb87447840dc52a' },
//   { version: '1.1.0', tag: 'v1.1.0', hash: '1d56b88b0fc2585ffaf43e416b87440667c3c53f' },
// ]
```

### Last project version
Return the last tagged project version:
```
const taggedVersions = require('tagged-versions');
return taggedVersions.getLastVersion()
  .then(versions => console.log(version));

// { version: '1.2.0', tag: 'v1.2.0', hash: 'f6bf448b02c489c8676f2eeaaac72ef93980baf2' }
```

Like with `getList`, you can also filter with a [semver range](https://github.com/npm/node-semver#advanced-range-syntax):
```
const taggedVersions = require('tagged-versions');
return taggedVersions.getLastVersion('~1.1')
  .then(versions => console.log(version));

// { version: '1.1.1', tag: 'v1.1.1', hash: 'b656238b0fc2502b19bd0e803eb87447840dc52a' }
```

## Contributing
Please follow the [Airbnb guidelines](https://github.com/airbnb/javascript), commit your changes with `git cz`, and then create a pull request.
Thank you :-)
