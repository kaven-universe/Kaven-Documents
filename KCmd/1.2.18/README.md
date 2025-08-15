﻿# [KCmd-1.2.18](https://doc.kaven.xyz/KCmd/1.2.18)

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
kcmd copy|cp src dest [name:value] ...
```

#### Required Parameters(Copy)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |
| dest     | file or directory |

#### Optional Parameters(Copy)

| Name                                | Alias     | Default | Definition                                           |
| ----------------------------------- | -----     | ------- | ---------------------------------------------------- |
| AttributesToSkip                    |           | 0       | [AttributesToSkip](#attributes-to-skip)              |
| ExcludeFileNameContains             |           |         |                                                      |
| ExcludeFileNameContainsIgnoreCase   |           |         |                                                      |
| ExcludeFileNameEndsWith             | Exclude   |         |                                                      |
| ExcludeFileNameEndsWithIgnoreCase   |           |         |                                                      |
| ExcludeFileNameStartsWith           |           |         |                                                      |
| ExcludeFileNameStartsWithIgnoreCase |           |         |                                                      |
| IgnoreInaccessible                  |           | true    | [IgnoreInaccessible](#ignore-inaccessible)           |
| Include                             | I         |         | [Include](#include)                                  |
| OverrideFile                        | Override  | true    |                                                      |
| Recursive                           | R         | false   |                                                      |
| Silent                              | S         | false   |                                                      |
| SrcSearchPattern                    |           | *       |                                                      |
| WhenDirectoryExists                 |           |         | [WhenDirectoryExists](#when-directory-exists)        |
| WhenDirectoryNotExists              |           |         | [WhenDirectoryNotExists](#when-directory-not-exists) |
| WhenFileExists                      |           |         | [WhenFileExists](#when-file-exists)                  |
| WhenFileNotExists                   |           |         | [WhenFileNotExists](#when-file-not-exists)           |

#### Remarks(Copy)

#### Examples(Copy)

```sh
kcmd copy xxx/file.src yyy/file.dest

kcmd copy xxx/src yyy/dest recursive
kcmd copy xxx/src yyy/dest -recursive
kcmd cp xxx/src yyy/dest r
kcmd cp xxx/src yyy/dest -r

kcmd cp xxx/src yyy/dest -r -OverrideFile:false
kcmd cp xxx/src yyy/dest -r -override:false

