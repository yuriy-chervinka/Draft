# IT
Draft

## Table of Contents
- [Docker](#docker)

- [Features](#features)
- [Example](#example)
- [Philosophy](#philosophy)
- [Events](#events)
- [State](#state)
- [Routing](#routing)
- [Server Rendering](#server-rendering)
- [Components](#components)
- [Optimizations](#optimizations)
- [FAQ](#faq)
- [API](#api)
- [Installation](#installation)
- [See Also](#see-also)
- [Support](#support)



### Docker

#### Installation




## Features
- __minimal size:__ weighing `4kb`, Choo is a tiny little framework
- __event based:__ our performant event system makes writing apps easy
- __small api:__ with only 6 methods there's not much to learn
- __minimal tooling:__ built for the cutting edge `browserify` compiler
- __isomorphic:__ renders seamlessly in both Node and browsers
- __very cute:__ choo choo!

## Example
```js
var html = require('choo/html')
var devtools = require('choo-devtools')
var choo = require('choo')

var app = choo()
app.use(devtools())
app.use(countStore)
app.route('/', mainView)
app.mount('body')

function mainView (state, emit) {
  return html`
    <body>
      <h1>count is ${state.count}</h1>
      <button onclick=${onclick}>Increment</button>
    </body>
  `

  function onclick () {
    emit('increment', 1)
  }
}

function countStore (state, emitter) {
  state.count = 0
  emitter.on('increment', function (count) {
    state.count += count
    emitter.emit('render')
  })
}
```
Want to see more examples? Check out the [Choo handbook][handbook].

## Philosophy
We believe programming should be fun and light, not stern and stressful. It's
cool to be cute; using serious words without explaining them doesn't make for
better results - if anything it scares people off. We don't want to be scary,
we want to be nice and fun, and then _casually_ be the best choice around.
_Real casually._

We believe frameworks should be disposable, and components recyclable. We don't
want a web where walled gardens jealously compete with one another. By making
the DOM the lowest common denominator, switching from one framework to another
becomes frictionless. Choo is modest in its design; we don't believe it will
be top of the class forever, so we've made it as easy to toss out as it is to
pick up.

We don't believe that bigger is better. Big APIs, large complexities, long
files - we see them as omens of impending userland complexity. We want everyone
on a team, no matter the size, to fully understand how an application is laid
out. And once an application is built, we want it to be small, performant and
easy to reason about. All of which makes for easy to debug code, better results
and super smiley faces.

## Events
At the core of Choo is an event emitter, which is used for both application
logic but also to interface with the framework itself. The package we use for
this is [nanobus](https://github.com/choojs/nanobus).

You can access the emitter through `app.use(state, emitter, app)`, `app.route(route,
view(state, emit))` or `app.emitter`. Routes only have access to the
`emitter.emit` method to encourage people to separate business logic from
render logic.

The purpose of the emitter is two-fold: it allows wiring up application code
together, and splitting it off nicely - but it also allows communicating with
the Choo framework itself. All events can be read as constants from
`state.events`. Choo ships with the following events built in:

### `'DOMContentLoaded'`|`state.events.DOMCONTENTLOADED`
Choo emits this when the DOM is ready. Similar to the DOM's
`'DOMContentLoaded'` event, except it will be emitted even if the listener is
added _after_ the DOM became ready. Uses
[document-ready](https://github.com/bendrucker/document-ready) under the hood.

### `'render'`|`state.events.RENDER`
This event should be emitted to re-render the DOM. A common pattern is to
update the `state` object, and then emit the `'render'` event straight after.
Note that `'render'` will only have an effect once the `DOMContentLoaded` event
has been fired.

