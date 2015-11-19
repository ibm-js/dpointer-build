# dpointer-build

Build version of [ibm-js/dpointer](https://github.com/ibm-js/dpointer).

## Status

No official release yet.

## Installation

_Bower_ release installation:

    $ bower install dpointer-build

_Manual_ master installation:

    $ git clone git://github.com/ibm-js/dpointer-build.git

Then install dependencies with bower (or manually from github if you prefer to):

	$ cd dpointer-build
	$ bower install


## How to use

### `baseUrl` is the directory containing `dpointer-build`.
This is the most common use-case so the needed configuration is built in the layer.
To load the minified layer you just need to wrap your main `require` call with another `require`, requiring `"dpointer-build/layer"`.
Then you should continue to refer to modules with `"dpointer/foo"`.

For example, this code:
```js
require(["app/main", "dpointer/foo"], function() {
	...
});
```
Becomes:
```js
require(["dpointer-build/layer"], function() {
	require(["app/main", "dpointer/foo"], function() {
		...
	});
});
```

### Other `baseUrl`

If `baseUrl` is not the directory containing `dpointer-build`, custom configuration is needed.

```js
require.config({
	paths: {
		"dpointer": "path/to/dpointer-build"
	}
});
```


## Bug reporting

Issues should be filled against the source version of this project at [ibm-js/dpointer](https://github.com/ibm-js/dpointer)


## Licensing

This project is distributed by the Dojo Foundation and licensed under the ["New" BSD License](./LICENSE).
All contributions require a [Dojo Foundation CLA](http://dojofoundation.org/about/claForm).
