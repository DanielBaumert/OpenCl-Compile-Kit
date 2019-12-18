https://git-scm.com
	-> https://git-scm.com/download/win
https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2017
	-> https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16
https://docs.microsoft.com/en-us/windows-hardware/drivers/download-the-wdk
	-> https://go.microsoft.com/fwlink/?linkid=2085767

run git install
run vs_BuildTools install
	-> Select "C++ build tools" 
	-> install
run wdk install

under the documents create new folder named "OpenCL", move into it. 
Click into the space of that folder and then hold shift and press right-mouse. 
Now hit the "Open PowerShell window here" menu-item.

## Powershell
> git clone https://github.com/KhronosGroup/OpenCL-Headers.git
> git clone https://github.com/KhronosGroup/OpenCL-ICD-Loader

> mkdir .\OpenCL-ICD-Loader\inc\CL
> Copy-Item OpenCL-Headers/CL/* -Destination OpenCL-ICD-Loader/inc/CL -Recurse
> cd OpenCL-ICD-Loader
> mkdir build 
> exit

now open "Developer Command Prompt for VS 2019"

## Developer Command Prompt for VS 2019
> cd path/to/OpenCL-ICD-Loader/build #e.g.:
	-> e.g.: cd C:\Users\[Username]\Documents\[OpenCL]\OpenCL-ICD-Loader\build 
> cmake ..
> msbuild OPENCL_ICD_LOADER.sln /p:Configuration=Release

You will find the dll inside the build folder in Release folder :D

	