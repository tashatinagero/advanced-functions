##Callback exercises

1. Use _.each to loop through an array and console.log() all the values. Now use it to console.log() the indices. How would this be different if you were looping through an object?

2. Write a function `answer_logger` that takes a function as input, runs it, and places the return value from that function invocation into a div#answer

   We can test `answer_logger` using the following code, we should not need to change it at all:

   ```javascript
   answer_logger(function(){
     return "I should appear in div#answer!";
   });
   ```

3. Write a function `answer_collector` that takes an array of functions as an input and runs each of them, in turn. Each time you run a function, collect its return value and add it to a `results_array`. Return the results array from `answer_collector`.

   We can test `answer_collector` with this code:

   ```javascript
   var fn1 = function () {
     return "this should be the first value in results array";
   };

   answer_collector([fn1, function(){ return "this should be the second value in results array"; }]);
   ```

4. Write a function that pushes all the values in an object to an array.

   ```javascript
   input: {two: 2, four: 4, three: 3, twelve: 12}
   output: [2, 4, 3, 12]
   ```

5. Write a function that takes an array and a function as arguments and calls that function on every value in the array, and replaces the original value with the return value of the callback function: 

   ```javascript
   var doubler = function(value){return value * 2};
   input: [1,2,3,4,5], doubler
   output: [2,4,6,8,10]
   ```

6. Refactor that function so that instead of altering the input array, it returns a new array of transformed values. 

### Functional Programming with Underscore

Underscore is a JavaScript Library (like jQuery). It provides a bunch of pre-written code for solving common programming challenges. While jQuery helps web developers interact with the DOM, Underscore focuses on providing useful helpers for [Functional-style programming](http://en.wikipedia.org/wiki/Functional_programming).

Include the [Underscore library](http://underscorejs.org/) in an empty HTML document, along with an array of products (you can use your own from the e-commerce exercise or use [this one](http://remote-prep.herokuapp.com/students/products.js)) and try the following:

**first:** Pass `_.first()` the array of products and display the returned object in a "featured" section of your site.

**last:** Pass `_.last()` the array of products and display the returned object in a "clearance" section of your site.

**filter:** Use `_.filter()` to display only products that belong to the "books" category.

**reject:** Use `_.reject()` to display only products that are priced below $20.

**uniq:** Use `_.uniq()` to ensure that their are no duplicate selling points in any products before displaying them.

**map:** Use `_.map()` to grab the `picture_url` of all products for sale, assign each to the `src` property of a new `` tag and return that DOM element. Pass the result of calling `_.map()` directly into a`$('#container').append()` expression to create a photo montage.

**pluck:** Use `_.pluck()` to quickly retrieve a list of the names of all products for sale to list them in an index

**reduce:** Pass a shopping cart (array of objects) to `_.reduce()` and use it to add up the total price of the order.

**contains:** Determine if the order `_.contains()` a copy of 'Twilight'. If so, display a drastic message to the user asking them to re-evaluate their life choices.

**every:** Use `_.every()` to determine if every item in the order has a price tag less than $10. If so, call the user a cheapskate!

**some:** Use `_.some()` to determine if any item in the order has a price tag of $100 or more. If so, chide the user for their profligacy!

**extend:** Use `_.extend()` to merge two objects together. What would this be good for?



### Extra Credit

1. Write a function that pushes all the values in an object to an array. Sound familiar? Use _.map in your implementation this time. 

   ```javascript
   input: {two: 2, four: 4, three: 3, twelve: 12}
   output: [2, 4, 3, 12]
   ```

2. Use _.filter to return all the even numbers in an array.

   ```javascript
   input: [9,8,7,6,5,2]
   output: [8,6,2]
   ```

3. Use _.reduce to multiply all the values in an array.

   ```javascript
   input: [1,2,3,4]
   output: 24
   ```

4. Use _.reduce to concatenate all strings in an array.

   ```javascript
   input: ['x','y','z']
   output: 'xyz'
   ```

5. Given a string of only lowercase alphabet characters, find the character that occurs the highest number of times. If any characters tie, return them all in alphabetical order.

   ```javascript
   input: 'abcdc'
   output: 'c'

   input: "occurring"
   output: "cr"
   ```

   ​

   ​

   ​



