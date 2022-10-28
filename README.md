# Cache Blockstore

> An IPLD Blockstore on top of the browser [CacheStorage](https://developer.mozilla.org/en-US/docs/Web/API/Cache) API

## Install

```sh
npm i cache-blockstore
```

## Usage

```ts
import {Cachestore} from "cache-blockstore";
import * as Block from 'multiformats/block'
import * as codec from '@ipld/dag-cbor'
import { sha256 as hasher } from 'multiformats/hashes/sha2'

const value = { hello: 'world' }

(async () => {
  const store = new Cachestore("/my-app/blocks");

  await store.open();

  // encode a block
  let block = await Block.encode({ value, codec, hasher })

  await store.put(block.cid, block.bytes);
}());
```
