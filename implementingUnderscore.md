# Re-Implementing Underscore

Re-implement the following methods from underscore. You can reference the Underscore documentation for what they do as well as example usage. Underscore offers optional arguments for some of these methods. In those cases, follow the instructions here, rather than the Underscore documentation. 

1. `_.each` takes a collection and an iterator function and calls the `iterator(value, key, collection)` for each element of collection. It should accept both arrays and objects

2. `_.indexOf`   takes an array and a target value. It returns the index at which value can be found in the array, or -1 if value is not present in the array. Use `_.each` in your implementation

3. `_.filter` takes a collection and a predicate function, also known as a truth test. Return an array of all elements of the collection that pass the truth test, ie return a truthy value from the predicate function. Consider reusing `_.each` here. 

4. `_.reject` works similiarly to `_.filter` but returns an array of all elements that don't pass the truth test. Use `_.filter` in your implementation.

5. `_.uniq` produces a duplicate free version of an array. Use `_.filter` and `_.indexOf` in your implementation.

6. `_.map` works a lot like `_.each`. It takes a collection and iterator, and calls the iterator on every element of the array. However, `_.map` returns an results array of the transformed values. 

7. `_.pluck` takes an array of objects and returns an array of the values of a certain property in it. Ex. take an array of people objects and return an array of just their ages. Use `_.map` in your implementation.

8. `_.reduce` reduces an array or object to a single value by repetitively calling `iterator(accumulator, item)` for each item.  `accumulator` should be
     the return value of the previous iterator call. Reduce takes a collection, an iterator, and an optional third argument of a starting value. Where no starting value is provided, the first element is used as the starting value and the iterator is not  called on the first value. 

9. `_.every` determines whether all ements of a collection pass a truth test. It takes a collection and a predicate function. Use `_.reduce` in your implementation.

10. `_.some` determines whether some eleements of a collection pass a truth test. It takes a collection and a predicate function. You could use `_.reduce` here, but there is a clever way to re-use `_.every`. 

    ​

    ​

    ​

    ​