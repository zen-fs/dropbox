# ZenFS Dropbox

> [!WARNING]
> This package was implemented very recently and may not be stable.
> 
> If you find a bug, please report it. Thanks!

This package adds the `Dropbox` backend for ZenFS.

For more information, see the [API documentation](https://zenfs.dev/dropbox).

> [!IMPORTANT]
> Please read the [ZenFS core documentation](https://zenfs.dev/core)!

## Installing

```sh
npm install @zenfs/dropbox
```

## Usage

> [!NOTE]
> The examples are written in ESM.  
> For CJS, you can `require` the package.  
> For a browser environment without support for `type=module` in `script` tags, you can add a `script` tag to your HTML pointing to the `browser.min.js` and use the global `ZenFS_Dropbox` object.

```ts
import { configure, fs } from '@zenfs/core';
import { Dropbox } from '@zenfs/dropbox';
import { Dropbox as DropboxClient } from 'dropbox';

const client = new DropboxClient({
	accessToken: '...',
	// ...
});

await configure({
	mounts: {
		'/mnt/dropbox': {
			backend: Dropbox,
			client,
		},
	},
});
```