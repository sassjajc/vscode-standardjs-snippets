# vscode-standardjs-snippets

Forked from https://github.com/capaj/vscode-standardjs-snippets to changes the snippet prefixs to be more compatible when inlined with intellisense keywords.

ES6 Import and export snippets as well as the console snippets are from https://github.com/xabikos/vscode-javascript, converted to Standard JS format with new prefixes and descriptions.

"Originally forked from https://github.com/gaboesquivel/atom-standardjs-snippets, but we've added couple more. Also these are not using special characters because vscode doesn't like them in the snippets."

## Standard JavaScript Snippets for Visual studio code

A collection of ES6 snippets for faster JavaScript development in [Atom Editor](https://atom.io/).

This collection is complementary to [atom/language-javascript](https://github.com/atom/language-javascript). It's based on [extrabacon/atom-turbo-javascript](https://github.com/extrabacon/atom-turbo-javascript) and it enforces [standardjs code style](http://standardjs.com/).

[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)

__Yes!, no semicolons:__
- [Are Semicolons Necessary in JavaScript?](https://www.youtube.com/watch?v=gsfbh17Ax9I)
- [An Open Letter to JavaScript Leaders Regarding Semicolons](http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding)
- [JavaScript Semicolon Insertion - Everything You Need to Know](http://inimino.org/~inimino/blog/javascript_semicolons)


## No need to give snippets the top autocompletion priority

Although you can enable it, it isn't necessary for snippets to be at the top of your autocompletion results.
Intellisense keyword completion is generally more important to me, so I keep the default value of inlining snippets with keywords.

However, if you want snippets to be at the top, you can enable it with:

```
"editor.snippetSuggestions": "top",
```
in your settings.json.

## Snippets

Snippets are optimized to be short and mnemonic, but also to not conflict with common JavaScript keywords.

Note that these links work only on github, not on VSCode marketplace:

- [declarations](#declarations)
- [flow control](#flow-control)
- [functions](#functions)
- [iterables](#iterables)
- [objects and classes](#objects-and-classes)
- [return values](#return-values)
<!--- [types](#types)-->
- [promises](#promises)
- [ES6 modules](#es6-modules)
- [Node.js modules](#nodejs)
- [testing](#testing)
- [timers](#timers)
- [miscellaneous js](#miscellaneous-js)
- [console](#console)
- [DOM](#dom)

### Declarations

#### `vas⇥` var assignment
```js
var ${1:name} = ${2:value}
```

#### `las⇥` let assignment
```js
let ${1:name} = ${2:value}
```

#### `ly⇥` let yielded assignment
```js
let ${1:name} = yield ${2:value}
```

#### `cna⇥` const assignment
```js
const ${1:name} = ${2:value}
```

#### `cnob⇥` const object
```js
const ${1:name} = {
  ${0}
}
```

#### `cod⇥` const object destructuring
```js
const {${1:name}} = ${2:value}
```

#### `cnar⇥` const array
```js
const ${1:name} = [
  ${0}
]
```

#### `cad⇥` const array destructuring
```js
const [{${1:name}}] = ${2:value}
```

#### `cy⇥` const yielded assignment
```js
const ${1:name} = yield ${2:value}
```


### Flow Control

#### `ifs⇥` if statement
```js
if (${1:condition}) {
  ${0}
}
```

#### `ees⇥` and `ee⇥` else statement
```js
else {
  ${0}
}
```

#### `ies⇥` else statement
```js
if (${1:condition}) {
  ${0}
} else {

}
```

#### `eis⇥` and `ei⇥` else if statement
```js
else if (${1:condition}) {
  ${0}
}
```

#### `letif⇥` and `lei⇥` let - if statement
```js
let ${1}
if (${0}) {
  ${1} = ${2}
}
```

#### `fl⇥` for loop (ES6)
```js
for (let ${1:i} = 0, ${2:len} = ${3:iterable}.length ${1:i} < ${2:len}; ${1:i}++) {
  ${0}
}
```

#### `flin⇥` for in loop (ES6)
```js
for (let ${1:key} in ${2:source}) {
  if (${2:source}.hasOwnProperty(${1:key})) {
    ${0}
  }
}
```

#### `flof⇥` for of loop (ES6)
```js
for (let ${1:key} of ${2:source}) {
  ${0}
}
```

#### `wl⇥` while loop
```js
while (${1:condition}) {
  ${0}
}
```

#### `wid⇥` while iteration decrementing
```js
let ${1:array}Index = ${1:array}.length
while (${1:array}Index--) {
  ${0}
}
```

#### `tc⇥` try/catch
```js
try {
 ${0}
} catch (${1:err}) {

}
```

#### `tf⇥` try/finally
```js
try {
 ${0}
} finally {

}
```

#### `tcf⇥` try/catch/finally
```js
try {
  ${0}
} catch (${1:err}) {

} finally {

}
```

#### `tn⇥` throw new
```js
throw new ${0:error}
```


### Functions

#### `fn⇥` anonymous function
```js
function (${1}) {${0}}
```

#### `fne⇥` anonymous empty function
```js
function () {${0}}
```

#### `fnn⇥` named function
```js
function ${1:name}(${2:arguments}) {
  ${0}
}
```

#### `af⇥` arrow function (ES6)
```js
(${1}) => {${0}}
```

#### `afe⇥` arrow empty function (ES6)
```js
() => {${0}}
```

#### `afcb⇥` arrow function concise body (ES6)
```js
(${1:arguments}) => ${2:statement}
```

#### `gf⇥` generator function (ES6)
```js
function* (${1:arguments}) {
  ${0}
}
```

#### `gfn⇥` named generator function (ES6)
```js
function* ${1:name}(${1:arguments}) {
  ${0}
}
```

#### `asf⇥` async function
```js
async function (${1:arguments}) {
  ${0}
}
```

#### `asa⇥` async arrow function
```js
async (${1:arguments}) => {
  ${0}
}
```

#### `iife⇥` immediately-invoked function expression (IIFE)
```js
;(function (${1:arguments}) {
  ${0}
})(${2})
```

#### `fap⇥` function apply
```js
${1:fn}.apply(${2:this}, ${3:arguments})
```

#### `fc⇥` function call
```js
${1:fn}.call(${2:this}, ${3:arguments})
```

#### `fb⇥` function bind
```js
${1:fn}.bind(${2:this}, ${3:arguments})
```


### Iterables

#### `felp⇥` forEach loop
```js
${1:iterable}.forEach((${2:item}) => {
  ${0}
})
```

#### `map⇥` map function
```js
${1:iterable}.map((${2:item}) => {
  ${0}
})
```

#### `reduce⇥` reduce function
```js
${1:iterable}.reduce((${2:previous}, ${3:current}) => {
  ${0}
}${4:, initial})
```

#### `filter⇥` filter function
```js
${1:iterable}.filter((${2:item}) => {
  ${0}
})
```

#### `find⇥` ES6 find function
```js
${1:iterable}.find((${2:item}) => {
  ${0}
})
```

#### `every⇥` every function
```js
${1:iterable}.every((${2:item}) => {
  ${0}
})
```

#### `some⇥` some function
```js
${1:iterable}.some((${2:item}) => {
  ${0}
})
```


### Objects and classes

#### `ok` Object.keys
```js
Object.keys(${1:obj})
```

#### `oc` Object.create
```js
Object.create(${1:obj})
```

#### `oa` Object.assign
```js
Object.assign(${1:dest}, ${2:source})
```

#### `og` Object.getOwnPropertyDescriptor
```js
Object.getOwnPropertyDescriptor(${1:dest}, '${2:prop}')
```

#### `od` Object.defineProperty
```js
Object.defineProperty(${1:dest}, '${2:prop}', {
  ${0}
})
```

#### `proto⇥` prototype method
```js
${1:Class}.prototype.${2:methodName} = function (${3:arguments}) {
  ${0}
}
```

#### `cs⇥` class (ES6)
```js
class ${1:name} {
  constructor(${2:arguments}) {
    ${0}
  }
}
```

#### `csx⇥` extend a class (ES6)
```js
class ${1:name} extends ${2:base} {
  constructor(${2:arguments}) {
    super(${2:arguments})
    ${0}
  }
}
```

#### `cc⇥` constructor (ES6 syntax)
```js
constructor () {
  ${0}
}
```

#### `cm⇥` method (ES6 syntax)
```js
${1:method} (${2:arguments}) {
  ${0}
}
```

#### `cget⇥` getter (ES6 syntax)
```js
get ${1:property} () {
  ${0}
}
```

#### `cset⇥` setter (ES6 syntax)
```js
set ${1:property} (${2:value}) {
  ${0}
}
```

#### `cgs⇥` getter and setter (ES6 syntax)
```js
get ${1:property} () {
  ${0}
}
set ${1:property} (${2:value}) {

}
```


### Return values

#### `rt⇥` return
```js
return ${0}
```

#### `rtt⇥` return this
```js
return this
```

#### `rtn⇥` return null
```js
return null
```

#### `rto⇥` return new object
```js
return {
  ${0}
}
```

#### `rta⇥` return new array
```js
return [
  ${0}
]
```

#### `rtp⇥` return Promise (ES6)
```js
return new Promise((resolve, reject) => {
  ${0}
})
```


### Promises

#### `pnew⇥` and `pn⇥` new Promise (ES6)
```js
new Promise((resolve, reject) => {
  ${0}
})
```

#### `pall⇥` Promise.all
```js
Promise.all([${1:value}])
```

#### `presolve⇥` and `prs⇥` Promise.resolve
```js
Promise.resolve(${1:value})
```

#### `preject⇥` and `prj⇥` Promise.reject
```js
Promise.reject(${1:value})
```

#### `pthen⇥` and `pth⇥` Promise.then
```js
${1:promise}.then((${2:value}) => {
  ${0}
})
```

#### `pcatch⇥` and `pc⇥` Promise.catch
```js
${1:promise}.catch((${2:err}) => {
  ${0}
})
```

#### `awt⇥` await
```js
await ${0}
```

#### `yd⇥` yield
```js
yield ${0}
```


### ES6 modules

#### `imd⇥` import module default export
```js
import ${2:moduleName} from '${1:module}'$0
```

#### `imm⇥` import member(s) of module with destructuring
```js
import { $2 } from '${1:module}'$0
```

#### `imma⇥` import member(s) of module in a local alias with destructuring
```js
import { ${2:originalName} as ${3:alias} } from '${1:module}'$0
```

#### `imwb⇥` import entire module without bindings
```js
import '${1:module}'$0
```

#### `ima⇥` import all exported bindings in a local alias
```js
import * as ${2:alias} from '${1:module}'$0
```

#### `edf⇥` export default function
```js
export default (${1:params}) =>  {
  $0
}
```

#### `emf⇥` export member function(s)
```js
export { ${0} }
```

#### `enf⇥` export named function
```js
export const ${1:functionName} = (${2:params}) =>  {
  $0
}
```

#### `edc⇥` export default class
```js
export default class ${1:className} {
  $0
}
```

#### `edce⇥` export default class that extends a base class
```js
export default class ${1:className} extends ${2:baseclassName} {
  $0
}
```


### Node.js modules

#### `rq⇥` require a module
```js
require('${1:module}')
```
#### `crq⇥` require and assign a module
```js
const ${1:module} = require('${1:module}')
```

#### `eme⇥` export member
```js
exports.${1:name} = ${2:value}
```

#### `moe⇥` module.exports
```js
module.exports = ${1:name}
```

#### `cb⇥` Node.js style callback
```js
function (err, ${1:value}) {
  if (err) throw err
  t${0}
}
```


### Testing

#### `iarr⇥` and `ia⇥` isArray
```js
Array.isArray(${1:source})
```

#### `tyo⇥` typeof comparison
```js
typeof ${1:source} === '${2:undefined}'
```

#### `ino⇥` instanceof comparison
```js
${1:source} instanceof ${2:Object}
```

#### `exxpect⇥` expect (multiple libraries)
```js
expect(${1})${0}
```

### Jest using anonymous arrow functions

#### `adescribe⇥` and `ads⇥` describe
```js
describe('${1:description}', () => {
  ${0}
})
```

#### `atest⇥` and `ate⇥` test
```js
test('${1:description}', () => {
  ${0}
})
```

#### `ait⇥` it
```js
it('${1:description}', () => {
  ${0}
})
```

#### `abfa⇥` and `aba⇥` before all
```js
before(() => {
  ${0}
})
```

#### `abfe⇥` and `abe⇥` before each
```js
beforeEach(() => {
  ${0}
})
```

#### `aafa⇥` and `aaa⇥` after all
```js
after(() => {
  ${0}
})
```

#### `aafe⇥` and `aae⇥` after each
```js
afterEach(() => {
  ${0}
})
```

### Mocha, Jasmine, ... using anonymous functions

#### `tdescribe⇥` and `fd⇥` describe
```js
describe('${1:description}', function () {
  ${0}
})
```

#### `tcontext⇥` context (alias for describe)
```js
describe('${1:description}', function () {
  ${0}
})
```

#### `tsit⇥` and `ts⇥` synchronous "it"
```js
it('${1:description}', function () {
  ${0}
})
```

#### `tait⇥` asynchronous "it"
```js
it('${1:description}', function (${2:done}) {
  ${0}
})
```

#### `ttest⇥` and `tt⇥` test (alias for it)
```js
test('${1:description}', function (${2:done}) {
  ${0}
})
```

#### `tbf⇥` before
```js
before(function () {
  ${0}
})
```

#### `tbfa⇥` and `tba⇥` before all (jasmine)
```js
beforeAll(function () {
  ${0}
})
```

#### `tbfe⇥` and `tbe⇥` before each
```js
beforeEach(function () {
  ${0}
})
```

#### `taf⇥` after
```js
after(function () {
  ${0}
})
```

#### `tafa⇥` and `taa⇥` after all (jasmine)
```js
afterAll(function () {
  ${0}
})
```

#### `tafe⇥` and `tae⇥` after each
```js
afterEach(function () {
  ${0}
})
```

#### `tsuite⇥` suite with setup and teardown
```js
suite('${1:suiteName}', function() {
  setup(function() {
    ${2}
  })
  teardown(function() {
    ${3}
  })
  ${0}
})
```


### Timers

#### `sti⇥` setTimeout
```js
setTimeout(() => {
  ${0}
}, ${1:delay})
```

#### `sin⇥` setInterval
```js
setTimeout(() => {
  ${0}
}, ${1:delay})
```

#### `sim⇥` setImmediate
```js
setImmediate(() => {
  ${0}
})
```


### Miscellaneous JS

#### `ust⇥` use strict
```js
'use strict'
```

#### `js⇥` JSON Stringify
```js
JSON.stringify($0)
```

#### `jp⇥` JSON Parse
```js
JSON.parse($0)
```


### Console

#### `coa⇥` console.assert
```js
console.assert(${1:expression}, ${2:object})
```

#### `coc⇥` console.clear
```js
console.clear()
```

#### `coct⇥` console.count
```js
console.count(${1:label})
```

#### `cod⇥` console.dir
```js
console.dir(${1:object})
```

#### `coe⇥` console.error
```js
console.error(${1:object})
```

#### `cog⇥` console.group
```js
console.group(\"${1:label}\")
```

#### `coge⇥` console.groupEnd
```js
console.groupEnd()
```

#### `coi⇥` console.info
```js
console.info(${1:object})
```

#### `col⇥` console.log
```js
console.log(${1:object})
```

#### `cot⇥` console.trace
```js
console.trace(${1:object})
```

#### `cow⇥` console.warn
```js
console.warn(${1:object})
```


### DOM

#### `aev⇥` addEventListener
```js
${1:document}.addEventListener('${2:event}', ${3:ev} => {
  ${0}
})
```

#### `rev⇥` removeEventListener
```js
${1:document}.removeEventListener('${2:event}', ${3:listener})
```

#### `evon⇥` attach an event handler
```js
${1:emitter}.on('${2:event}', (${3:arguments}) => {
  ${0}
})
```

#### `evc` dom event cancel default and propagation
```js
ev.preventDefault()
ev.stopPropagation()
return false
```

#### `gi⇥` getElementById
```js
${1:document}.getElementById('${2:id}')
```

#### `gc⇥` getElementsByClassName
```js
Array.from(${1:document}.getElementsByClassName('${2:class}'))
```

#### `gt⇥` getElementsByTagName
```js
Array.from(${1:document}.getElementsByTagName('${2:tag}'))
```

#### `qs⇥` querySelector
```js
${1:document}.querySelector('${2:selector}')
```

#### `qsa⇥` querySelectorAll
```js
Array.from(${1:document}.querySelectorAll('${2:selector}'))
```

#### `cdf⇥` createDocumentFragment

```js
${1:document}.createDocumentFragment(${2:elem});
```

#### `cel⇥` createElement

```js
${1:document}.createElement(${2:elem});
```

#### `ach⇥` appendChild

```js
${1:document}.appendChild(${2:elem});
```

#### `rch⇥` removeChild

```js
${1:document}.removeChild(${2:elem});
```

#### `clad⇥` classList.add

```js
${1:document}.classList.add('${2:class}');
```

#### `clr⇥` classList.remove

```js
${1:document}.classList.remove('${2:class}');
```

#### `clt⇥` classList.toggle

```js
${1:document}.classList.toggle('${2:class}');
```

#### `ga⇥` getAttribute

```js
${1:document}.getAttribute('${2:attr}');
```

#### `sa⇥` setAttribute

```js
${1:document}.setAttribute('${2:attr}', ${3:value});
```

#### `ra⇥` removeAttribute

```js
${1:document}.removeAttribute('${2:attr}');
```

# License

The MIT License (MIT)

Copyright (c) 2016, [Jiří Špác](http://github.com/capaj)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NON INFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
