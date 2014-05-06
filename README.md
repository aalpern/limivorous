# limivorous

 An implementation of the Observable pattern for simple Javascript
 data models. Yes, another implementation of Observable for
 Javascript.

**Why another Observable?**

There are lots of implementations of Observable for Javascript - why
right another one?

In part, as part of learning Javascript in a real project. And because
my needs for that project were quite simple, I wanted to work in bare
Javascript without pulling in a large framework. Many reactive
frameworks for Javascript bundle templating along with their data
modelling, and I wanted something simple that focused solely on the
data model and change events.

limivorous is intended to work with simple data model objects built
with the Javascript module pattern. The main requirements are:

* Support standard property get syntax, for compatibility with
  templating engines such as [handlebars](http://handlebarsjs.com/).
* Support a method chaining style or setting properties in addition to
  regular assignment.

## Example

```javascript
var limivorous = require('limivorous')

Tag = function(data) {
  "use strict";

  var storage = {}
    , self = {}

  limivorous.observable(self)
            .defineProperty(self, 'id', storage)
            .defineProperty(self, 'name', storage)
            .defineProperty(self, 'color', storage)

}
```
