
# Install
1. run git install<br/>
2. run vs_BuildTools install<br/>
2.1. Select "C++ build tools" <br/>
2.2. install<br/>
3. run wdk install

> Under the documents create new folder named "OpenCL", move into it.<br/>
> Click into the space of that folder and then hold shift and press right-mouse. <br/> 
> Now hit the "Open PowerShell window here" menu-item.<br/>

# Build and Compile
## Powershell
```cmd
> git clone https://github.com/KhronosGroup/OpenCL-Headers.git
> git clone https://github.com/KhronosGroup/OpenCL-ICD-Loader

> mkdir .\OpenCL-ICD-Loader\inc\CL
> Copy-Item OpenCL-Headers/CL/* -Destination OpenCL-ICD-Loader/inc/CL -Recurse
> cd OpenCL-ICD-Loader
> mkdir build 
> exit
```
now open "Developer Command Prompt for VS 2019"

## Developer Command Prompt for VS 2019
```cmd
> cd path/to/OpenCL-ICD-Loader/build #e.g.:
	-> e.g.: cd C:\Users\[Username]\Documents\[OpenCL]\OpenCL-ICD-Loader\build 
> cmake ..
> msbuild OPENCL_ICD_LOADER.sln /p:Configuration=Release
```cmd

You will find the dll inside the build folder in Release folder :D

# Version
to change the version you have only to replace the headerfiles inside the ``OpenCL-Headers/CL/`` folder

# Extra 
``cmake -A x64 ..`` -> AMD64 
``cmake -A x32 ..`` -> AMD32

# Pages and Downloads
## Git 
https://git-scm.com - Page<br/> 
https://git-scm.com/download/win - Download 
## Build Tools For Visual Studio 2019
https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2017 - Page<br>
https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16 - Download
## Windows Development Kit (WDK)
https://docs.microsoft.com/en-us/windows-hardware/drivers/download-the-wdk - Page<br> 
https://go.microsoft.com/fwlink/?linkid=2085767 - Download
