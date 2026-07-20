# linuxgaming-fix-vcrun2022-install

## About
This [repository](https://github.com/rboxeur/linuxgaming-fix-vcrun2022-install) provides to install Visual C++ 2015-2055. Wine release could sometimes break its installation.

## How to proceed

1. Clone this repository

```bash
git clone https://github.com/rboxeur/linuxgaming-fix-vcrun2022-install.git && cd linuxgaming-fix-vcrun2022-install.git
```

2. Load the registry file using Wine

```bash
wine reg import vcrun.reg /reg:64
```

3. Copy respectively 32 bits and 64 bits dlls to their respective subfolder (32bits = syswow64 / 64 bits = system32)

```bash
cp -af x64/dlls/* /path/to/drive_c/windows/system32/
cp -af x86/dlls/* /path/to/drive_c/windows/syswow64/
```

or if your WINEPREFIX environment variable is already set then

```bash
cp -af x64/dlls/* ${WINEPREFIX}/drive_c/windows/system32/
cp -af x86/dlls/* ${WINEPREFIX}/drive_c/windows/syswow64/
```
