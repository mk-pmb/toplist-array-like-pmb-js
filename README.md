
<!--#echo json="package.json" key="name" underline="=" -->
toplist-array-like-pmb
======================
<!--/#echo -->

<!--#echo json="package.json" key="description" -->
Mostly an array, but .push() inserts to the proper position by score, and
drops items that exceed the maximum length.
<!--/#echo -->



API
---

This module exports one function that also acts as a namespace other stuff:

### makeToplist(initialItems, opt)

`initialItems` should be either false-y
or something with an Array-like `.forEach` method.

`opt` is an optional options object that supports these optional keys:

* `scoreFunc`: Should be either false-y or a function that calculates a
  report about new items to be added.
  False-y values are equivalent to giving the identity function:
  The new value itself will be used as the score report.
* `scoreKey`: Name (as string) of the property of the score report
  (see `scoreFunc` above) whose value, converted to a number, shall be
  the score.
  Default: `undefined` = Assume the report is just a number.
  If `scoreFunc` and `scoreKey` both are `undefined`,
  the items to be added should all just be numbers.
* `maxLength`: Intended maximum length for the list.
  False-y values (even number 0!) mean infinite.

Returns an array whose `.push` is `makeToplist.pushOntoThis`,
has all the `opt` assigned onto it,
and all potential `initialItems` have been `.push()`ed.







Usage
-----

see [test/usage.mjs](test/usage.mjs).
from [test/usage.mjs](test/usage.mjs):
:TODO:

<!--!#include file="test/usage.mjs" transform="mjsUsageDemo1802" -->
<!--!#include file="test/usage.mjs" outdent="  " code="javascript"
  start="  // #BEGIN# usage demo" stop="  // #ENDOF# usage demo" -->
```javascript
var toplist-array-like-pmb = require('toplist-array-like-pmb');
D.result  = toplist-array-like-pmb(null);
D.expect('===',           null);
```
<!--/include-->

```bash
$ toplist-array-like-pmb foo
bar
```


<!--#toc stop="scan" -->



Known issues
------------

* Needs more/better tests and docs.




&nbsp;


License
-------
<!--#echo json="package.json" key=".license" -->
ISC
<!--/#echo -->
