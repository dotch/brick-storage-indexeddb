# x-storage-indexeddb

[![Build Status](https://travis-ci.org/dotch/x-storage-indexeddb.png)](https://travis-ci.org/dotch/x-storage-indexeddb)

## Demo

[Check it live!](http://dotch.github.io/x-storage-indexeddb)

## Usage

1. Import Web Components polyfill:

    ```html
    <script src="bower_components/platform/platform.js"></script>
    ```

2. Import Custom Element:

    ```html
    <link rel="import" href="src/element.html">
    ```

3. Start using it:

    ```html
    <x-storage-indexeddb></x-storage-indexeddb>
    ```

## Options

Attribute     | Options     | Default      | Description
---           | ---         | ---          | ---
`name`        | *string*    | `storage`    | The database name.
`key`         | *string*    |              | The name of the mandatory unique primary key to use for get, set and remove operations.
`index`       | *string*    |              | One or multiple indices which can be used to order and  the results of queries which return multiple items.

## Methods

Method            | Returns a promise for           | Description
---               | ---                             | ---
`insert(object)`  | Key of the saved object.        | Insert an object.
`set(object)`     | Object to save/update.          | Insert/upate an object.
`get(key)`        | Object                          | Retrieves the object with the key.
`remove(key)`     | Null                            | Deletes the object with the key.
`getAll(options)` | All objects.                    | Retrieves all stored object. <ul><li>`options.orderby` - The key/index by which the results will be ordered.</li></ul>
`getMany(options)`| Multiple objects.               | Retrieves multiple stored objects. <ul><li>`options.start` - The first id of the results.</li><li>`options.end` - The last id of the results.</li><li>`options.count` - The number of results.</li><li>`options.offset` - The offset of the first result when set to true.</li><li>`options.orderby` - The key/index by which the results will be ordered.</li><li>`options.reverse` - Reverse the order of the results.</li></ul>
`size()`          | Number of stored items.         | Returns the number of stored objects.
`clear()`         | Null                            | Deletes all database entries.

## Development

In order to run it locally you'll need to fetch some dependencies and a basic server setup.

* Install [Bower](http://bower.io/) & [Gulp](http://gulpjs.com/):

    ```sh
    $ npm install -g bower gulp
    ```

* Install local dependencies:

    ```sh
    $ bower install && npm install
    ```

* To test the project, start the development server and open `http://localhost:3001`.

    ```sh
    $ gulp server
    ```

* To build the css and lint the scripts.

    ```sh
    $ gulp build
    ```

* To provide a live demo, send everything to `gh-pages` branch.

    ```sh
    $ gulp deploy
    ```

## License

[MIT License](http://opensource.org/licenses/MIT)
