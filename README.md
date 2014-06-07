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
* Don't require a browser

### Example

```javascript
var limivorous = require('limivorous')

Tag = function(data) {
  "use strict";

  var self = limivorous.observable()
                       .property('id')
                       .property('name')
                       .property('color', { init: 'red' } )
                       .build()

  /** Add any functions or other private storage */

  return self
}

t = Tag()
t.on('change:name', function(e) {
  console.log('Name changed from ' + e.previous + ' to ' + e.value)
})
```

## Licence & copyright

Limivorous is copyright &copy; 2014 Adam Alpern and licenced under the
MIT licence. All rights not explicitly granted in the MIT license are
reserved. See the included LICENSE file for more details.
