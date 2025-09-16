<!-- GENERATED DOCUMENT DO NOT EDIT! -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->

<!-- Compiled with doculisp https://www.npmjs.com/package/doculisp -->
<!-- Written By: Jason Kerney -->

# File System Wrapper #

## Table of Contents ##

1. Section: [Introduction](#introduction)
2. Section: [Builder.Accessor](#builderaccessor)
3. Section: [Builder.FileSystem](#builderfilesystem)
4. Section: [Thanks to all Contributors](#thanks-to-all-contributors)

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

This allows access to information about the file before and after delete.

The `DirectoryEventHandlers` look very similar:

```f#
type DirectoryEventHandlers = {
    BeforeDelete : (IDirectoryWrapper -> unit) option
    AfterDelete : (IDirectoryWrapper -> unit) option
}
```

This allows access to the information about the directory before and after delete.

## Builder.FileSystem ##

This is a functional wrapper around the file system objects in .NET

### Get Plain Directory ###

This will return an `IDirectoryWrapper` without event handlers configured to capture delete events.

This method has the following signature:

```f#
// string -> IDirectoryWrapper
let getPlainDirectory path : IDirectoryWrapper
```

### Get Directory ###

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

### Get Plain File ###

This returns an `IFileWrapper` without any events configured for capture.

This has the following signature:

```f#
// string -> IFileWrapper
let getPlainFile path : IFileWrapper
```

### Get File ###

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

## Thanks to all Contributors ##

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<table>
  <tr>
    <td align="center"><a href="https://github.com/edf-re"><img src="https://avatars.githubusercontent.com/u/13739273?v=4?s=100" width="100px;" alt=""/><br /><sub><b>EDF Renewables</b></sub></a><br /><a href="#financial-edf-re" title="Financial">💵</a></td>
  </tr>
</table>

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!

<!-- Written By: Jason Kerney -->
<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->
<!-- GENERATED DOCUMENT DO NOT EDIT! -->