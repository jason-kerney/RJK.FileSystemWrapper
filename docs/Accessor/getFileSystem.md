<!--bl
    (filemeta
        (title "Get File System")
    )
/bl-->
This returns a `IFileSystemAccessor` with events configured to be captured.

This method has the following signature:

```f#
// FileEventHandlers -> DirectoryEventHandlers -> IFileSystemAccessor
let getFileSystem fileEventHandlers dirEventHandlers : IFileSystemAccessor
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