kcmd cp xxx/src yyy/dest Exclude:.exe/.lib/.temp
kcmd cp xxx/src yyy/dest -r SrcSearchPattern:*.txt ExcludeFileNameStartsWith:exclude_
```

```sh
# This command copies the contents of ./src to ./dest at the top level, but only the top-level files (not directories).
kcmd copy ./src ./dest
```

- `src`
  - `file1`
  - `file2`
  - `folder1`
    - `file3`
    - `file4`
    - `subfolder1`
      - `file5`
      - `file6`

- `dest`
  - `file1`
  - `file2`

```sh
# This command copies the contents of ./src to ./dest recursively, including all subdirectories and their contents.
kcmd copy ./src ./dest recursive
kcmd copy ./src ./dest -r
```

- `src`
  - `file1`
  - `file2`
  - `folder1`
    - `file3`
    - `file4`
    - `subfolder1`
      - `file5`
      - `file6`

- `dest`
  - `file1`
  - `file2`
  - `folder1`
    - `file3`
    - `file4`
    - `subfolder1`
      - `file5`
      - `file6`

```sh
# Keep src folder in dest
kcmd copy ./src ./dest/src
```

- `src`
  - `file1`
  - `file2`
  - `folder1`
    - `file3`
    - `file4`
    - `subfolder1`
      - `file5`
      - `file6`

- `dest`
  - `src`
    - `file1`
    - `file2`

```sh
# Keep src folder in dest
kcmd copy ./src ./dest/src recursive
```

- `src`
  - `file1`
  - `file2`
  - `folder1`
    - `file3`
    - `file4`
    - `subfolder1`
      - `file5`
      - `file6`

- `dest`
  - `src`
    - `file1`
    - `file2`
    - `folder1`
      - `file3`
      - `file4`
      - `subfolder1`
        - `file5`
        - `file6`

### Move/mv

#### Syntax(Move)

```sh
kcmd move/mv src dest [name:value] ...
```

#### Required Parameters(Move)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |
| dest     | file or directory |

#### Optional Parameters(Move)

| Name                                | Alias     | Default | Definition                                           |
| ----------------------------------- | -----     | ------- | ---------------------------------------------------- |
| AttributesToSkip                    |           | 0       | [AttributesToSkip](#attributes-to-skip)              |
| ExcludeFileNameContains             |           |         |                                                      |
| ExcludeFileNameContainsIgnoreCase   |           |         |                                                      |
| ExcludeFileNameEndsWith             | Exclude   |         |                                                      |
| ExcludeFileNameEndsWithIgnoreCase   |           |         |                                                      |
| ExcludeFileNameStartsWith           |           |         |                                                      |
| ExcludeFileNameStartsWithIgnoreCase |           |         |                                                      |
| IgnoreInaccessible                  |           | true    | [IgnoreInaccessible](#ignore-inaccessible)           |
| Include                             | I         |         | [Include](#include)                                  |
| OverrideFile                        | Override  | true    |                                                      |
| Recursive                           | R         | false   |                                                      |
| Silent                              | S         | false   |                                                      |
| SrcSearchPattern                    |           | *       |                                                      |
| WhenDirectoryExists                 |           |         | [WhenDirectoryExists](#when-directory-exists)        |
| WhenDirectoryNotExists              |           |         | [WhenDirectoryNotExists](#when-directory-not-exists) |
| WhenFileExists                      |           |         | [WhenFileExists](#when-file-exists)                  |
| WhenFileNotExists                   |           |         | [WhenFileNotExists](#when-file-not-exists)           |

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
kcmd delete/rm src [name:value] ...
```

#### Required Parameters(Delete)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |

#### Optional Parameters(Delete)

