# houdini-shl-doxygen

## Summary
The Standard Houdini Library (SHL).  

The documentation was generated from the standard library of header files developed in SideFX. These are mainly VEX, OSL, OCL header files, but this library can be extended with header files for other languages if desired.

![Preview](https://i.imgur.com/yuzQArj.jpeg)

## Motivation

The Houdini documentation contains quite a lot of useful information, but still it lacks descriptions and definitions about header files that are used in snippets hidden in HDA. It is very difficult to use something you don't know enough about. 
The purpose of this work was to get documentation about these header files so that it is easy to use them as well as the rest of the documentation in Houdini. 

## Requirements
doxygen

## Installation
- Pre-built:
    - Extract the archive `shl-doxygen-*.tar.gz` or `shl-doxygen-*.7z`
    - Copy the directory `houdini-shl-doxygen/build/houdiniX.Y` to the `$HOUDIINI_USER_PREF_DIR` directory for storing user preference files.
    - The documentation will then be locally available from Houdini.  
    To go to the new documentation page:  
    `Help -> Contents -> APIs -> Standard Houdini Library`<br></br>

- Build from source:
    - Install [doxygen](https://www.doxygen.nl "Generate documentation from source code") from source or use pre-built realeses
    - In the `houdini-shl-doxygen/src` directory, create a new `include` directory.
    - Copy the contents of the `include` vex, osl, ocl directories from the `$HFS/houdini` directory to `houdini-shl-doxygen/src/include`.
    - Go to the `houdini-shl-doxygen/src` directory and run the command:  
    `doxygen Doxyfile -l DoxygenLayout.xml`
        - You can also use an application with the `doxywizard` interface to generate documentation.
    - After this, new documentation will be generated.

## TODO
- [ ] Generating documentation using AI? (AI Doxygen) or fully prepare header files for generation.
- [ ] Refine feature signatures to improve parsing of conspiracy files.
- [ ] Examples of use.

## Known issues and restriction
- The header files were not specifically prepared for generating documentation so the search structure is fuzzy.
- As the header files are proprietary to SideFX the documentation cannot be used for commercial purposes.
