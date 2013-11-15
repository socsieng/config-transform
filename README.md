config-transform
================

Configuration transformations are convenient for managing build specific configuration files in .Net. However, the results of these transformations are easily accessible. This repository contains a useful batch file to apply and view these transformations without having to deploy the project.

Usage

```
transform.bat <file.config> <transformation> [output file]
```

Where:

* `<file.config>` is the .Net configuration file that will be applied
* `<transformation> is the name of the transformation to apply (typically `Debug` or `Release`)
  * assumption: corresponding `file.debug.config` or `file.release.config` file exists in the same directory as `file.config`
* `[output file]` is the optional file name to outupt the resultant transformation to
  * if unspecified, the contents will be sent to command window (`stdout`)
