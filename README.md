# ApolloCrossDev

1. Visual Studio Code
    1. Download and install VSC
    2. Install Microsoft C/C++ Extension + Extension Pack and Themes
    3. Install Amiga Assembly Extension (Paul Raingeard)
    4. Install GitHub Pull Requests and Issues Extension
    5. Clone amiga-gcc into a local repository
2. Build Amiga-GCC Compiler (Bebbo Franken)
    1. MacOS
        1. Download and install Homebrew package manager
        2. brew install bash wget make lhasa gmp mpfr libmpc flex gettext gnu-sed texinfo gcc@12 make autoconf bison
        3. sudo make all SHELL=$(brew --prefix)/bin/bash
    2. Windows
    3. Linux
3. Visual Studio Code Workspace (Paul Raingeard)  
    1. Clone vscode-amiga-gcc-example into a local repository
    2. Edit .vscode/c_cpp_properties.json file
        1. "includePath": ["/opt/amiga/**”]
        2. "compilerPath": "/opt/amiga/bin/m68k-amigaos-gcc"
    3. Edit .vscode/launch.json file
        1. "miDebuggerPath": "/opt/amiga/bin/m68k-amigaos-gdb"
        2. "miDebuggerPath": "/opt/amiga/bin/m68k-amigaos-gdb.exe"
        3.         {
        4.             "type": "uae-run",
        5.             "request": "launch",
        6.             "name": "Run",
        7.             "buildWorkspace": true,
        8.             "windows": {
        9.                 "emulator": "${config:amiga-assembly.binDir}/fs-uae.exe"
        10.             },
        11.             "osx": {
        12.                 "emulator": "${config:amiga-assembly.binDir}/fs-uae"
        13.             },
        14.             "linux": {
        15.                 "emulator": "${config:amiga-assembly.binDir}/fs-uae"
        16.             },
        17.             "emulatorWorkingDir": "${config:amiga-assembly.binDir}",
        18.             "options": [
        19.                 "--chip_memory=2048",
        20.                 "--hard_drive_0=${workspaceFolder}/fs-uae/hd0",
        21.                 "--amiga_model=A1200",
        22.                 "--automatic_input_grab=0"
        23.             ],
        24.             "preLaunchTask": "Build"
        25.         }
    4. Edit .vscode/settings.json file
        1. "file": "/opt/amiga/bin/vasmm68k_mot"
    5. Edit Makefile
        1. AMIGA_GCC_ROOT=/opt/amiga
    6. Give access permissions to /opt/amiga (and all subfolders)
    7. Copy ApolloROM_UAE.rom to fs-uae folder
