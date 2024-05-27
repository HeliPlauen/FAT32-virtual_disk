FAT32 disk emulator - creates a wirtual copy of folder where app was started.

It was created using WinFsp open-source library and it is a Windows Service.

The step by step instruction how to create it is here: https://github.com/winfsp/winfsp/blob/master/doc/WinFsp-Tutorial.asciidoc#testing-the-file-system

Works with Windows only!!! It was created using Visual Studio 2019 and should run using Visual Studio!!!

1. Install WinFsp

2. Link hearders and dll
C/C++ > General > Additional Include Directories: $(MSBuildProgramFiles32)\WinFsp\inc
Linker > Input > Additional Dependencies: $(MSBuildProgramFiles32)\WinFsp\lib\winfsp-$(PlatformTarget).lib
Linker > Input > Delay Loaded Dll’s: winfsp-$(PlatformTarget).dll

3. Put as a command line argument 
-p "E:\A_OLEG\TEST TASKS\YY\Task3\tests\FAT32emulator\x64\Debug" -m Y:
It will mount drive Y:

4. DO NOT USE COMMAND LINE!!!! RUN USING VISUAL STUDIO DEBYG!!! IGNORE RED UNDERLINES !!!

5. When Y: is mounted - run powershell, input cd Y: - and you may work with virtual drive! You should see it also if open "My Computer"

6. Commands are implemented: ls, cd, mkdir, New-Item(instead of touch!!!) and many others....
