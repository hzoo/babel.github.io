---
layout: docs
title: Transformers
description: What are the various transformers?
permalink: /docs/advanced/transformers/
redirect_from:
 - /docs/usage/transformers/
---

A transformer is a module with a specific goal that is run against your code to transform it. For example,
the `es6.arrowFunctions` transformer has the very specific goal of transforming [ES6 Arrow Functions](https://babeljs.io/docs/learn-es2015/#arrows)
to the equivalent ES3. This allows transformers to be completely unaware of the other transformations happening
so that you can easily chain them together.

## ES3

 - [es3.memberExpressionLiterals]({{ site.baseurl }}/docs/advanced/transformers/es3/member-expression-literals)
 - [es3.propertyLiterals]({{ site.baseurl }}/docs/advanced/transformers/es3/property-literals)

## ES5

 - [es5.properties.mutators]({{ site.baseurl }}/docs/advanced/transformers/es5/properties-mutators)

## ES6

 - [es6.arrowFunctions]({{ site.baseurl }}/docs/learn-es2015/#arrows)
 - [es6.blockScoping]({{ site.baseurl }}/docs/learn-es2015/#let-const)
 - [es6.classes]({{ site.baseurl }}/docs/learn-es2015/#classes)
 - [es6.constants]({{ site.baseurl }}/docs/learn-es2015/#let-const)
 - [es6.destructuring]({{ site.baseurl }}/docs/learn-es2015/#destructuring)
 - [es6.forOf]({{ site.baseurl }}/docs/learn-es2015/#iterators-for-of)
 - [es6.modules]({{ site.baseurl }}/docs/learn-es2015/#modules)
 - [es6.parameters]({{ site.baseurl }}/docs/learn-es2015/#default-rest-spread)
 - [es6.properties.computed]({{ site.baseurl }}/docs/learn-es2015/#enhanced-object-literals)
 - [es6.properties.shorthand]({{ site.baseurl }}/docs/learn-es2015/#enhanced-object-literals)
 - [es6.spread]({{ site.baseurl }}/docs/learn-es2015/#default-rest-spread)
 - [es6.tailCall]({{ site.baseurl }}/docs/learn-es2015/#tail-calls)
 - [es6.templateLiterals]({{ site.baseurl }}/docs/learn-es2015/#template-strings)
 - [es6.regex.unicode]({{ site.baseurl }}/docs/learn-es2015/#unicode)
 - es6.regex.sticky

## ES7 (Experimental)

- [es7.asyncFunctions](https://github.com/lukehoban/ecmascript-asyncawait)
- [es7.classProperties](https://gist.github.com/jeffmo/054df782c05639da2adb)
- [es7.comprehensions]({{ site.baseurl }}/docs/advanced/transformers/comprehensions)
- [es7.decorators](https://github.com/wycats/javascript-decorators)
- [es7.doExpressions](http://wiki.ecmascript.org/doku.php?id=strawman:do_expressions)
- [es7.exponentiationOperator](https://github.com/rwaldron/exponentiation-operator)
- [es7.exportExtensions](https://github.com/leebyron/ecmascript-more-export-from)
- [es7.functionBind](https://github.com/zenparsing/es-function-bind)
- [es7.objectRestSpread](https://github.com/sebmarkbage/ecmascript-rest-spread)
- [es7.trailingFunctionCommas](https://github.com/jeffmo/es-trailing-function-commas)

<blockquote class="babel-callout babel-callout-warning">
  <h4>Disabled by default</h4>
  <p>
    These are only usable if you enable staged support. See <a href={{ "/docs/usage/experimental" | prepend: site.baseurl }}>experimental usage</a> for information.
  </p>
</blockquote>

## Other

 - [flow]({{ site.baseurl }}/docs/advanced/transformers/other/flow)
 - [react]({{ site.baseurl }}/docs/advanced/transformers/other/react)
 - [reactCompat]({{ site.baseurl }}/docs/advanced/transformers/other/react-compat)
 - [regenerator]({{ site.baseurl }}/docs/advanced/transformers/other/regenerator)
 - [strict]({{ site.baseurl }}/docs/advanced/transformers/other/strict)
 - [jscript]({{ site.baseurl }}/docs/advanced/transformers/other/jscript)

## Optional

Babel also includes some optional transformers for those who want to take their code that extra mile.

These are disabled by default, see [usage](#usage) for instructions on how to enable them.

 - [es6.spec.blockScoping]({{ site.baseurl }}/docs/advanced/transformers/es6/spec-block-scoping)
 - [es6.spec.symbols]({{ site.baseurl }}/docs/advanced/transformers/es6/spec-symbols)
 - [es6.spec.templateLiterals]({{ site.baseurl }}/docs/advanced/transformers/es6/spec-template-literals)
 - [asyncToGenerator]({{ site.baseurl }}/docs/advanced/transformers/other/async-to-generator)
 - [bluebirdCoroutines]({{ site.baseurl }}/docs/advanced/transformers/other/bluebird-coroutines)
 - [runtime]({{ site.baseurl }}/docs/usage/runtime)
 - [minification.deadCodeElimination]({{ site.baseurl }}/docs/advanced/transformers/minification/dead-code-elimination)
 - [minification.constantFolding]({{ site.baseurl }}/docs/advanced/transformers/minification/constant-folding)
 - [minification.memberExpressionLiterals]({{ site.baseurl }}/docs/advanced/transformers/minification/member-expression-literals)
 - [minification.propertyLiterals]({{ site.baseurl }}/docs/advanced/transformers/minification/property-literals)
 - [minification.removeConsole]({{ site.baseurl }}/docs/advanced/transformers/minification/remove-console)
 - [minification.removeDebugger]({{ site.baseurl }}/docs/advanced/transformers/minification/remove-debugger)
 - [optimisation.react.inlineElements]({{ site.baseurl }}/docs/advanced/transformers/optimisation/react/inline-elements)
 - [optimisation.react.constantElements]({{ site.baseurl }}/docs/advanced/transformers/optimisation/react/constant-elements)
 - [utility.inlineEnvironmentVariables]({{ site.baseurl }}/docs/advanced/transformers/utility/inline-environment-variables)
 - [spec.protoToAssign]({{ site.baseurl }}/docs/advanced/transformers/spec/proto-to-assign)
 - [spec.undefinedToVoid]({{ site.baseurl }}/docs/advanced/transformers/spec/undefined-to-void)
 - [validation.undeclaredVariableCheck]({{ site.baseurl }}/docs/advanced/transformers/validation/undeclared-variable-check)
 - [validation.react]({{ site.baseurl }}/docs/advanced/transformers/validation/react)

### Usage

```javascript
require("babel").transform("code", { optional: ["transformerName"] });
```

```sh
$ babel --optional transformerName script.js
```
