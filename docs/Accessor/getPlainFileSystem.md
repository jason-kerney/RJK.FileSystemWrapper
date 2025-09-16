<!-- (dl (section-meta Get Plain File System)) -->
This returns a `IFileSystemAccessor` with no events configured for capture.

The signature of this method is as follows:

```f#
// unit -> IFileSystemAccessor
let getPlainFileSystem () : IFileSystemAccessor
```