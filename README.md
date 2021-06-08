# AtomicParsley

This is a copy of the [BitBucket repo](https://bitbucket.org/wez/atomicparsley) of this project, because it's more up to date than the [Github repo](https://github.com/wez/atomicparsley) by the same author.

Changes in this version:

* A `.gitignore` file to hide the bits created by autoconf/automake. 
* `MAX_ATOMS` has been [bumped from 1024 to 2048](https://github.com/benfry/atomicparsley/commit/a66918b5c76d21f94cdd0f87a9793f729cb4a7e5) to handle some newer files from the iTunes Store.
* Changed `char` to `const char` in a couple places in the macOS-facing code.
* Attempted to use `\uNNNN` escapes because of compiler warnings about `<A9>` and others being illegal characters, but was unsuccessful (came out as ?© in `--longhelp`). Parts of `main.cpp` use octal numbers for © and others, but not gonna fiddle with it further because it appears to be working in spite of the warnings.


## Basic Instructions

If you are building from source you will need autoconf & automake (you will
definitely need make):

      % ./autogen.sh
      % ./configure
      % make

Use the program in situ or place it somewhere in your $PATH by using:

      % sudo make install


### Dependencies:

zlib  - used to compress ID3 frames & expand already compressed frames
        available from http://www.zlib.net

## For Mac OS X users:

To build on Mac OS X / macOS just do a straight forward as shown above.


## For Windows users:
AtomicParsley builds under cygwin and/or mingw using the same procedure as above.

Foosatraz built in Windows 8 using MinGW.

MinGW-get version 0.6.2-beta-20131004-1

mingw-libz version 1.2.8-1 from MinGW Installation Manager

      % ./autogen.sh
      % ./configure --prefix=/mingw
      % make LDFLAGS=-static
      % strip AtomicParsley.exe

Full details [pdf](https://bitbucket.org/Foosatraz/wez-atomicparsley-foosatraz-fork/downloads/AtomicParsleyMinGWBuildNotebook.pdf)

To build with MSVC, you will need to create your own project file; look
at the list of source files in Makefile.am; you need to add all of the
source files *except* the .mm files.  You will also need to provide your
own zlib.

If you don't want to build it yourself, [Jon Hedgrows' fork ](https://bitbucket.org/jonhedgerows/atomicparsley/wiki/Home) maintains pre-built Windows binaries of the Wez fork:
[Windows Downloads](https://bitbucket.org/jonhedgerows/atomicparsley/downloads)

