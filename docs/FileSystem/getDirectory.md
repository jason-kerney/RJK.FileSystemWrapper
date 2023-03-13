<!--bl
    (filemeta
        (title "Get Directory")
    )
/bl-->
This returns an `IDirectoryWrapper` with events configured as you need them.

This call has the following signature:

```f#
// FileEventHandlers -> DirectoryEventHandlers -> string -> IDirectoryWrapper
let getDirectory fileEventHandlers dirEventHandlers path : IDirectoryWrapper
```

File Event Handlers looks like:

```f#
type FileEventHandlers = {
    BeforeDelete : (IFileWrapper -> unit) option
    AfterDelete : (IFileWrapper -> unit) option
}
```

This allows access to the information about the file before and after delete.

Directory Event Handlers looks like:

```f#
type DirectoryEventHandlers = {
    BeforeDelete : (IDirectoryWrapper -> unit) option
    AfterDelete : (IDirectoryWrapper -> unit) option
}
```

This allows access to the information about the directory before and after delete.