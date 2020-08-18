# Protocol Buffers for Node
A wrapper in Node for the compiled protoc from https://github.com/google/protobuf.

This package was originally forked from https://github.com/YePpHa/node-protoc but my primary use case was being able to use the protoc command without compiling or manually installing.

## Version
Currently using Protocol Buffers `v3.11.2`.

## Platforms
Google provides binary files for Windows, Linux and OSX in x86_64 and x86_32.

## Get the `protoc` command without installing
You can use this package to execute the `protoc` command on any compatible platform that runs NodeJS/NPM.

For example, install this package locally to your project:
```
npm i -D protoc-cli
```
Then you may execute using `npx`. For example, to compile a message class from `protos/dummy.proto`:
```
npx protoc --proto_path=protos --js_out=import_style=commonjs,binary:messageClasses protos/dummy.proto
```

## Example: usage in JS
This library also allows for use in NodeJS code. Documentation has not been provided, other than this example:

```JavaScript
var protoc = require("protoc");

protoc.library(["path/to/file.proto", "path/to/file2.proto"], function(err, files) {
  if (err) return console.error(err);
  
  // Handle the JavaScript Vinyl files.
  // These files can be used in Google Closure Compiler,
  // but they require the files in
  // https://github.com/google/protobuf/tree/master/js
  
  // ...
});
```
