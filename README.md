# Cache Blockstore

> An IPLD Blockstore on top of the browser CacheStorage API

## Usage

```ts
import {Cachestore} from "cache-blockstore";

(async () => {
  const store = new Cachestore("/my-app/blocks");

  await store.open();
}());
```
