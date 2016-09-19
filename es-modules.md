## Geoff Filippi

### Application Architect

---

# [Oildex](www.oildex.com)

A cloud service company for oil and gas

* 1 year

---

Formerly:

# [Time Warner Cable](www.timewarnercable.com)

* 12 years

---

## Experience

<i class="fa fa-phone"></i>

* Worked on streaming media (Voice over IP), 6 years
* 5 million phone customers

---

## Experience

<i class="fa fa-video-camera"></i>

* Worked on video and streaming video, 4 years

---

## Projects

[twctv.com](twctv.com)

* Video streaming website
 * backbone.js
* Video streaming Set-Top Box (STB) web application

---

## Oildex Projects

* Rewrite 10+-year-old apps
* Angular 1.5
* Angular 2
* ES6
* Typescript

---

---

# We will cover

* History and Background
* ES Module Standards
* Current and Upcoming Implementations

---

---

# History
## and
# Background

---

## Modular Programming

* Separation of Concerns
* Information Hiding
* Encapsulation
* Dependency Management

---

## Benefits of Modules

* Code reuse
* Maintainability

---

## Drawbacks of Modules

* Complexity
* Coupling

---

## Early Module Implementations

* ALGOL 68-R and ALGOL 68C (1970)
* Modula (1968)

---

## Partial List of Languages with Module Support

Ada, Algol, Clojure, COBOL, Dart, Erlang, F, Fortran, Go, Haskell, MATLAB, ML, Modula, Objective-C, Perl, Python, Ruby, Rust

---

## [Scripts](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)

```
<script src="javascript.js"></script>
```

---

## [Script Loading](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)

* Parse HTML until script tag is located
* Stop parsing HTML
* Fetch script
* Execute immediately
* Resume parsing HTML

---

## Global Scope

```
var myVariable = "global scope";
```

---

## Function Scope

```
function myFunction() {
   var myVariable = "function scope";
}
```
---

## Object Literals

```
var myModule = {
   myVariable: 0,
   myFunction: function () { 
      return "myFunction called";
   }
}
```

```
console.log(myModule.myVariable); // 0

console.log(myModule.myFunction()); // myFunction called

```

---

## [Closure](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)

```
function myFunction() {
   var myVariable = "my value";
   function myOtherFunction() {
      console.log(myVariable);
   }
   return myOtherFunction;
}
```

```
var myOneMoreFunction = myFunction();
myOneMoreFunction();
```
---

## [IIFE](http://benalman.com/news/2010/11/immediately-invoked-function-expression/)

```
(function(){ 
   var myVariable = "my value";
   console.log("myVariable");
}()); 
```

---

## [Module Pattern](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#modulepatternjavascript)

```
var myModule = (function(){ 
   var myVariable = "my value";

   return {
      get: function(){
         return myVariable;

      },
      set: function( newValue ){
         myVariable = newValue;

      }
   };
}()); 
```

```
console.log(myModule.get());
```

---

## [Revealing Module Pattern](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#revealingmodulepatternjavascript)

```
var myModule = (function () {
        var myVariable = "my value";
        function _set( newValue ) {
            myVariable = newValue;
        }
        function set(newValue) {
            _set(newValue);
        }
        function get() {
            return myVariable;
        }
       return {
            get,
            set
        };
    })();
```
---

## [Revealing Module Pattern](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#revealingmodulepatternjavascript)
 
```
myModule.get(); // "my value"
myModule.set("new value");
myModule.get(); // "new value"
myModule._set("call private");
// TypeError: myModule._set is not a function

```

---

## [CommonJS Modules](http://wiki.commonjs.org/wiki/Modules/1.1.1)

### Use

```
var fs = require('fs');

fs.readFile('index.js', function (err, data) {
   if (err) {
      return console.error(err);
   }
   console.log("input file: \n" + data.toString());
});
```

---

## [CommonJS Modules](http://wiki.commonjs.org/wiki/Modules/1.1.1)

### Define

```
var myVariable = "my value";
var _set = function ( newValue ) {
   myVariable = newValue;
}
var set = function set(newValue) {
   _set(newValue);
}
var get = function () {
   return myVariable;
}

module.exports = {
   get,
   set
};
```

---

## [AMD](https://github.com/amdjs/amdjs-api/blob/master/AMD.md)

### Asynchronous Module Definition

```
define("myModule", 
   ["require", "exports"], 
   function (require, exports) {
      exports.get = function() {
         return "value";
      }
});
```

---

