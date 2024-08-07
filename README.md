# houdini-shl-doxygen

## Summary
The Standard Houdini Library (SHL).

The documentation was generated from the standard library of header files developed in SideFX. These are mainly VEX, OSL, OCL header files, but this library can be extended with header files for other languages if desired.

![Preview](https://i.imgur.com/yuzQArj.jpeg)

## Motivation

The Houdini documentation contains quite a lot of useful information, but still it lacks descriptions and definitions about header files that are used in snippets hidden in HDA. It is very difficult to use something you don't know enough about.
The purpose of this work was to get documentation about these header files so that it is easy to use them as well as the rest of the documentation in Houdini.

## Requirements
doxygen>=1.9.8

## Installation
For Linux Distribution:
- Pre-built:
    - Extract the archive:
    ```bash
    >>> tar xvf shl-doxygen-*.tar.gz or 7z x shl-doxygen-*.7z
    ```
    - Copy the directory **houdini-shl-doxygen/build/houdiniX.Y**
    ```bash
    cp -R houdini-shl-doxygen/build/houdiniX.Y $HOME/houdiniX.Y
    ```
    to directory for storing user preference files. Or to another directory defined by the user to store the settings defined in the variable **$HOUDINI_USER_PREF_DIR**
    - The documentation will then be locally available from Houdini.
    *Help -> Contents -> APIs -> Standard Houdini Library*<br></br>

- Build from source:
    - Install [doxygen](https://www.doxygen.nl "Generate documentation from source code") from source or use pre-built realeses
        - Check if doxygen is installed correctly from the terminal:
        ```bash
        >>> doxygen --version
        >>> 1.9.8
        ```
    - In the **houdini-shl-doxygen** directory, create a new **include** directory:
    ```bash
    >>> cd houdini-shl-doxygen
    >>> mkdir -p src/include/{ocl,osl,vex}
    ```
    - Copy the contents of the **include** vex, osl, ocl directories from the **$HFS/houdini** directory to **houdini-shl-doxygen/src/include**:
    ```bash
    >>> cp -r $HFS/houdini/ocl/include src/include/ocl && cp -r $HFS/houdini/osl/include src/include/osl && cp -r $HFS/houdini/vex/include src/include/vex
    ```
    - Building new documentation from header files:
    ```bash
    >>> doxygen Doxyfile -l DoxygenLayout.xml
    ```
    - Optional:
        - You can also use an application with the `doxywizard` interface to generate documentation.
        - You can use whatever structure you want within the **include** directory to create your own documentation or extend an existing one.
    - After this, new documentation will be generated.

For a Windows build, many of the steps will be very similar.

## TODO
- [ ] Generating documentation using AI? (AI Doxygen) or fully prepare header files for generation.
- [ ] Refine feature signatures to improve parsing of conspiracy files.
- [ ] Examples of use.

## Known issues and restriction
- The header files were not specifically prepared for generating documentation so the search structure is fuzzy.
- The types, functions, structures defined in the standard Houdini help are not available in this part of the documentation. Therefore it is not possible to make a jump from the documentation to the point function for example.
- As the header files are proprietary to SideFX the documentation cannot be used for commercial purposes.
