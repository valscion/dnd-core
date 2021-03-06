# dnd-core [![npm package](https://img.shields.io/npm/v/dnd-core.svg?style=flat-square)](https://www.npmjs.org/package/dnd-core) [![Build Status](https://travis-ci.org/gaearon/dnd-core.svg?branch=master)](https://travis-ci.org/gaearon/dnd-core) [![Test Coverage](https://codeclimate.com/github/gaearon/dnd-core/badges/coverage.svg)](https://codeclimate.com/github/gaearon/dnd-core) [![Join the chat at https://gitter.im/gaearon/dnd-core](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/gaearon/dnd-core?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)  


Drag and drop sans the GUI.  
Work in progress.

This is a clean re-implementation of drag and drop primitives and will eventually become core of [React DnD](https://github.com/gaearon/react-dnd).  

## Wat?

To give you a better idea:

* There is no DOM here
* We let you define drop target and drag source logic
* We let you supply custom underlying implementations (console, DOM via jQuery, React, React Native, *whatever*)
* We manage drag source and drop target interaction

This was written to support some rather complicated scenarios that were too hard to implement in [React DnD](https://github.com/gaearon/react-dnd) due to its current architecture:

* [Mocking drag and drop interaction in tests](https://github.com/gaearon/react-dnd/issues/55)
* [Full support for arbitrary nesting and handling drag sources and drop targets](https://github.com/gaearon/react-dnd/issues/87)
* [Dragging multiple items at once](https://github.com/gaearon/react-dnd/issues/14)
* [Even when source is removed, letting another drag source “represent it” (e.g. card disappeared from one Kanban list, reappeared in another one)](https://github.com/gaearon/react-dnd/pull/64#issuecomment-76118757)

Turns out, these problems are much easier to solve when DOM is thrown out of the window.

## What's the API like?

[Tests](https://github.com/gaearon/dnd-core/tree/master/modules/__tests__) should give you some idea. You register drag sources and drop targets, hook up a backend (you can use barebone `TestBackend` or implement a fancy real one yourself), and your drag sources and drop targets magically begin to interact.

![](http://i.imgur.com/6l8CpxZ.png)

