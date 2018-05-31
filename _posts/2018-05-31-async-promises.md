---

 title: Resolving Promises

---

# Asynchronicity in JavaScript

Yes, asynchronicity is a word. I verified it with a Google search, which also revealed its increasing importance in the JavaScript realm, as half of the top search results were related to JavaScript. And in JavaScript, asynchronous functions are heavily tied to `Promises`.

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)is an object that represents the yet to be determined value of an asynchronous operation. A `Promise` has three potential states: 

* unfulfilled/pending: the initial state, when a `Promise` has not been rejected but has yet to be fulfilled
* fulfilled: the asynchronous operation has reached successful completion and the pending `Promise` can be fulfilled with a value
* rejected: the asynchronous operation has failed and the pending `Promise` can return a reason for the error

[MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) supplies the following syntax for the `Promise` constructor:

`new Promise( /* executor */ function(resolve, reject) { ... } );`

The `executor` function is executed immediately, and usually initiates the asynchronous operation. It takes the `resolve` and `reject` functions as arguments because, upon completion of that asynchronous operation, it calls `resolve` or `reject` to change the state of the `Promise`. If the `Promise` is resolved, it is considered fulfilled and a value can be returned. If the `Promise` is rejected, and error can be thrown.

A promise chain can be created by chaining [`.then()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then) to a returned `Promise`, allowing the return value of a fulfilled `Promise` to be passed into subsequent functions. In this chain, [`.catch()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/catch) "catches" errors thrown by a rejected `Promise`. Using React and Redux, with [thunk middleware](https://github.com/reduxjs/redux-thunk), this pattern could be implemented within an action creator as follows: 

```javascript
export const fetchCats = () => {
  return dispatch => {
    return fetch(URL)
      .then(response => response.json())
      .then(function(cats) {
        let mappedResponse = mapCats(cats);
        return mappedResponse
      })
      .then(async (mappedResponse) => {
        let kitties = await Promise.all(mappedResponse.map((cat) => {
          return createCat(cat);
        }))
        // Always return results so they are available to the next element in the promise chain
        return kitties
      })
      .then(function(kitties) {
          dispatch(addCats(kitties))
        })
      .then(function() {
        dispatch(clearGame())
      })
      .then(function() {
        dispatch(playGame())
      })
      .catch(error => window.alert("Not enough kitties!"));
  };
};
```

The example implements a couple other promise-related elements: 

* [`async`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function): Introduced in ES 2017, `async` can be prepended to a function to return a `Promise` and resolve or reject it as needed (without the explicit `resolve` or `reject` of the `Promise` constructor)
* `await`: Also introduced in ES 2017, `await` can be used in conjunction with `async` to pause the execution of the `async` function until the `Promise` that follows `await` is resolved. While `async` can be used without `await`, the latter can *only* be used within an `async` function.
* [`Promise.all`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all): Is used with iterables and returns a *single* promise when all promises present in the iterable argument have been resolved. Upon any rejection, it rejects with the reason. The best part, `Promise.all` not only returns a `Promise`, but preserves the order of the input, if the input is strictly ordered (i.e. an array).

There are a variety of ways to [use promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises) in JavaScript. And the composition of one's approach largely depends on 1) which version of JavaScript is used throughout the rest of the code-base (always good to maintain consistency), 2) which approach will provide the intended results with the greatest amount of clarity and readability (callbacks can get messy). 

For the usage of `async` and `await`, [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) provides a succinct determiner for usage:

> The purpose of `async`/`await` functions is to simplify the behavior of using promises synchronously and to perform some behavior on a group of `Promises`. Just as `Promises` are similar to structured callbacks, `async`/`await` is similar to combining generators and promises.

In the example above, there are other ways to work through an array of `Promises` but none would be as clean as prepending it with `Promise.all`. There is potential for enhancement in the realm of error/rejection handling as more `.catch()` statements could be added, to make debugging the promise chain easier. But, otherwise, it's asynchronicity in action!



