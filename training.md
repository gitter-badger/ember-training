# EmberJS Training

Prepared by Katie Gengler, [Code All Day Consulting](http://www.codeallday.com)

## Review of JavaScript

## Intro to ES2015 Features used prominently in Ember Apps
 - ### [BabelJS](https://babeljs.io/docs/learn-es2015/)

 - ### [`let` and `const`](https://babeljs.io/docs/learn-es2015/#let-const)
     ```js
 var x = 'Global';
 function test(){
     console.log(x);
     var x = 'Local';
     console.log(x);
 }
 test();
 > undefined
 > 'Local'
     ```
     The above is equivalent to the following, thanks to hoisting:
     ```js
 var x = 'Global';
 function test(){
     var x;
     console.log(x);
     x = 'Local';
     console.log(x)
 }
     ```

     Enter `let`, which has block scope.

 ```js
  function varTest() {
     var x = 31;
     if (true) {
       var x = 71;  // same variable!
       console.log(x);  // 71
     }
     console.log(x);  // 71
  }

  function letTest() {
     let x = 31;
     if (true) {
       let x = 71;  // different variable
       console.log(x);  // 71
     }
     console.log(x);  // 31
  }
// This example is from: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let
 ```

     `const` is also block-scoped but cannot be re-assigned or redeclared.

 - ### [Template Strings](https://babeljs.io/docs/learn-es2015/#template-strings)
 ```js
   var aboutTime = 'about damn time';
   console.log(`JavaScript has interpolation, ${aboutTime}.`);
   > JavaScript has interpolation, about damn time.
 ```
 - ### [Default parameters](https://babeljs.io/docs/learn-es2015/#default-rest-spread)
 ```js
  function increase(a, b=1){
    return a + b;
  }
 ```
 - ### [Rest](https://babeljs.io/docs/learn-es2015/#default-rest-spread)
 ```js
  function concat(...strs){
    var result = '';
    strs.forEach(function(str){
      result += str;
    });
    return result;
  }
 ```
 - ### [Spread](https://babeljs.io/docs/learn-es2015/#default-rest-spread)
 ```js
   function fullName(first, last) {
     return `${first} ${last}`;
   }
   var names = ['Jane', 'Smith'];
   fullName(...names);
 ```

 - ### [Destructuring](https://babeljs.io/docs/learn-es2015/#destructuring)
 ```js
   var [a, b] = [1, 2];

   ---

   var a = 1;
   var b = 5;
   [a, b] = [b, a];

   function nums() {
     return [1, 2, 3];
   }

   var [, b, c] = nums();
 ```

 ```js
   var person = {name: 'Jane', age: 87};
   var {name, age} = person;
 ```

 ```js
  function log({level: level = 'info', text: ''} = {}){
    console[level](text);
  }
  log({text: 'Some info'});
  log({text: 'A warning', level: 'warn'});
 ```

 - ### [Arrow Functions](https://babeljs.io/docs/learn-es2015/#arrows-and-lexical-this)

  ```js
  var totals = [102, 55, 77];
  var totalsWithTax = totals.map(n => applyTax(n));

  var totalsWithTaxIfApplicable = totals.map(n => {
    if (taxAppliesTo(n)) {
      return applyTax(n);
    } else {
      return n;
    }
  });

  logError() => { console.log('Error'); }  
  ```

    no more `that`

  ```js
    function Invite(id){
      this.id = id;
      this.respondedTo = false;
      $.get(`/invites/${id}/`), (response) -> {
        this.respondedTo = response.respondedTo;
      });
    }
  ```
 - ### [Modules](https://babeljs.io/docs/learn-es2015/#modules)

  ```js
    // `utils/pluralize.js`
    export default function(str) {
      return str.pluralize();
    }
    // `app/home.js`
    import pluralize from '../utils/pluralize';
  ```

  ```js

    // `utils/string-helpers.js`
    export function pluralize(str) {
      //...
    };

    export function concat(str1, str2) {
      //...
    };

    // `app/home.js`
    import * as strHelpers from '../utils/string-helpers';
    strHelpers.pluralize('thing');

    import {pluralize} from '../utils/string-helpers';
    pluralize('thing');


    import {pluralize} from '../utils/string-helpers';
    pluralize('thing');

    import './domReady';

    import Ember from 'ember';
  ```

## EmberCLI
### Broccoli
### npm
### bower
### jscs & jshint

## Community Resources

## The Ember Object Model

## Github issues clone

## The Router
## Ember Data
## Components
## Async
## Testing
## Addons

## Tour of your app & deployment
