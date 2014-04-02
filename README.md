# broccoli-transform

This helper base class is now obsolete. Use
[broccoli-writer](https://github.com/joliss/broccoli-writer) instead.

To migrate existing `Transform`-based plugins to the new `Writer` base class
supplied by broccoli-writer, turn this `Transform`-based code:

```js
MyCompiler.prototype.transform = function (srcDir, destDir) {
  // code goes here; read from srcDir, write to destDir
};
```

into this `Writer`-based code:

```js
MyCompiler.prototype.write = function (readTree, destDir) {
  return readTree(this.inputTree).then(function (srcDir) {
    // code goes here; read from srcDir, write to destDir
  });
};
```
