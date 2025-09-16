<!-- (dl (section-meta Introduction)) -->

RJK.FileSystem is a functional wrapper around the .Net File System. This allows all calls to appropriately curry the parameters and work form functions.

There are two basic entry points into this library.

`Builder.Accessor` which wraps all the static file system methods to allow for curried parameters.
`Builder.FileSystem` which wraps all the object based file system methods.