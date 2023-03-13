<!--bl
    (filemeta
        (title "Get Plain File")
    )
/bl-->
This returns an `IFileWrapper` without any envents configured for capture.

This has the following signature:

```f#
// string -> IFileWrapper
let getPlainFile path : IFileWrapper
```