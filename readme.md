
<!-- GENERATED DOCUMENT! DO NOT EDIT! -->
# File System Wrapper #

## Table Of Contents ##

- [Section 1: Introduction](#user-content-introduction)
- [Section 2: Builder.Accessor](#user-content-builder.accessor)
- [Section 3: Thanks to all Contributors](#user-content-thanks-to-all-contributors)

## Introduction ##

RJK.FileSystem is a functional wrapper around the .Net File System. This allows all calls to appropriately curry the parameters and work form functions.

There are two basic entry points into this library.

`Builder.Accessor` which wraps all the static file system methods to allow for curried parameters.
`Builder.FileSystem` which wraps all the object based file system methods.
    

## Builder.Accessor ##
This is a functional wrapper around the static .Net FileSystem calls.

### Get Plain File System ###
This returns a `IFileSystemAccessor` with no events configured for capture.

The signature of this method is as follows:

```f#
// unit -> IFileSystemAccessor
let getPlainFileSystem () : IFileSystemAccessor
```
    

### Get File System ###
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

This allows access to a file before and after delete.

The `DirectoryEventHandlers` look very similar:

```f#
type DirectoryEventHandlers = {
    BeforeDelete : (IDirectoryWrapper -> unit) option
    AfterDelete : (IDirectoryWrapper -> unit) option
}
```

And this lets you have access to a Directory before and after it is deleted.
    
    

## Thanks to all Contributors ##
## Contributors

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/edf-re"><img src="https://avatars.githubusercontent.com/u/13739273?v=4?s=100" width="100px;" alt=""/><br /><sub><b>EDF Renewables</b></sub></a><br /><a href="#financial-edf-re" title="Financial">💵</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
    

<!-- GENERATED DOCUMENT! DO NOT EDIT! -->
    