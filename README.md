config-transform
================

Configuration transformations are convenient for managing build specific configuration files in .Net. However, the results of these transformations are easily accessible. This repository contains a batch file used to apply and view these transformations without having to first deploy the project.

## Usage

```
transform.bat <file.config> <transformation> [output file]
```

Where:

* `<file.config>` is the .Net configuration file that will be applied
* `<transformation>` is the name of the transformation to apply (typically `Debug` or `Release`)
  * assumption: corresponding `file.debug.config` or `file.release.config` file exists in the same directory as `file.config`
* `[output file]` is the optional file name to outupt the resultant transformation to
  * if unspecified, the contents will be sent to command window (`stdout`)
  
## Example

Sample file structure

```
C:
|- transform.bat

D:
|- Project Folder
   |- default.aspx
   |- web.config
   |- web.debug.config
   |- web.release.config
```

Output to a file

```
C:\> transform.bat web.config debug output.config
```

Output to the command window

```
C:\> transform.bat web.config debug
```

## Prerequisites

In order to use this batch file, you will need:

* Microsoft .Net (tested with .Net 4)
* `msbuild` accessible from the command prompt
  * I've done this by adding `C:\WINDOWS\Microsoft.NET\Framework\v4.0.30319` to the `PATH` environment variable
