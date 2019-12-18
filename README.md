> 12/18/2019
```cmd 
> git clone --recursive https://github.com/facebamm/OpenCl-Compile-Kit.git
```
# Install
Open the software folder or download the software below
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
Dowload the repositories [Optinal]
```cmd
> git clone https://github.com/KhronosGroup/OpenCL-Headers.git
> git clone https://github.com/KhronosGroup/OpenCL-ICD-Loader
```
Setup the ICD-Loader 
```cmd
> mkdir .\OpenCL-ICD-Loader\inc\CL
> mkdir .\OpenCL-ICD-Loader\build 
> Copy-Item OpenCL-Headers/CL/* -Destination OpenCL-ICD-Loader/inc/CL -Recurse
> exit
```
now open "Developer Command Prompt for VS 2019"

## Developer Command Prompt for VS 2019
```cmd
> cd path/to/OpenCL-ICD-Loader/build #e.g.:
```
e.g.: ```cd C:\[...]\[OpenCL]\OpenCL-ICD-Loader\build```
```cmd
> cmake ..
> msbuild OPENCL_ICD_LOADER.sln /p:Configuration=Release
```

You will find the dll inside the build folder in Release folder :D

# Version
to change the version you have only to replace the headerfiles inside the ``OpenCL-Headers/CL/`` folder

# Extra 
``cmake -A x64 ..`` -> AMD64<br/>
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
