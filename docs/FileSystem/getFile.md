<!--bl
    (filemeta
        (title "Get File")
    )
/bl-->
This returns an `IFileWrapper` with the ability to configure delete event capturing.

The signature for this function is:

```f#
// FileEventHandlers -> DirectoryEventHandlers -> string -> IFileWrapper
let getFile fileEventHandlers dirEventHandlers path : IFileWrapper
```

The `FileEventHandlers` has the following structure:

```f#
type FileEventHandlers = {
    BeforeDelete : (IFileWrapper -> unit) option
    AfterDelete : (IFileWrapper -> unit) option
}
```

This allows access to information about the file before and after delete.

The `DirectoryEventHandlers` look very similar:

```f#
type DirectoryEventHandlers = {
    BeforeDelete : (IDirectoryWrapper -> unit) option
    AfterDelete : (IDirectoryWrapper -> unit) option
}
```

This allows access to the information about the directory before and after delete.