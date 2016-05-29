---
layout: docs
title: CLI
description: How to use the CLI tools.
permalink: /docs/usage/cli/
redirect_from: /usage.html
---

<p class="lead">
  Babel comes with a built-in CLI which can be used to compile files from the
  command line.
</p>

## Install

Using [npm](https://www.npmjs.com/) you can install Babel globally, making it
available from the command line.

```sh
$ npm install --global babel
```

## babel

#### Compile Files

Compile the file `script.js` and **output to stdout**.

```sh
$ babel script.js
# output...
```

If you would like to **output to a file** you may use `--out-file` or `-o`.

```sh
$ babel script.js --out-file script-compiled.js
```

To compile a file **every time that you change it**, use the `--watch` or `-w` option:

```sh
$ babel script.js --watch --out-file script-compiled.js
```

### Compile with Source Maps

If you would then like to add a **source map file** you can use
`--source-maps` or `-s`. [Learn more about source maps](http://www.html5rocks.com/en/tutorials/developertools/sourcemaps/).

```sh
$ babel script.js --out-file script-compiled.js --source-maps
```

If you would rather have **inline source maps**, you may use `--source-maps inline`.

```sh
$ babel script.js --out-file script-compiled.js --source-maps inline
```

### Compile Directories

Compile the entire `src` directory and output it to the `lib` directory. You may use `--out-dir` or `-d`.

```sh
$ babel src --out-dir lib
```

Compile the entire `src` directory and output it to the one concatenated file.

```sh
$ babel src --out-file script-compiled.js
```

### Piping Files

Pipe a file in via stdin and output it to `script-compiled.js`

```sh
$ babel --out-file script-compiled.js < script.js
```

## babel-node

<blockquote class="babel-callout babel-callout-warning">
  <h4>Not meant for production use</h4>
  <p>
    You should not be using <code>babel-node</code> in production. It is unnecessarily heavy,
    with high memory usage due to the cache being stored in memory. You will also always
    experience a startup performance penalty as the entire app needs to be compiled on the fly.
  </p>
</blockquote>

babel comes with a second CLI which works exactly the same as Node.js's CLI, only
it will compile ES6 code before running it.

Launch a REPL (Read-Eval-Print-Loop).

```sh
$ babel-node
```

Evaluate code.

```sh
$ babel-node -e "class Test { }"
```

Compile and run `test.js`.

```sh
$ babel-node test
```

### Usage

```sh
$ babel-node [options] [ -e script | script.js ] [arguments]
```

When arguments for user script have names conflicting with node options, double dash placed before script name can be used to resolve ambiguities

```sh
$ babel-node --debug --stage 0 -- script.js --debug
```

### Options

| Option                   | Default              | Description                     |
| ------------------------ | -------------------- | ------------------------------- |
| `-e, --eval [script]`    |                      | Evaluate script                 |
| `-p, --print`            |                      | Evaluate script and print result |
| `-i, --ignore [regex]`   | `node_modules`       | Ignore all files that match this regex when using the require hook |
| `-x, --extensions`       | `".js",".jsx",".es6",".es"` | List of extensions to hook into |
| `-r, --stage [stage]`    | `2`                  | Set the [experimental]({{ site.baseurl }}/docs/usage/experimental) proposal stage |
| `-w, --whitelist`        |                      | Whitelist of transformers separated by comma to ONLY use |
| `-b, --blacklist`        |                      | Blacklist of transformers separated by comma to NOT use |
| `-o, --optional`         |                      | List of optional transformers separated by comma to enable | 
