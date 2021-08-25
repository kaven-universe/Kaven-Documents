﻿# KCmd

## Install

```sh
dotnet tool install --global KCmd
```

## Uninstall

```sh
dotnet tool uninstall KCmd -g
```

## Use

```sh
kcmd cmd RequiredParameters... [OptionalParameters...]
```

### Copy/cp

#### Syntax(Copy)

```sh
kcmd copy|cp src dest [name:value]
```

#### Required Parameters(Copy)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |
| dest     | file or directory |

#### Optional Parameters(Copy)

| Name                                | Alias | Default | Definition                                 |
| ----------------------------------- | ----- | ------- | ------------------------------------------ |
| AttributesToSkip                    |       | 0       | [AttributesToSkip](#attributes-to-skip)    |
| ExcludeFileNameStartsWith           |       |         |                                            |
| ExcludeFileNameStartsWithIgnoreCase |       |         |                                            |
| IgnoreInaccessible                  |       | true    | [IgnoreInaccessible](#ignore-inaccessible) |
| Include                             | I     |         | [Include](#include)                        |
| OverrideFile                        | O     | true    |                                            |
| Recursive                           | R     | false   |                                            |
| Silent                              | S     | false   |                                            |
| SrcSearchPattern                    |       | *       |                                            |

#### Remarks(Copy)

#### Examples(Copy)

```sh
kcmd copy xxx/file.src yyy/file.dest

kcmd copy xxx/src yyy/dest recursive
kcmd copy xxx/src yyy/dest -recursive
kcmd cp xxx/src yyy/dest r
kcmd cp xxx/src yyy/dest -r

kcmd cp xxx/src yyy/dest -r -OverrideFile:false
kcmd cp xxx/src yyy/dest -r -o:false

kcmd cp xxx/src yyy/dest -r SrcSearchPattern:*.txt ExcludeFileNameStartsWith:exclude_
```

### Move/mv

#### Syntax(Move)

```sh
kcmd move/mv src dest [name:value]
```

#### Required Parameters(Move)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |
| dest     | file or directory |

#### Optional Parameters(Move)

| Name                                | Alias | Default | Definition                                 |
| ----------------------------------- | ----- | ------- | ------------------------------------------ |
| AttributesToSkip                    |       | 0       | [AttributesToSkip](#attributes-to-skip)    |
| ExcludeFileNameStartsWith           |       |         |                                            |
| ExcludeFileNameStartsWithIgnoreCase |       |         |                                            |
| IgnoreInaccessible                  |       | true    | [IgnoreInaccessible](#ignore-inaccessible) |
| Include                             | I     |         | [Include](#include)                        |
| OverrideFile                        | O     | true    |                                            |
| Recursive                           | R     | false   |                                            |
| Silent                              | S     | false   |                                            |
| SrcSearchPattern                    |       | *       |                                            |

#### Remarks(Move)

#### Examples(Move)

```sh
kcmd move xxx/file.src yyy/file.dest

kcmd move xxx/src yyy/dest recursive
kcmd move xxx/src yyy/dest -recursive
kcmd mv xxx/src yyy/dest r
kcmd mv xxx/src yyy/dest -r

kcmd mv xxx/src yyy/dest -r SrcSearchPattern:*.txt ExcludeFileNameStartsWith:exclude_
```

### Delete/rm

#### Syntax(Delete)

```sh
kcmd delete/rm src [name:value]
```

#### Required Parameters(Delete)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |

#### Optional Parameters(Delete)

| Name                                | Alias | Default | Definition                                 |
| ----------------------------------- | ----- | ------- | ------------------------------------------ |
| AttributesToSkip                    |       | 0       | [AttributesToSkip](#attributes-to-skip)    |
| ExcludeFileNameStartsWith           |       |         |                                            |
| ExcludeFileNameStartsWithIgnoreCase |       |         |                                            |
| IgnoreInaccessible                  |       | true    | [IgnoreInaccessible](#ignore-inaccessible) |
| Include                             | I     |         | [Include](#include)                        |
| OverrideFile                        | O     | true    |                                            |
| Recursive                           | R     | false   |                                            |
| Silent                              | S     | false   |                                            |
| SrcSearchPattern                    |       | *       |                                            |

#### Remarks(Delete)

#### Examples(Delete)

```sh
kcmd delete xxx/file.txt
kcmd rm xxx/file.txt

kcmd delete xxx/dir recursive
kcmd delete xxx/dir -recursive
kcmd rm xxx/dir r
kcmd rm xxx/dir -r

kcmd rm xxx/src -r SrcSearchPattern:*.txt ExcludeFileNameStartsWith:exclude_
```

### Archive

#### Syntax(Archive)

```sh
kcmd archive src [name:value]
```

#### Required Parameters(Archive)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |

#### Optional Parameters(Archive)

| Name                                | Alias | Default  | **Definition**                             |
| ----------------------------------- | ----- | -------- | ------------------------------------------ |
| AttributesToSkip                    |       | 0        | [AttributesToSkip](#attributes-to-skip)    |
| CompressionLevel                    |       | Optimal  | [CompressionLevel](#compression-level)     |
| Dest                                | D     |          |                                            |
| Encoding                            | E     | utf-8    | [Encoding](#encoding)                      |
| ExcludeBaseDirectory                |       | true     |                                            |
| ExcludeFileNameStartsWith           |       |          |                                            |
| ExcludeFileNameStartsWithIgnoreCase |       |          |                                            |
| IgnoreInaccessible                  |       | true     | [IgnoreInaccessible](#ignore-inaccessible) |
| Include                             | I     |          | [Include](#include)                        |
| IncludeBaseDirectory                |       | false    |                                            |
| OverrideFile                        | O     | true     |                                            |
| Recursive                           | R     | **true** |                                            |
| Silent                              | S     | false    |                                            |
| SrcSearchPattern                    |       | *        |                                            |

#### Remarks(Archive)

- `IncludeBaseDirectory` and `ExcludeBaseDirectory` cannot be used at the same time.

```sh
kcmd archive ./ SrcSearchPattern:*.txt AttributesToSkip:Hidden
kcmd archive ./ SrcSearchPattern:*.uff "AttributesToSkip:Hidden, System"
```

#### Examples(Archive)

```sh
kcmd archive xxx/file.txt

kcmd archive xxx/file.txt Dest:file.zip
kcmd archive xxx/file.txt dest:file.zip
kcmd archive xxx/file.txt D:file.zip
kcmd archive xxx/file.txt d:file.zip
kcmd archive xxx/file.txt -Dest:file.zip
kcmd archive xxx/file.txt -dest:file.zip
kcmd archive xxx/file.txt -D:file.zip
kcmd archive xxx/file.txt -d:file.zip

kcmd archive xxx/dir

kcmd archive xxx/dir Dest:yyy/file.zip CompressionLevel:Fastest ExcludeBaseDirectory Recursive

kcmd archive xxx/dir Include:file-list.txt
```

### Archive-Extract/Extract

#### Syntax(Archive-Extract)

```sh
kcmd archive-extract/extract src [name:value]
```

#### Required Parameters(Archive-Extract)

| Position | Value             |
| -------- | ----------------- |
| src      | zip file          |

#### Optional Parameters(Archive-Extract)

| Name                                | Alias | Default | **Definition**        |
| ----------------------------------- | ----- | ------- | --------------------- |
| Dest                                | D     |         |                       |
| Encoding                            | E     | utf-8   | [Encoding](#encoding) |
| ExcludeFileNameStartsWith           |       |         |                       |
| ExcludeFileNameStartsWithIgnoreCase |       |         |                       |
| OverrideFile                        | O     | true    |                       |
| Silent                              | S     | false   |                       |

#### Examples(Archive-Extract)

```sh
kcmd archive-extract xxx/file.zip
kcmd extract xxx/file.zip

kcmd extract xxx/file.zip Dest:yyy/dir

kcmd extract xxx/file.zip Dest:yyy/dir Encoding:gb2312
kcmd extract xxx/file.zip Dest:yyy/dir Encoding:936
kcmd extract xxx/file.zip Dest:yyy/dir -E:gb2312
kcmd extract xxx/file.zip Dest:yyy/dir e:936
```

## Common Parameters

### Compression Level

- [CompressionLevel](https://docs.microsoft.com/en-us/dotnet/api/system.io.compression.compressionlevel?view=net-5.0)

| Name          | Value | Description                                                  |
| ------------- | ----- | ------------------------------------------------------------ |
| Fastest       | 1     | The compression operation should complete as quickly as possible, even if the resulting file is not optimally compressed. |
| NoCompression | 2     | No compression should be performed on the file.              |
| Optimal       | 0     | The compression operation should be optimally compressed, even if the operation takes a longer time to complete. |

### Include

Use `Include` to include multiple files/directories under the `Src` directory.

file-list.txt(relative to `Src`):

```txt
dir1
dir3/file1
dir5/subDir/
file
...
```

```sh
kcmd mv xxx/src_dir yyy/dest_dir -include:file-list.txt
kcmd cp xxx/src_dir yyy/dest_dir Include:file-list.txt
kcmd rm xxx/src_dir I:file-list.txt
kcmd archive xxx/src_dir i:file-list.txt
```

### Attributes To Skip

- [AttributesToSkip](https://docs.microsoft.com/en-us/dotnet/api/system.io.enumerationoptions.attributestoskip?view=net-5.0)

### File Attributes

- [FileAttributes](https://docs.microsoft.com/en-us/dotnet/api/system.io.fileattributes?view=net-5.0)

| Name              | Value  | Description                                                  |
| ----------------- | ------ | ------------------------------------------------------------ |
| Archive           | 32     | This file is marked to be included in incremental backup operation. Windows sets this attribute whenever the file is modified, and backup software should clear it when processing the file during incremental backup. |
| Compressed        | 2048   | The file is compressed.                                      |
| Device            | 64     | Reserved for future use.                                     |
| Directory         | 16     | The file is a directory. `Directory` is supported on Windows, Linux, and macOS. |
| Encrypted         | 16384  | The file or directory is encrypted. For a file, this means that all data in the file is encrypted. For a directory, this means that encryption is the default for newly created files and directories. |
| Hidden            | 2      | The file is hidden, and thus is not included in an ordinary directory listing. `Hidden` is supported on Windows, Linux, and macOS. |
| IntegrityStream   | 32768  | The file or directory includes data integrity support. When this value is applied to a file, all data streams in the file have integrity support. When this value is applied to a directory, all new files and subdirectories within that directory, by default, include integrity support. |
| Normal            | 128    | The file is a standard file that has no special attributes. This attribute is valid only if it is used alone. `Normal` is supported on Windows, Linux, and macOS. |
| NoScrubData       | 131072 | The file or directory is excluded from the data integrity scan. When this value is applied to a directory, by default, all new files and subdirectories within that directory are excluded from data integrity. |
| NotContentIndexed | 8192   | The file will not be indexed by the operating system's content indexing service. |
| Offline           | 4096   | The file is offline. The data of the file is not immediately available. |
| ReadOnly          | 1      | The file is read-only. `ReadOnly` is supported on Windows, Linux, and macOS. On Linux and macOS, changing the `ReadOnly` flag is a permissions operation. |
| ReparsePoint      | 1024   | The file contains a reparse point, which is a block of user-defined data associated with a file or a directory. `ReparsePoint` is supported on Windows, Linux, and macOS. |
| SparseFile        | 512    | The file is a sparse file. Sparse files are typically large files whose data consists of mostly zeros. |
| System            | 4      | The file is a system file. That is, the file is part of the operating system or is used exclusively by the operating system. |
| Temporary         | 256    | The file is temporary. A temporary file contains data that is needed while an application is executing but is not needed after the application is finished. File systems try to keep all the data in memory for quicker access rather than flushing the data back to mass storage. A temporary file should be deleted by the application as soon as it is no longer needed. |

### Ignore Inaccessible

- [IgnoreInaccessible](https://docs.microsoft.com/en-us/dotnet/api/system.io.enumerationoptions.ignoreinaccessible?view=net-5.0)

### Encoding

- [List of encodings](https://docs.microsoft.com/en-us/dotnet/api/system.text.encoding?view=net-5.0#list-of-encodings)
