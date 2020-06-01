# AtomicParsley (get_iplayer version)

## Linux

* Tools: gcc/g++, make, autoconf, automake, git

* Dependencies: requires **zlib** development headers and libraries, which may be installed separately from the runtime library
  
        # Debian/Ubuntu example - adjust for other distros
        # install compilers, utilities, zlib development support
        sudo apt install build-essential make autoconf automake git zlib1g-dev
        # download source code
        git clone https://github.com/get-iplayer/atomicparsley.git
        cd atomicparsley
        # build
        ./autogen.sh
        ./configure
        make
        # install in $PATH
        sudo make install

## macOS

* Install [Homebrew](https://brew.sh)

* Xcode command-line tools are installed with Homebrew
  
        # install additional utilities
        brew install autoconf automake
        # download source code
        git clone https://github.com/get-iplayer/atomicparsley.git
        cd atomicparsley
        # build
        ./autogen.sh
        ./configure
        make
        # install in $PATH
        sudo make install

## Windows

* Install [MSYS2 (64-bit)](https://www.msys2.org/wiki/MSYS2-installation/)

* 32-bit: Open "MSYS2 MinGW 32-bit" command prompt from Start Menu
  
        # install 32-bit toolchain
        pacman -S mingw-w64-i686-gcc
- 64-bit: Open "MSYS2 MinGW 64-bit" command prompt from Start Menu
  
        # install 64-bit toolchain
        pacman -S mingw-w64-x86_64-gcc

- 32-bit and 64-bit: Complete build
  
        # install additional utilities
        pacman -S make autoconf automake-wrapper git
        # retrieve source code
        git clone https://github.com/get-iplayer/atomicparsley.git
        cd atomicparsley
        # build
        ./autogen.sh
        ./configure
        make LDFLAGS=-static
        # copy AtomicParsley.exe to desired location

    
