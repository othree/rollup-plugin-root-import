rollup-plugin-root-import
=========================

Add the ability to import modules by the root path, like Meteor.

[![Build Status](https://travis-ci.org/mixmaxhq/rollup-plugin-root-import.svg?branch=master)](https://travis-ci.org/mixmaxhq/rollup-plugin-root-import)

```js
// import a module from a different part of the project tree
import UserModel from '/models/user';

// illustrative - if we were in /views/user, we can reference a model's module
// using an absolute path from the root of the project, rather than relative to
// the current module
class UserView extends Backbone.View {
  // ...
}
```

Install
-------

```sh
$ npm install --save-dev rollup-plugin-root-import
```

Usage
-----

```js
import {rollup} from 'rollup';
import rootImport from 'rollup-plugin-root-import';

rollup({
  entry: 'client/src/main.js',
  plugins: [
    rootImport({
      // Will first look in client/src/* and then common/src/*
      root: 'common/src',
      useEntry: 'prepend',

      // If we don't find the file verbatim, try adding these extensions
      extensions: '.js'
    })
  ]
});
```

License
-------

> The MIT License (MIT)
>
> Copyright &copy; 2016 Mixmax, Inc ([mixmax.com](https://mixmax.com))
>
> Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
>
> The above copyright notice and this permission notice shall be included in allcopies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
