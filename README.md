# Dxm - DxToolkit for Masking

> [!CAUTION]
>
> ## Deprecated
>
> This project is now in long-term stasis. If you are using the dxm-toolkit today, we recommend that you adopt Data Control Tower (DCT) and migrate your automation to the [DCT Toolkit](https://help.delphix.com/dct/current/content/dct_toolkit.htm). The dxm-toolkit was a key input into the introduction of the fully Delphix supported DCT Toolkit.


## What is it

Dxtoolkit for masking is a command line script to manipulate Delphix Masking Engine and it is delivered by Delphix professional services team.
Dxmc script is a single command with parameters and arguments delivered as executable file with libraries. Dxm is written in Python, but no knowledge of Python is equired unless you want to extend it.  In fact, no programming experience whatsoever is required to use the Dxtoolkit for masking.

Supperted Delphix Engine version: >= 5.3.X and 6.0.X

## What's new

Please check a [change log](https://github.com/delphix/dxm-toolkit/blob/master/CHANGELOG.md) for list of changes.

## How to get started
### Compiled version

Download a compiled version of Dxm for required platform from a [releases  page](https://github.com/delphix/dxm-toolkit/releases).
Dxm keep a configuration using SQLLite database and it's creating a configuration file when a first engine is added.
When Dxm is started it will execute an action against Masking engine specified in option or against engine configured as default one.

Compiled version is distributed as single command on Linux and OSX and a zipped folder on Windows platform.
Single command distribution on Windows is limited by PyInstaller issue which require to disable some security features on Windows 10.
To start a DXM on the Linux or OSX, please run dxmc command from place where it was downloaded. On Windows please run dxmc.exe from unzipped folder.

Configure a masking engine using the following steps:

* add engine
```
dxmc engine add --engine testeng --ip testeng.foo.com --username delphix_admin --default Y
Password:
Repeat for confirmation:
Engine added to configuration
```

* list all engines from configuration
```
dxmc engine list

Engine name                     IP                              username                        protocol  port   default
==============================  ==============================  ==============================  ========  =====  =======
testeng                         testeng.foo.com                 delphix_admin                   http      8282   Y

```

* check if configuration is OK and list all applications from Masking Engine
```
dxmc application list

Engine name                     Application name
==============================  ==============================
testeng                         test app 2
```

Check a [documentation](https://github.com/delphix/dxm-toolkit/wiki) for more details

### Known issues

N/A

### Source version

Python 3.7.X or higher

**Required packages**
- Check setup.py for list standard Python packages

```
python setup.py install
```


## Contributing

All contributors are required to sign the Delphix Contributor Agreement prior to contributing code to an open source
repository. This process is handled automatically by [cla-assistant](https://cla-assistant.io/). Simply open a pull
request and a bot will automatically check to see if you have signed the latest agreement. If not, you will be prompted
to do so as part of the pull request process.

This project operates under the [Delphix Code of Conduct](https://delphix.github.io/code-of-conduct.html). By
participating in this project you agree to abide by its terms.

## Statement of Support

This software is provided as-is, without warranty of any kind or commercial support through Delphix. See the associated
license for additional details. Questions, issues, feature requests, and contributions should be directed to the
community as outlined in the [Delphix Community Guidelines](https://delphix.github.io/community-guidelines.html).

## License

This is code is licensed under the Apache License 2.0. Full license is available [here](./LICENSE).