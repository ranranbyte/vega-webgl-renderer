WebGL renderer for [Vega](https://vega.github.io/vega)
======================================================

[Demo](https://vega.github.io/vega-webgl-renderer)

Major features
--------------

* Implements nearly all Vega scene graph components as WebGL primitives. Falls
  back to 2D Canvas rendering for text and gradient fills, which are drawn to
  a WebGL texture and overlaid on the view.
* Custom shaders for Rect and Symbol marks, enabling greater scalability
  (to the hundreds of thousands) beyond Canvas and SVG renderers. See the
  "scale" example in the demo (Note: Do not attempt that example with the
  SVG renderer, it will lock your browser for a while).


Build
-----

```
npm install
npm run build
```

Test
----

Testing requires that the Selenium server is running with the Chrome driver installed.
To run all tests:

```
npm run test
```

To just run the linter:

```
npm run lint
```

Contributing
------------

Please try it out and let us know how it works for you.
Bug reports, feature and improvement ideas, and PRs welcome.

This code is built and maintained by the [Kitware](http://www.kitware.com)
[Resonant](http://resonant.kitware.com) team in collaboration with the
[UW Interactive Data Lab](https://idl.cs.washington.edu/). The work is supported
by the DARPA AFRL [XDATA](http://opencatalog.darpa.mil/XDATA.html) program.

Known issues
------------

* Line dashes are not supported (see "barley", "nested-plot", "map-bind" examples).
* Triangulation of trails is known to be buggy and leave holes at internal nodes.
* Custom symbol shapes are not supported.
* Triangulation of geometry sometimes results in spurious offshoots.

Notes
-----

There is one minor change to [extrude-polyline](https://github.com/mattdesl/extrude-polyline/compare/master...jeffbaumes:closed-path)
which hacks in a way to close mitered strokes, which has not been merged upstream.
