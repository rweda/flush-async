# Flush Async

[![Build Status](https://travis-ci.org/rweda/flush-async.svg?branch=master)](https://travis-ci.org/rweda/flush-async)

Promisified `flush()` for `web-component-tester`.

Example:

```html
<!doctype html>
<html>
  <head>
    <script src="/components/webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="/components/flush-async/flush-async.html">
  </head>
  <body>
    <!-- ... -->
    <script>
      chai.should();
      
      it("should do something", () => {
        const items = list.countElements();
        list.append("new element"); // won't hit DOM immediately
        return flushAsync()
          .then(() => list.countElements().should.equal(items + 1));
      });
    </script>
  </body>
</html>
```

## Installation

```sh
bower install --save-dev rweda/flush-async
```
