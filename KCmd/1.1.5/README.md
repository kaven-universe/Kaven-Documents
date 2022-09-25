# [KCmd-1.1.5](https://doc.kaven.xyz/KCmd/1.1.5)

## Install

```sh
# install
dotnet tool install --global KCmd

# update
dotnet tool update KCmd -g

# uninstall
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

| Name                                | Alias | Default | Definition                                           |
| ----------------------------------- | ----- | ------- | ---------------------------------------------------- |
| AttributesToSkip                    |       | 0       | [AttributesToSkip](#attributes-to-skip)              |
| ExcludeExe                          |       | false   | [ExcludeExe](#exclude-exe)                           |
| ExcludeExeFiles                     |       | false   | [ExcludeExeFiles](#exclude-exe-files)                |
| ExcludeExeRelatedFiles              |       | false   | [ExcludeExeRelatedFiles](#exclude-exe-related-files) |
| ExcludeFileNameStartsWith           |       |         |                                                      |
| ExcludeFileNameStartsWithIgnoreCase |       |         |                                                      |
| IgnoreInaccessible                  |       | true    | [IgnoreInaccessible](#ignore-inaccessible)           |
| Include                             | I     |         | [Include](#include)                                  |
| OverrideFile                        | O     | true    |                                                      |
| Recursive                           | R     | false   |                                                      |
| Silent                              | S     | false   |                                                      |
| SrcSearchPattern                    |       | *       |                                                      |
| WhenDirectoryExists                 |       |         | [WhenDirectoryExists](#when-directory-exists)        |
| WhenDirectoryNotExists              |       |         | [WhenDirectoryNotExists](#when-directory-not-exists) |
| WhenFileExists                      |       |         | [WhenFileExists](#when-file-exists)                  |
| WhenFileNotExists                   |       |         | [WhenFileNotExists](#when-file-not-exists)           |

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

| Name                                | Alias | Default | Definition                                           |
| ----------------------------------- | ----- | ------- | ---------------------------------------------------- |
| AttributesToSkip                    |       | 0       | [AttributesToSkip](#attributes-to-skip)              |
| ExcludeExe                          |       | false   | [ExcludeExe](#exclude-exe)                           |
| ExcludeExeFiles                     |       | false   | [ExcludeExeFiles](#exclude-exe-files)                |
| ExcludeExeRelatedFiles              |       | false   | [ExcludeExeRelatedFiles](#exclude-exe-related-files) |
| ExcludeFileNameStartsWith           |       |         |                                                      |
| ExcludeFileNameStartsWithIgnoreCase |       |         |                                                      |
| IgnoreInaccessible                  |       | true    | [IgnoreInaccessible](#ignore-inaccessible)           |
| Include                             | I     |         | [Include](#include)                                  |
| OverrideFile                        | O     | true    |                                                      |
| Recursive                           | R     | false   |                                                      |
| Silent                              | S     | false   |                                                      |
| SrcSearchPattern                    |       | *       |                                                      |
| WhenDirectoryExists                 |       |         | [WhenDirectoryExists](#when-directory-exists)        |
| WhenDirectoryNotExists              |       |         | [WhenDirectoryNotExists](#when-directory-not-exists) |
| WhenFileExists                      |       |         | [WhenFileExists](#when-file-exists)                  |
| WhenFileNotExists                   |       |         | [WhenFileNotExists](#when-file-not-exists)           |

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

| Name                                | Alias | Default | Definition                                           |
| ----------------------------------- | ----- | ------- | ---------------------------------------------------- |
| AttributesToSkip                    |       | 0       | [AttributesToSkip](#attributes-to-skip)              |
| ExcludeExe                          |       | false   | [ExcludeExe](#exclude-exe)                           |
| ExcludeExeFiles                     |       | false   | [ExcludeExeFiles](#exclude-exe-files)                |
| ExcludeExeRelatedFiles              |       | false   | [ExcludeExeRelatedFiles](#exclude-exe-related-files) |
| ExcludeFileNameStartsWith           |       |         |                                                      |
| ExcludeFileNameStartsWithIgnoreCase |       |         |                                                      |
| IgnoreInaccessible                  |       | true    | [IgnoreInaccessible](#ignore-inaccessible)           |
| Include                             | I     |         | [Include](#include)                                  |
| OverrideFile                        | O     | true    |                                                      |
| Recursive                           | R     | false   |                                                      |
| Silent                              | S     | false   |                                                      |
| SrcSearchPattern                    |       | *       |                                                      |
| WhenDirectoryExists                 |       |         | [WhenDirectoryExists](#when-directory-exists)        |
| WhenDirectoryNotExists              |       |         | [WhenDirectoryNotExists](#when-directory-not-exists) |
| WhenFileExists                      |       |         | [WhenFileExists](#when-file-exists)                  |
| WhenFileNotExists                   |       |         | [WhenFileNotExists](#when-file-not-exists)           |

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

| Name                                | Alias | Default  | **Definition**                                       |
| ----------------------------------- | ----- | -------- | ---------------------------------------------------- |
| AttributesToSkip                    |       | 0        | [AttributesToSkip](#attributes-to-skip)              |
| CompressionLevel                    |       | Optimal  | [CompressionLevel](#compression-level)               |
| Dest                                | D     |          |                                                      |
| Encoding                            | E     | utf-8    | [Encoding](#encoding)                                |
| ExcludeBaseDirectory                |       | true     |                                                      |
| ExcludeExe                          |       | false    | [ExcludeExe](#exclude-exe)                           |
| ExcludeExeFiles                     |       | false    | [ExcludeExeFiles](#exclude-exe-files)                |
| ExcludeExeRelatedFiles              |       | false    | [ExcludeExeRelatedFiles](#exclude-exe-related-files) |
| ExcludeFileNameStartsWith           |       |          |                                                      |
| ExcludeFileNameStartsWithIgnoreCase |       |          |                                                      |
| IgnoreInaccessible                  |       | true     | [IgnoreInaccessible](#ignore-inaccessible)           |
| Include                             | I     |          | [Include](#include)                                  |
| IncludeBaseDirectory                |       | false    |                                                      |
| OverrideFile                        | O     | true     |                                                      |
| Recursive                           | R     | **true** |                                                      |
| Silent                              | S     | false    |                                                      |
| SrcSearchPattern                    |       | *        |                                                      |
| WhenDirectoryExists                 |       |          | [WhenDirectoryExists](#when-directory-exists)        |
| WhenDirectoryNotExists              |       |          | [WhenDirectoryNotExists](#when-directory-not-exists) |
| WhenFileExists                      |       |          | [WhenFileExists](#when-file-exists)                  |
| WhenFileNotExists                   |       |          | [WhenFileNotExists](#when-file-not-exists)           |

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

### Archive-Subdirectories/archive-sd

#### Syntax(Archive-Subdirectories)

```sh
kcmd archive-subdirectories src [name:value]
```

#### Required Parameters(Archive-Subdirectories)

| Position | Value             |
| -------- | ----------------- |
| src      | directory |

#### Optional Parameters(Archive-Subdirectories)

| Name                                | Alias         | Default  | **Definition**                                       |
| ----------------------------------- | -----         | -------- | ---------------------------------------------------- |
| CompressionLevel                    |               | Optimal  | [CompressionLevel](#compression-level)               |
| Dest                                | D             |          |                                                      |
| Encoding                            | E             | utf-8    | [Encoding](#encoding)                                |
| IncludeBaseDirectory                |               | false    |                                                      |
| OverrideFile                        | Override      | true     |                                                      |
| Silent                              | S             | false    |                                                      |
| DeleteSubdirectories                | Delete        | false    |                                                      |

#### Examples(Archive-Subdirectories)

```sh
kcmd archive-subdirectories ./publish
kcmd archive-subdirectories ./publish -d:./publish/zip/
kcmd archive-subdirectories ./publish IncludeBaseDirectory OverrideFile
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