### [RequireJS](http://requirejs.org)

* File and AMD module loader

```
define(function (require) {
    var myModule = require('./myModule');

    myModule.get();
});
```

---

## [UMD](https://github.com/umdjs/umd)

```
(function (root, factory) {
    if (typeof define === 'function' && define.amd) {
        define([], factory); // AMD
    } else if (typeof module === 'object' && module.exports) {
        module.exports = factory(); // Node
    } else {
        root.returnExports = factory(); // Global
  }
}(this, function () {
    return {}; // module implementation
}));
```

---

---

# ES Module Standards

---

## [ES Module Syntax](https://tc39.github.io/ecma262/#prod-Module)

---

## `"use strict";`

---

## `import`

```
import { readFile } from 'fs';
```

---

## `export`

---

## [ES Module Loader](https://html.spec.whatwg.org/multipage/webappapis.html#module-script)

---
---

# Current and Upcoming Implementations

---

## Browsers

---

## Script Tag

```
<script type="module" src="echo.js"></script>
<script>
   import { echo } from 'echo';
   alert(echo("hello");
</script>
```

---

## [Browser Support](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)

### No Support (yet)

#### Desktop

* Chrome
* Firefox
* Internet Explorer
* Opera
* Safari

---

## [Browser Support](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)

### No support (yet)

#### Mobile

* Android
* Firefox Mobile
* IE Mobile
* Opera Mobile
* Safari Mobile

---

## [Browser Support](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)

### Basic Support

#### Desktop

* Edge (Build 14342)

---

## [Browser Support](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)

### Basic Support

#### Mobile

* Android Webview 36.0
* Chrome for Android 36.0

---

## Transpiliers

---

### [`babel`](https://github.com/geofffilippi/node-es6-modules-babel)

---

### [`typescript`](https://github.com/geofffilippi/node-es6-ts-modules)

---

## Polyfills and Runtimes

---

### [ES6 Module Loader Polyfill](https://github.com/ModuleLoader/es6-module-loader)

* Dynamic module loader
* Supports ES6 modules
* Browser and NodeJS
* Latest stable spec
* Expecting update after loader proposals stabilize

---

### [SystemJS](https://github.com/systemjs/systemjs)

* Built on ES6 Module loader
* Supports ES6, AMD, CommonJS and globals
* Can load other than JS (CSS, Images, etc.) with plugins

---

# Questions?

---

## Links

* [Script](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)
* [Script Element](https://html.spec.whatwg.org/multipage/scripting.html#the-script-element)
* [Script Specification](https://html.spec.whatwg.org/multipage/webappapis.html#classic-script)
* [WHATWG Module Loader Specification](https://html.spec.whatwg.org/multipage/webappapis.html#module-script)
* [ES Module Specification](https://tc39.github.io/ecma262/#prod-Module)

---

## Links

* [ES6 In Depth: Modules](https://hacks.mozilla.org/2015/08/es6-in-depth-modules/)
* [Module Pattern](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#modulepatternjavascript)
* [Revealing Module Pattern](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#revealingmodulepatternjavascript)
* [IIFE](http://benalman.com/news/2010/11/immediately-invoked-function-expression/)
* [Module - comp.lang.javascript](https://groups.google.com/forum/#!msg/comp.lang.javascript/eTzWVa1W_pE/N9lnvRG9WJ8J)

---

## Links

* [Modular Programming](https://en.wikipedia.org/wiki/Modular_programming)
* [Writing Modular JavaScript](https://addyosmani.com/writing-modular-js/)
* [SystemJS](https://github.com/systemjs/systemjs)
* [ES6 Module Loader](https://github.com/ModuleLoader/es6-module-loader)
* [ES6 Node modules](https://github.com/zenparsing/es6-node-modules)

---

## Links

* [WHATWG Loader](https://github.com/whatwg/loader.git)
* [Simplified Loader](https://github.com/whatwg/loader/issues/147)
* [babel ES Modules to CommonJS](https://babeljs.io/docs/plugins/transform-es2015-modules-commonjs/)
* [Node.js Enhancement Proposals](https://github.com/nodejs/node-eps)
* [Unambiguous JavaScript Grammar](https://github.com/bmeck/UnambiguousJavaScriptGrammar)

---

## Links

* [Exploring ES6 - Modules](http://exploringjs.com/es6/ch_modules.html)
* [Configuring Babel 6 for Node.js](http://jsrocks.org/2016/01/configuring-babel-6-for-node-js/)