| Name                                | Alias     | Default | Definition                                           |
| ----------------------------------- | -----     | ------- | ---------------------------------------------------- |
| AttributesToSkip                    |           | 0       | [AttributesToSkip](#attributes-to-skip)              |
| ExcludeFileNameContains             |           |         |                                                      |
| ExcludeFileNameContainsIgnoreCase   |           |         |                                                      |
| ExcludeFileNameEndsWith             | Exclude   |         |                                                      |
| ExcludeFileNameEndsWithIgnoreCase   |           |         |                                                      |
| ExcludeFileNameStartsWith           |           |         |                                                      |
| ExcludeFileNameStartsWithIgnoreCase |           |         |                                                      |
| IgnoreInaccessible                  |           | true    | [IgnoreInaccessible](#ignore-inaccessible)           |
| Include                             | I         |         | [Include](#include)                                  |
| OverrideFile                        | Override  | true    |                                                      |
| Recursive                           | R         | false   |                                                      |
| Silent                              | S         | false   |                                                      |
| SrcSearchPattern                    |           | *       |                                                      |
| WhenDirectoryExists                 |           |         | [WhenDirectoryExists](#when-directory-exists)        |
| WhenDirectoryNotExists              |           |         | [WhenDirectoryNotExists](#when-directory-not-exists) |
| WhenFileExists                      |           |         | [WhenFileExists](#when-file-exists)                  |
| WhenFileNotExists                   |           |         | [WhenFileNotExists](#when-file-not-exists)           |

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
kcmd archive src [name:value] ...
```

#### Required Parameters(Archive)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |

#### Optional Parameters(Archive)

| Name                                | Alias     | Default  | **Definition**                                       |
| ----------------------------------- | -----     | -------- | ---------------------------------------------------- |
| AttributesToSkip                    |           | 0        | [AttributesToSkip](#attributes-to-skip)              |
| CompressionLevel                    |           | Optimal  | [CompressionLevel](#compression-level)               |
| Dest                                | D         |          |                                                      |
| Encoding                            | E         | utf-8    | [Encoding](#encoding)                                |
| ExcludeBaseDirectory                |           | true     |                                                      |
| ExcludeFileNameContains             |           |          |                                                      |
| ExcludeFileNameContainsIgnoreCase   |           |          |                                                      |
| ExcludeFileNameEndsWith             | Exclude   |          |                                                      |
| ExcludeFileNameEndsWithIgnoreCase   |           |          |                                                      |
| ExcludeFileNameStartsWith           |           |          |                                                      |
| ExcludeFileNameStartsWithIgnoreCase |           |          |                                                      |
| IgnoreInaccessible                  |           | true     | [IgnoreInaccessible](#ignore-inaccessible)           |
| Include                             | I         |          | [Include](#include)                                  |
| IncludeBaseDirectory                |           | false    |                                                      |
| OverrideFile                        | Override  | true     |                                                      |
| Recursive                           | R         | **true** |                                                      |
| Silent                              | S         | false    |                                                      |
| SrcSearchPattern                    |           | *        |                                                      |
| WhenDirectoryExists                 |           |          | [WhenDirectoryExists](#when-directory-exists)        |
| WhenDirectoryNotExists              |           |          | [WhenDirectoryNotExists](#when-directory-not-exists) |
| WhenFileExists                      |           |          | [WhenFileExists](#when-file-exists)                  |
| WhenFileNotExists                   |           |          | [WhenFileNotExists](#when-file-not-exists)           |

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
kcmd archive-subdirectories src [name:value] ...
```

#### Required Parameters(Archive-Subdirectories)

| Position | Value             |
| -------- | ----------------- |
| src      | directory |

#### Optional Parameters(Archive-Subdirectories)

| Name                                | Alias     | Default  | **Definition**                                       |
| ----------------------------------- | -----     | -------- | ---------------------------------------------------- |
| CompressionLevel                    |           | Optimal  | [CompressionLevel](#compression-level)               |
| Dest                                | D         |          |                                                      |
| Encoding                            | E         | utf-8    | [Encoding](#encoding)                                |
| IncludeBaseDirectory                |           | false    |                                                      |
| OverrideFile                        | Override  | true     |                                                      |
| Silent                              | S         | false    |                                                      |
| DeleteSubdirectories                | Delete    | false    |                                                      |

#### Examples(Archive-Subdirectories)

```sh
kcmd archive-subdirectories ./publish
kcmd archive-subdirectories ./publish -d:./publish/zip/
kcmd archive-subdirectories ./publish IncludeBaseDirectory OverrideFile
```

### Archive-Extract/Extract

#### Syntax(Archive-Extract)

```sh
kcmd archive-extract/extract src [name:value] ...
```

#### Required Parameters(Archive-Extract)

| Position | Value             |
| -------- | ----------------- |
| src      | zip file          |

#### Optional Parameters(Archive-Extract)

| Name                                | Alias     | Default | **Definition**                                       |
| ----------------------------------- | -----     | ------- | ---------------------------------------------------- |
| Dest                                | D         |         |                                                      |
| Encoding                            | E         | utf-8   | [Encoding](#encoding)                                |
| ExcludeFileNameContains             |           |         |                                                      |
| ExcludeFileNameContainsIgnoreCase   |           |         |                                                      |
| ExcludeFileNameEndsWith             | Exclude   |         |                                                      |
| ExcludeFileNameEndsWithIgnoreCase   |           |         |                                                      |
| ExcludeFileNameStartsWith           |           |         |                                                      |
| ExcludeFileNameStartsWithIgnoreCase |           |         |                                                      |
| OverrideFile                        | Override  | true    |                                                      |
| Silent                              | S         | false   |                                                      |
| WhenDirectoryExists                 |           |         | [WhenDirectoryExists](#when-directory-exists)        |
| WhenDirectoryNotExists              |           |         | [WhenDirectoryNotExists](#when-directory-not-exists) |
| WhenFileExists                      |           |         | [WhenFileExists](#when-file-exists)                  |
| WhenFileNotExists                   |           |         | [WhenFileNotExists](#when-file-not-exists)           |

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
kcmd format src type [name:value] ...
```

#### Required Parameters(Format)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |
| type     | [FileFormatType](#file-format-type) |

#### Optional Parameters(Format)

| Name                                | Alias     | Default | Definition                                           |
| ----------------------------------- | -----     | ------- | ---------------------------------------------------- |
| AttributesToSkip                    |           | 0       | [AttributesToSkip](#attributes-to-skip)              |
| Encoding                            | E         | utf-8   | [Encoding](#encoding)                                |
| ExcludeFileNameContains             |           |         |                                                      |
| ExcludeFileNameContainsIgnoreCase   |           |         |                                                      |
| ExcludeFileNameEndsWith             | Exclude   |         |                                                      |
| ExcludeFileNameEndsWithIgnoreCase   |           |         |                                                      |
| ExcludeFileNameStartsWith           |           |         |                                                      |
| ExcludeFileNameStartsWithIgnoreCase |           |         |                                                      |
| IgnoreInaccessible                  |           | true    | [IgnoreInaccessible](#ignore-inaccessible)           |
| Include                             | I         |         | [Include](#include)                                  |
| OverrideFile                        | Override  | true    |                                                      |
| Recursive                           | R         | false   |                                                      |
| Silent                              | S         | false   |                                                      |
| SrcSearchPattern                    |           | *       |                                                      |
| WhenDirectoryExists                 |           |         | [WhenDirectoryExists](#when-directory-exists)        |
| WhenDirectoryNotExists              |           |         | [WhenDirectoryNotExists](#when-directory-not-exists) |
| WhenFileExists                      |           |         | [WhenFileExists](#when-file-exists)                  |
| WhenFileNotExists                   |           |         | [WhenFileNotExists](#when-file-not-exists)           |

#### Remarks(Format)

##### File Format Type

| Name                      | Value | Description |
| ------------------        | ----- | ----------- |
| Xml                       | 1     |             |
| Utf8                      | 2     |             |
| PreferDoubleQuotes        | 10    |             |
| CSharpDataMemberOrder     | 101   |             |

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

kcmd format ./Config.cs CSharpDataMemberOrder
```

### Telnet

#### Syntax(Telnet)

```sh
kcmd telnet [name:value] ...
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
kcmd list dir [name:value] ...
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
kcmd upload src server [name:value] ...
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
kcmd generate-commands src [name:value] ...
kcmd gc src [name:value] ...
```

#### Required Parameters(Generate-Commands)

| Position | Value             |
| -------- | ----------------- |
| src      | Defined json file |

#### Optional Parameters(Generate-Commands)

| Name                   | Alias   | Default | Definition |
| ---------------------- | ------- | ------- | ---------- |
| Output                 | O       |         |            |

#### Remarks(Generate-Commands)

- Define commands in `Variables` and access the output of execution by `{xxx}`, like `Version` below.

#### Examples(Generate-Commands)

`publish.json`:

```json
[
  {
    "Name": "dotnet publish",
    "Arguments": "./Kaven.Network.Statistics/Kaven.Network.Statistics.csproj",
    "Variables": {
      "Version": "kcmd parse-version ./Kaven.Network.Statistics/"
    },
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
        "win-arm64"
      ],
      "-p:DebugType=": [
        "None"
      ],
      "-p:DebugSymbols=": [
        "false"
      ],
      "-p:EnableWindowsTargeting=": [
        "true"
      ],
      "--output ": [
        "./publish/Kaven.Network.Statistics-{Version}-{--runtime }"
      ]
    },
    "PreCommands":[
      "kcmd delete ./publish -R"
    ],
    "PostCommands":[
      "kcmd copy '../../Kaven.Wrapper.WinDivert/WinDivert-2.2.2-A/x64' './publish/Kaven.Network.Statistics-{Version}-win-x64/x64' -Exclude:.exe/.lib",
      "kcmd copy '../../Kaven.Wrapper.WinDivert/WinDivert-2.2.2-A/x86' './publish/Kaven.Network.Statistics-{Version}-win-x86/x86' -Exclude:.exe/.lib"
    ]
  }
]
```

```sh
kcmd generate-commands .\publish.json
kcmd generate-commands .\publish.json -o:.\publish.ps1
```

outputs:

```ps1
kcmd delete ./publish -R
dotnet publish ./Kaven.Network.Statistics/Kaven.Network.Statistics.csproj --configuration Release --self-contained false -p:PublishSingleFile=true --runtime win-x64 -p:DebugType=None -p:DebugSymbols=false -p:EnableWindowsTargeting=true --output ./publish/Kaven.Network.Statistics-1.2.0-win-x64
dotnet publish ./Kaven.Network.Statistics/Kaven.Network.Statistics.csproj --configuration Release --self-contained false -p:PublishSingleFile=true --runtime win-x86 -p:DebugType=None -p:DebugSymbols=false -p:EnableWindowsTargeting=true --output ./publish/Kaven.Network.Statistics-1.2.0-win-x86
dotnet publish ./Kaven.Network.Statistics/Kaven.Network.Statistics.csproj --configuration Release --self-contained false -p:PublishSingleFile=true --runtime win-arm64 -p:DebugType=None -p:DebugSymbols=false -p:EnableWindowsTargeting=true --output ./publish/Kaven.Network.Statistics-1.2.0-win-arm64
kcmd copy '../../Kaven.Wrapper.WinDivert/WinDivert-2.2.2-A/x64' './publish/Kaven.Network.Statistics-1.2.0-win-x64/x64' -Exclude:.exe/.lib
kcmd copy '../../Kaven.Wrapper.WinDivert/WinDivert-2.2.2-A/x86' './publish/Kaven.Network.Statistics-1.2.0-win-x86/x86' -Exclude:.exe/.lib
```

### Pack

#### Syntax(Pack)

```sh
kcmd pack src [name:value] ...
```

#### Required Parameters(Pack)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |

#### Optional Parameters(Pack)

none

#### Remarks(Pack)

Based on the [Archive](#archive) command, the files in the corresponding directory are automatically packaged into a zip file.

#### Examples(Pack)

```sh
kcmd pack ./
kcmd pack ./bin/Release/AnyCPU/publish/win-x64
kcmd pack ./bin/Release/AnyCPU/publish/win-x64/myApp.exe

->

Generate a file named `myApp-1.0.0.zip`
```

### Guid

Generate a new Guid.

#### Syntax(Guid)

```sh
kcmd guid [name:value] ...
```

#### Required Parameters(Guid)

none

#### Optional Parameters(Guid)

none

#### Remarks(Guid)

#### Examples(Guid)

```sh
kcmd guid
```

### HTTP-Server

#### Syntax(HTTP-Server)

```sh
kcmd http-server [name:value] ...
```

#### Required Parameters(HTTP-Server)

none

#### Optional Parameters(HTTP-Server)

| Name                   | Alias      | Default | Definition                                                                   |
| ---------------------- | -------    | ------- | ----------                                                                   |
| Directory              | Dir, D     | CWD     |                                                                              |
| Host                   | H          |         |                                                                              |
| Port                   | P          | 3991    |                                                                              |
| UserName               | User, U    |         |                                                                              |
| Password               | Pass, pwd  |         |                                                                              |
| Upload                 |            |         | Set to `false` to disable uploading, or set the directory path to upload to  |

#### Remarks(HTTP-Server)

- Automatically enable Basic Authentication when neither `username` nor `password` is empty.
- Uploaded to `Directory` by default.

#### Examples(HTTP-Server)

```sh
kcmd http-server
kcmd http-server Dir:./root/ Host:192.168.1.100 Port:80
kcmd http-server UserName:test Password:123456
kcmd http-server Upload:false
kcmd http-server Upload:./root/upload/
```

### FTP-Server

#### Syntax(FTP-Server)

```sh
kcmd ftp-server [name:value] ...
```

#### Required Parameters(FTP-Server)

none

#### Optional Parameters(FTP-Server)

| Name                   | Alias      | Default | Definition                                                                   |
| ---------------------- | -------    | ------- | ----------                                                                   |
| ConfigFile             | Config, C  | CWD     |                                                                              |

#### Remarks(FTP-Server)

- Supports basic FTP commands (not fully supported)
- Partial support for explicit/implicit encryption
- Control connections support TLS encryption
- Data connections support TLS encryption only in passive mode

demo configuration file:

```json
{
  "Port": 21,
  "PasvServerAddress": "",
  "PasvPorts": "5555,5600-5655",
  "Users": [
    {
      "UserName": "admin",
      "Password": "******",
      "Paths": [
        {
          "VirtualPath": "/",
          "RealPath": "E:/Temp"
        }
      ],
      "Permissions": "List, Download, Upload, Delete, Rename, CreateDirectory, DeleteDirectory",
      "Disabled": false,
      "MergePermissions": false,
      "AllowClearProtectionLevelOnDataConnection": false
    },
    {
      "UserName": "anonymous",
      "Paths": [
        {
          "VirtualPath": "/",
          "RealPath": "E:/Temp"
        },
        {
          "VirtualPath": "/virtual",
          "RealPath": "D:/Documents",
          "Permissions": "Delete"
        },
        {
          "VirtualPath": "/virtual/data/123",
          "RealPath": "D:/Pictures"
        }
      ],
      "Permissions": "List, Download",
      "Disabled": false,
      "MergePermissions": true,
      "AllowClearProtectionLevelOnDataConnection": true
    }
  ],
  "ImplicitTls": false,
  "EnableActiveMode": false,
  "EnableTls": true,
  "CertificateFile": "certificate.crt",
  "PrivateKeyFile": "privateKey.key",
}
```

#### Examples(FTP-Server)

```sh
kcmd ftp-server
kcmd ftp-server ConfigFile
kcmd ftp-server -c
kcmd ftp-server -c:./ftp.json
```

### Parse-Version

#### Syntax(Parse-Version)

```sh
kcmd parse-version src [name:value] ...
```

#### Required Parameters(Parse-Version)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |

#### Optional Parameters(Parse-Version)

| Name                   | Alias   | Default | Definition |
| ---------------------- | ------- | ------- | ---------- |
| Output                 | O       |         |            |

#### Remarks(Parse-Version)

none

#### Examples(Parse-Version)

```sh
kcmd parse-version ./
kcmd parse-version ./ output:./version.txt

kcmd parse-version ./package.json
kcmd parse-version ./pubspec.yaml

kcmd parse-version ./KCmd.csproj
kcmd parse-version ./xxx/Properties/AssemblyInfo.cs
```

### Generate-Protobuf/Gen-PB

#### Syntax(Generate-Protobuf)

```sh
kcmd generate-protobuf file [name:value] ...
kcmd gen-pb file [name:value] ...
```

#### Required Parameters(Generate-Protobuf)

| Position | Value             |
| -------- | ----------------- |
| file     | Config file       |

#### Optional Parameters(Generate-Protobuf)

none

#### Remarks(Generate-Protobuf)

none

#### Examples(Generate-Protobuf)

```sh
kcmd generate-protobuf ./pb.kcf
kcmd gen-pb ./pb.kcf
```

### Speed-Test-Server

#### Syntax(Speed-Test-Server)

```sh
kcmd speed-test-server [name:value] ...
```

#### Required Parameters(Speed-Test-Server)

none

#### Optional Parameters(Speed-Test-Server)

| Name                   | Alias   | Default | Definition                                             |
| ---------------------- | ------- | ------- | ----------                                             |
| Port                   |         | 4520    |                                                        |
| Interval               |         | 1000    | Calculate every second                                 |
| BufferSize             |         | 1048576 |                                                        |
| OneTime                |         | false   | Automatically close after the first client disconnects |

#### Remarks(Speed-Test-Server)

none

#### Examples(Speed-Test-Server)

```sh
kcmd speed-test-server
kcmd speed-test-server port:3721 interval:5000 bufferSize:1024
kcmd speed-test-server -oneTime
```

### Speed-Test-Client

#### Syntax(Speed-Test-Client)

```sh
kcmd speed-test-client [name:value] ...
```

#### Required Parameters(Speed-Test-Client)

none

#### Optional Parameters(Speed-Test-Client)

| Name                   | Alias   | Default    | Definition                |
| ---------------------- | ------- | -------    | ----------                |
| Server                 |         | 127.0.0.1  |                           |
| Port                   |         | 4520       |                           |
| Interval               |         | 1000       | Calculate every second    |
| BufferSize             |         | 1048576    |                           |

#### Remarks(Speed-Test-Client)

none

#### Examples(Speed-Test-Client)

```sh
kcmd speed-test-client
kcmd speed-test-client server:192.168.1.1 port:3721 interval:5000 bufferSize:1024
```

### Watermark

#### Syntax(Watermark)

```sh
kcmd watermark src [name:value] ...
```

#### Required Parameters(Watermark)

| Position | Value             |
| -------- | ----------------- |
| src      | file or directory |

#### Optional Parameters(Watermark)

| Name                   | Alias     | Default                | Definition                 |
| ---------------------- | -------   | -------                | ----------                 |
| Output                 | O         | `src`                  | file or directory          |
| OverrideFile           | Override  | false                  |                            |
| Text                   |           | DateTime.Now           | watermark text             |
| FontName               |           | CygnetRound            |                            |
| FontSize               | Size      | 16                     |                            |
| FontColor              | Color     | rgba(36, 33, 30, 0.16) |                            |
| Angle                  |           | -45                    |                            |
| HorizontalSpace        | H         | 60                     |                            |
| VerticalSpace          | V         | 30                     |                            |
| Utc                    |           | false                  |                            |

#### Remarks(Watermark)

- `Text` formatted with [System.DateTime.ToString()](https://learn.microsoft.com/en-us/dotnet/api/system.datetime.tostring?view=net-8.0#system-datetime-tostring(system-string))

#### Examples(Watermark)

```sh
kcmd watermark ./image.png -override
kcmd watermark ./ -output:./output

# you can escape the literal part of the format string using single quotes
kcmd watermark ./image.png -output:./watermarked.png -text:"'Kaven: 'yyyy-MM-dd HH:mm:ss"

kcmd watermark ./image.png -output:./watermarked.png -size:32

kcmd watermark ./image.png -output:./watermarked.png -color:red
kcmd watermark ./image.png -output:./watermarked.png -color:"rgba(36, 33, 30, 0.16)"
kcmd watermark ./image.png -output:./watermarked.png -color:"#f00"
```

### Compare

#### Syntax(Compare)

```sh
kcmd compare file1 file2
```

#### Required Parameters(Compare)

| Position | Value             |
| -------- | ----------------- |
| file1    | file1 path        |
| file2    | file2 path        |

#### Optional Parameters(Compare)

none

#### Remarks(Compare)

- If the files are not identical, it will try to open them in VSCode or Visual Studio for comparison.

#### Examples(Compare)

```sh
kcmd compare ./file1 ./file2
```

### Generate-Dummy-File/Gen-Dummy

#### Syntax(Generate-Dummy-File/Gen-Dummy)

```sh
kcmd generate-dummy-file output size [name:value] ...
kcmd gen-dummy output size [name:value] ...
```

#### Required Parameters(Generate-Dummy-File/Gen-Dummy)

| Position | Value             |
| -------- | ----------------- |
| output   | save path         |
| size     | file size         |

#### Optional Parameters(Generate-Dummy-File/Gen-Dummy)

| Name                   | Alias     | Default                | Definition                 |
| ---------------------- | -------   | -------                | ----------                 |
| FillRandomData         | Fill      | false                  |                            |

#### Remarks(Generate-Dummy-File/Gen-Dummy)

none

#### Examples(Generate-Dummy-File/Gen-Dummy)

```sh
kcmd gen-dummy ./file 10485760
kcmd gen-dummy ./file 10485760 -fill
kcmd gen-dummy ./file 100MiB -fill
kcmd gen-dummy ./file "10.5 GB" -fill
```

### Calculate-Hash/Hash

#### Syntax(Calculate-Hash/Hash)

```sh
kcmd calculate-hash file [name:value] ...
kcmd hash file [name:value] ...
```

#### Required Parameters(Calculate-Hash/Hash)

| Position | Value             |
| -------- | ----------------- |
| file     | The file path for which the hash value needs to be calculated |

#### Optional Parameters(Calculate-Hash/Hash)

| Name                   | Alias     | Default                                  | Definition                 |
| ---------------------- | -------   | -------                                  | ----------                 |
| Output                 | O         | `file` + '.yyyyMMddHHmmssfff.kaven.hash' |                            |

#### Remarks(Calculate-Hash/Hash)

none

#### Examples(Calculate-Hash/Hash)

```sh
# Calculate file hash and save to default file
kcmd calculate-hash ./file
kcmd hash ./file

# Save to a custom file
kcmd hash ./file output:./hash.txt

# No need to save to file
kcmd hash ./file output:false
```

### Verify-Hash

#### Syntax(Verify-Hash)

```sh
kcmd verify-hash file [name:value] ...
```

#### Required Parameters(Verify-Hash)

| Position | Value             |
| -------- | ----------------- |
| file     | The file path for which the hash value needs to be verified |

#### Optional Parameters(Verify-Hash)

| Name                   | Alias     | Default                                          | Definition                                                                                |
| ---------------------- | -------   | -------                                          | ----------                                                                                |
| HashFile               |           |                                                  | Specify a hash file generated by the [Calculate-Hash/Hash](#calculate-hashhash) command  |
| Output                 | O         | `file` + '.yyyyMMddHHmmssfff.kaven.hash.fails'  | Only if the verification fails will it be saved automatically                             |

#### Remarks(Verify-Hash)

none

#### Examples(Verify-Hash)

```sh
# Automatically find hash files with the same name
kcmd verify-hash ./file

# Specify a hash file
kcmd verify-hash ./file hashFile:./hash.txt

# Specify the file to save the verification results
kcmd verify-hash ./file output:./result.txt

# No need to save even if validation fails
kcmd verify-hash ./file output:false
```

### Run

Searches for `*.kcmd` files and runs the commands in the files line by line.

#### Syntax(Run)

```sh
kcmd run [name:value] ...
```

#### Required Parameters(Run)

none

#### Optional Parameters(Run)

| Name        | Alias     | Default                   | Definition                                  |
| ----------- | -------   | -------                   | ----------                                  |
| Root        |           | `CWD`                     | Current working directory                   |
| SearchLevel |           | -1                        | `<0`: AllDirectories, `0`: TopDirectoryOnly |

#### Remarks(Run)

none

#### Examples(Run)

```sh
kcmd run
kcmd run root:./src
kcmd run root:./src searchLevel:10
```

### Find-Open-Handles

Display the processes that occupy the file.

#### Syntax(Find-Open-Handles)

```sh
kcmd find-open-handles file [name:value] ...
```

#### Required Parameters(Find-Open-Handles)

| Position | Value             |
| -------- | ----------------- |
| file     | file path         |

#### Optional Parameters(Find-Open-Handles)

none

#### Remarks(Find-Open-Handles)

none

#### Examples(Find-Open-Handles)

```sh
kcmd find-open-handles C:\Windows\explorer.exe
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
| SmallestSize  | 3     | The compression operation should create output as small as possible, even if the operation takes a longer time to complete. |

### Encoding

- [List of encodings](https://docs.microsoft.com/en-us/dotnet/api/system.text.encoding?view=net-6.0#list-of-encodings)

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

### Exit Code

A 32-bit signed integer containing the exit code. The default value is 0 (zero), which indicates that the process completed successfully.

## Disclaimer

The creators of this command-line tool hereby declare that they bear no responsibility for any direct or indirect damages arising from the use of the code or information contained herein. All code within this tool is provided "as is," with no expressed or implied warranties. Users assume full responsibility for any risks associated with utilizing this tool.

The code in this tool may contain errors or defects, and the creators do not ensure its accuracy, completeness, or suitability. Users are urged to validate the code and make necessary modifications to suit their specific requirements.

The creators shall not be held liable for any direct or indirect damages resulting from the use of this tool, including but not limited to loss of profits, data, or business interruption.

By utilizing this tool, you acknowledge and accept all terms and conditions stated in this disclaimer.
