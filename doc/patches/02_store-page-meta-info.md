# Patch #2 (2024-05-13, 2024-04-10)
## Store page meta info of last loaded page


__Encountered problem__

When a page is loaded, additional meta info like file path can be very helpful, so this information should be provided.

__How to reproduce__

```js
document.addEventListener('init', function (event) {
    // The event only contains the element, but no other page details
});
```

__Solution__

```js
document.addEventListener('init', function (event) {
  console.log(event.target._meta); // provies additional info on the target element
    //  {
    //      PageLoader: {
    //          page: "views/example.html", 
    //          parent: HTMLElement, 
    //          params: {}
    //      }
    // }
});
```



Done with commits:
* Second attempt (2024-05-13) https://github.com/magynhard/OnsenUI/commit/5a0b41fc29fdc957e92d9c0c2d0fedf53ac6cc1f
* First attempt (2024-04-10) https://github.com/magynhard/OnsenUI/commit/b04374d9494c48b09235152aa2f6998a23e19685