| Name                                | Alias | Default | **Definition**                                       |
| ----------------------------------- | ----- | ------- | ---------------------------------------------------- |
| Dest                                | D     |         |                                                      |
| Encoding                            | E     | utf-8   | [Encoding](#encoding)                                |
| ExcludeExe                          |       | false   | [ExcludeExe](#exclude-exe)                           |
| ExcludeExeFiles                     |       | false   | [ExcludeExeFiles](#exclude-exe-files)                |
| ExcludeExeRelatedFiles              |       | false   | [ExcludeExeRelatedFiles](#exclude-exe-related-files) |
| ExcludeFileNameStartsWith           |       |         |                                                      |
| ExcludeFileNameStartsWithIgnoreCase |       |         |                                                      |
| OverrideFile                        | O     | true    |                                                      |
| Silent                              | S     | false   |                                                      |
| WhenDirectoryExists                 |       |         | [WhenDirectoryExists](#when-directory-exists)        |
| WhenDirectoryNotExists              |       |         | [WhenDirectoryNotExists](#when-directory-not-exists) |
| WhenFileExists                      |       |         | [WhenFileExists](#when-file-exists)                  |
| WhenFileNotExists                   |       |         | [WhenFileNotExists](#when-file-not-exists)           |

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

### Format

#### Syntax(Format)

```sh
kcmd format src type [name:value]
```

#### Required Parameters(Format)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |
| type     | [FileFormatType](#file-format-type) |

#### Optional Parameters(Format)

| Name                                | Alias | Default | Definition                                           |
| ----------------------------------- | ----- | ------- | ---------------------------------------------------- |
| AttributesToSkip                    |       | 0       | [AttributesToSkip](#attributes-to-skip)              |
| Encoding                            | E     | utf-8   | [Encoding](#encoding)                                |
| ExcludeExe                          |       | false   | [ExcludeExe](#exclude-exe)                           |
| ExcludeExeFiles                     |       | false   | [ExcludeExeFiles](#exclude-exe-files)                |
| ExcludeExeRelatedFiles              |       | false   | [ExcludeExeRelatedFiles](#exclude-exe-related-files) |
| ExcludeFileNameStartsWith           |       |         |                                                      |
| ExcludeFileNameStartsWithIgnoreCase |       |         |                                                      |
| IgnoreInaccessible                  |       | true    | [IgnoreInaccessible](#ignore-inaccessible)           |
| Include                             | I     |         | [Include](#include)                                  |
| OverrideFile                        | O     | true    |                                                      |
| Recursive                           | R     | false   |                                                      |
| Silent                              | S     | false   |                                                      |
| SrcSearchPattern                    |       | *       |                                                      |
| WhenDirectoryExists                 |       |         | [WhenDirectoryExists](#when-directory-exists)        |
| WhenDirectoryNotExists              |       |         | [WhenDirectoryNotExists](#when-directory-not-exists) |
| WhenFileExists                      |       |         | [WhenFileExists](#when-file-exists)                  |
| WhenFileNotExists                   |       |         | [WhenFileNotExists](#when-file-not-exists)           |

#### Remarks(Format)

##### File Format Type

| Name               | Value | Description |
| ------------------ | ----- | ----------- |
| Xml                | 1     |             |
| Utf8               | 2     |             |
| PreferDoubleQuotes | 10    |             |

#### Examples(Format)

```sh
kcmd format ./KCmd.csproj xml
kcmd format ./ xml SrcSearchPattern:*.csproj -R

kcmd format ./common.h utf8 encoding:gb2312
kcmd format ./common.h utf8 encoding:gb2312 backup:false

kcmd format ./ utf8 SrcSearchPattern:*.cs Backup:false Recursive
kcmd format ./ utf8 SrcSearchPattern:"*.h;*.cpp" Backup:false Recursive

kcmd format ./lib/app.dart 10
kcmd format ./lib PreferDoubleQuotes SrcSearchPattern:*.dart Recursive
kcmd format ./lib PreferDoubleQuotes SrcSearchPattern:*.dart Recursive i:./lib/file-list.txt
```

### Telnet

#### Syntax(Telnet)

```sh
kcmd telnet [name:value]
```

#### Required Parameters(Telnet)

none

#### Optional Parameters(Telnet)

| Name        | Alias | Default   | Definition                  |
| ----------- | ----- | --------- | --------------------------- |
| Host        | h     | localhost |                             |
| Port        | p     | 23        |                             |
| UserName    | u     |           |                             |
| Password    | pwd   |           |                             |
| Type        | t     | 0(None)   | 0\|1, None\|AndroidEmulator |
| CommandFile | cf    |           |                             |

#### Remarks(Telnet)

#### Examples(Telnet)

```sh
kcmd telnet h:localhost p:23 u:root pwd:admin

kcmd telnet Type:AndroidEmulator CommandFile:./cmd-line-by-line.txt Port:5554
kcmd telnet t:1 cf:./cmd-line-by-line.txt h:localhost p:5554
```

cmd-line-by-line.txt:

```txt
redir add tcp:18080:8080
redir add tcp:18081:8081
redir list
```

### List

#### Syntax(List)

```sh
kcmd list dir [name:value]
```

#### Required Parameters(List)

| Position | Value             |
| -------- | ----------------- |
| dir      | directory         |

#### Optional Parameters(List)

| Name            | Alias | Default             | Definition        |
| --------------- | ----- | -------             | ----------------- |
| OnlyDirectories |       | false               |                   |
| OnlyFiles       |       | false               |                   |
| Level           |       | 0                   | for sub-directory |
| Output          | O     |                     | output file       |
| Relative        |       | false               | use relative path |
| SearchPattern   |       | *                   |                   |
| Separator       |       | Environment.NewLine |                   |
| SurroundBy      |       |                     |                   |
| DoubleQuotes    |       | false               |                   |
| SingleQuotes    |       | false               |                   |

#### Remarks(List)

#### Examples(List)

```sh
kcmd list ./
kcmd list ./lib relative o:./lib/file-list.txt

kcmd list ./ SearchPattern:*.txt Separator:"," DoubleQuotes
```

### Upload

#### Syntax(Upload)

```sh
kcmd upload src server [name:value]
```

#### Required Parameters(Upload)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |
| server   | http url          |

#### Optional Parameters(Upload)

| Name                   | Alias   | Default | Definition |
| ---------------------- | ------- | ------- | ---------- |
| Destination            | Dest, D |         |            |
| KeepDirectoryStructure | Keep    | false   |            |
| Recursive              | R       | false   |            |
| AuthenticationType     | Auth    |         |            |
| UserName               | User, U |         |            |
| Password               | Pass, P |         |            |

#### Remarks(Upload)

This command is mainly used for [kaven-file-server](https://github.com/Kaven-Universe/kaven-file-server).

If `Destination` is a directory, make sure it ends with a slash.

#### Examples(Upload)

```sh
kcmd upload ./file.txt http://localhost:3000/file

kcmd upload ./ http://127.0.0.1/file Destination:sub/dir -r -keep

kcmd upload ./build/app-release.apk http://localhost:3000/file dest:"My App {{Version}}.apk"

kcmd upload ./file.txt http://127.0.0.1/file auth:Digest u:username p:password
```

### Generate-Commands/GC

#### Syntax(Generate-Commands)

```sh
kcmd generate-commands src [name:value]
```

#### Required Parameters(Generate-Commands)

| Position | Value             |
| -------- | ----------------- |
| src      | Defined json file |

#### Optional Parameters(Generate-Commands)

| Name                   | Alias   | Default | Definition |
| ---------------------- | ------- | ------- | ---------- |
| Output                 | o       |         |            |

#### Examples(Generate-Commands)

`publish.json`:

```json
[
  {
    "Name": "dotnet publish",
    "Arguments": "./ProtocolBuffersGenerator/ProtocolBuffersGenerator.csproj",
    "Options": {
      "--configuration ": [
        "Release"
      ],
      "--self-contained ": [
        "false"
      ],
      "-p:PublishSingleFile=": [
        "true"
      ],
      "--runtime ": [
        "win-x64",
        "win-x86"
      ],
      "-p:DebugType=": [
        "None"
      ],
      "-p:DebugSymbols=": [
        "false"
      ],
      "--output ": [
        "./publish/{--runtime }"
      ]
    }
  },
  {
    "Name": "dotnet publish",
    "Arguments": "./ProtocolBuffersGeneratorCmd/ProtocolBuffersGeneratorCmd.csproj",
    "Options": {
      "--configuration ": [
        "Release"
      ],
      "--self-contained ": [
        "false"
      ],
      "-p:PublishSingleFile=": [
        "true"
      ],
      "--runtime ": [
        "win-x64",
        "win-x86",
        "linux-x64"
      ],
      "-p:DebugType=": [
        "None"
      ],
      "-p:DebugSymbols=": [
        "false"
      ],
      "--output ": [
        "./publish/{--runtime }"
      ]
    }
  }
]
```

```sh
kcmd generate-commands .\publish.json
kcmd generate-commands .\publish.json -o:.\publish.ps1
```

outputs:

```ps1
dotnet publish ./ProtocolBuffersGenerator/ProtocolBuffersGenerator.csproj --configuration Release --self-contained false -p:PublishSingleFile=true --runtime win-x64 -p:DebugType=None -p:DebugSymbols=false --output ./publish/win-x64
dotnet publish ./ProtocolBuffersGenerator/ProtocolBuffersGenerator.csproj --configuration Release --self-contained false -p:PublishSingleFile=true --runtime win-x86 -p:DebugType=None -p:DebugSymbols=false --output ./publish/win-x86
dotnet publish ./ProtocolBuffersGeneratorCmd/ProtocolBuffersGeneratorCmd.csproj --configuration Release --self-contained false -p:PublishSingleFile=true --runtime win-x64 -p:DebugType=None -p:DebugSymbols=false --output ./publish/win-x64
dotnet publish ./ProtocolBuffersGeneratorCmd/ProtocolBuffersGeneratorCmd.csproj --configuration Release --self-contained false -p:PublishSingleFile=true --runtime win-x86 -p:DebugType=None -p:DebugSymbols=false --output ./publish/win-x86
dotnet publish ./ProtocolBuffersGeneratorCmd/ProtocolBuffersGeneratorCmd.csproj --configuration Release --self-contained false -p:PublishSingleFile=true --runtime linux-x64 -p:DebugType=None -p:DebugSymbols=false --output ./publish/linux-x64
```

### Others

#### Where

```sh
kcmd where [open]
```

#### Help

```sh
kcmd help
```

## Common Parameters

### Attributes To Skip

- [AttributesToSkip](https://docs.microsoft.com/en-us/dotnet/api/system.io.enumerationoptions.attributestoskip?view=net-6.0)

### Compression Level

- [CompressionLevel](https://docs.microsoft.com/en-us/dotnet/api/system.io.compression.compressionlevel?view=net-6.0)

| Name          | Value | Description                                                  |
| ------------- | ----- | ------------------------------------------------------------ |
| Fastest       | 1     | The compression operation should complete as quickly as possible, even if the resulting file is not optimally compressed. |
| NoCompression | 2     | No compression should be performed on the file.              |
| Optimal       | 0     | The compression operation should be optimally compressed, even if the operation takes a longer time to complete. |
| SmallestSize	| 3	    | The compression operation should create output as small as possible, even if the operation takes a longer time to complete. |

### Encoding

- [List of encodings](https://docs.microsoft.com/en-us/dotnet/api/system.text.encoding?view=net-6.0#list-of-encodings)

### Exclude Exe

[ExcludeExeFiles](#exclude-exe-files) and [ExcludeExeRelatedFiles](#exclude-exe-related-files)

### Exclude Exe Files

Exclude all `.exe` files;

```eg
KCmd.exe
```

### Exclude Exe Related Files

Exclude all `.exe` related files.

```eg
KCmd.deps.json
KCmd.dll
KCmd.pdb
KCmd.runtimeconfig.dev.json
KCmd.runtimeconfig.json
```

### File Attributes

- [FileAttributes](https://docs.microsoft.com/en-us/dotnet/api/system.io.fileattributes?view=net-6.0)

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

- [IgnoreInaccessible](https://docs.microsoft.com/en-us/dotnet/api/system.io.enumerationoptions.ignoreinaccessible?view=net-6.0)

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

### When Directory Exists

Specify a directory path, execute the command only if the path exists.

```sh
kcmd cp README.md ../doc/KCmd/README.md WhenDirectoryExists:../doc
```

### When Directory Not Exists

Specify a directory path, execute the command only if the path dose not exists.

### When File Exists

Specify a file path, execute the command only if the path exists.

### When File Not Exists

Specify a file path, execute the command only if the path dose not exists.
