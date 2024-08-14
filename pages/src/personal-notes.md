# Personal Notes
_This section is for the author to take notes while writing._

V2B should parse chained bindings into one binding. `'if'/'else if'/'else'` statements would compress to one single
"conditional" bin with a child for each comparison operation.

Use of `^` for functional bins. Functional bins are accessible from anywhere within any scene and view. Functional bins
will return values to the specified pool.


Viewbinder calls with a pool target will always resolve the scene to the left unless the pool type does not specify a
type, or the binding target is `throw`. Then it will resolve to the right and close to the left.

Viewbinder calls with no pool target will always close the scene to the left and resolve the scene to the right,
remaining out of scope.

Viewbinder calls should close in all directions if they have no value to return. Viewbinder calls should close to
the left and right and resolve downwards if an `ok` binding target is specified within any scene.


- Resolving right concludes in a loss of scope and no return value.
- Resolving downwards concludes in the returned value being passed to the end of the scene.
- Resolving left concludes in the returned value being passed into the parent scene. A functional bin can consume this
  value.