Simple reducer for use with flux. Reduces an array or map into an array of objects with:
  { id, data, status }

Status is given first so we can allow currying, ex:

```js
var loadedReducer = reducer.bind(null, 'LOADED');

fetch(url).then(loadedReducer).then(store);
```

status is optional, default value is 'OK'

```js
assert(reducer([1]) === [{ id: 0, data: 1, status: 'OK' }]
```
