# Advanced Functions

#### Functions are Values

Functions are values, just like numbers, strings, arrays and objects.
They can be saved to variables:

```javascript
var say_hi = function () {
  console.log('hi');
};

var greeter = say_hi;

say_hi();
greeter();

say_hi = function () {
  console.log('meh');
};

say_hi(); // ??
greeter(); // ??
```



#### Passing Functions to Functions

Functions can be passed as arguments to other functions. These are called callback functions

```javascript
var runner = function (fn) {
  console.log('Invoking a function now!');
  fn();
};

runner( function(){ console.log('okay'); } );
runner(say_hi);
runner(greeter);

runner( say_hi() ); // ??
```



#### Returning Functions from Functions

Not only can functions be passed as inputs, they can also be returned as outputs.

```javascript
var returns_a_func = function () {
  return function(){ console.log('BOOP!'); };
};

// have we booped yet?
var booper = returns_a_func();

// how about now?
booper();
```



# Higher Order Functions

Higher order functions either

1. Take a callback function as input

   ```javascript
   $('#button').on('click', function(){
     console.log('The button has been clicked.');
   })
   ```

2. Return a function as an output

   ```javascript
   var add = function(num){
     var num1 = num;

     return addToNum1 = function(num2){
       return num1 + num2;
     };
   };

   var invokeLater = add(5);

   invokeLater(7) //12
   ```



#### Composability

It is often desirable to create generalized functions which take callback functions. We can use these generalized functions, often called **utility functions**, to compose higher order functions which do more specific tasks.

```javascript
var doMathSoIDontHaveTo = function(n, func){ return func(n); };

var increment = function(n){ return n + 1; };

var square = function(n){ return n*n; };

doMathSoIDontHaveTo(5, square);
doMathSoIDontHaveTo(4, increment);
```



Here's another example:

```javascript
var ifThen = function(condition, isTrue, isFalse, arg){
  if(condition (arg)){
    isTrue(arg);
  } else {
    isFalse(arg);
  }
};

var condition = function(number){ return number % 2 === 0 };
var isTrue = function(number){ return "even" };
var isFalse = function(number){ return "odd"};

var oddOrEven = function(array){
  for (var i = 0; i < array.length; i++){
  	array[i] = ifThen(number); 
  }
}

```



Let's refactor the last bit of code using forEach. forEach is chained to an array and takes one callback function as an argument.  The callback is called at each iteration with the current element of the array. 

```javascript
array.forEach(callback); 

var range = [1,2,3,4,5,6];

range.forEach(oddOrEven(number)) //['odd', 'even', 'odd', 'even','odd', 'even'];
```





# Scope

Function define their own local scope. Variables declared within a function invocation are available only inside of that function.  It's as if invocations are surrounded by one-way mirrors, they can see out and access variables named in their parent scope, but code running outside can't see in to access parameters or  variables defined inside.



```javascript
var word = 'original';
var phrase = " is the word";

var word_changer = function (new_word) {
    var word = new_word;
    console.log(word + phrase);
};

console.log(word + phrase); // ??
console.log(new_word + phrase); // ??
word_changer('changed');
console.log(word + phrase); // ??
console.log(new_word + phrase); // ??

// what's different here?
var leaky_word_changer = function (new_word) {
    word = new_word;
    console.log(word + phrase);
};

leaky_word_changer('changed');
console.log(word + phrase); // ??
console.log(new_word + phrase); // ??
```



# The Arguments Object

The arguments object: As we saw in the first lecture on functions, any argument you pass to a function is added to the arguments object. The arguments object is accessible through the arguments keyword.
The arguments keyword refers to the arguments object of the scope it belongs to. 

```javascript
var  noParams = function(){
  console.log(arguments);
  for (var i = 0; i < arguments.length; i++){
    console.log(arguments[i]);
  }
}

noParams(1,2,3,4,5,6,7,8,9,10);

var noParams = function(){
  var newArgs = Array.prototype.slice.call(arguments, 4);
  var  inner = function(){
  console.log(arguments);
    for (var i = 0; i < arguments.length; i++){
      console.log(arguments[i]);
    }
  };
  inner.apply(null, newArgs);
};

noParams(1,2,3,4,5,6,7,8,9,10);
```



### Further Functional JS Resources

**LearnRX**

http://reactivex.io/learnrx/

****

**Functional Javascript Workshop**

https://github.com/timoxley/functional-javascript-workshop/



