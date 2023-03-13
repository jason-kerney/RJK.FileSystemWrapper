<!--bl
    (filemeta
        (title "Get Plain Directory")
    )
/bl-->
This will return an `IDirectoryWrapper` without event handlers configured to capture delete events.

This method has the following signature:

```f#
// string -> IDirectoryWrapper
let getPlainDirectory path : IDirectoryWrapper
```