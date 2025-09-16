<!-- (dl (section-meta Get Plain Directory)) -->
This will return an `IDirectoryWrapper` without event handlers configured to capture delete events.

This method has the following signature:

```f#
// string -> IDirectoryWrapper
let getPlainDirectory path : IDirectoryWrapper
```