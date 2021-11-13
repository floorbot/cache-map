# cache-map

A simple key/value pair caching system

### Example

```ts
import CacheMap from 'cache-map';

const cache = new CacheMap<string, string>({ ttl: 1000 * 60, maxKeys: 2 });
cache.set('first', 'I will expire in 60 seconds!');
cache.set('second', 'I will expire in 160 seconds!', 1000 * 160);
const set = cache.set('third', 'max keys reached and will return false');
const first = cache.get('first');
if (!first) console.log('Must have expired!');
```
