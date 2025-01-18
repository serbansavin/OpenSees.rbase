# OpenSees with rBase flavour

OpenSees's numerical data files are implemented with rBase kit.
OpenSees serves as a trial for the capabilities of the rBase lib.

This OpenSees builds with
-Python 3.12.5
-Visual Studio 17 2022
-Intel OneAPI 2024.2 (Base and HPC toolkits)
-conan 2.11.0

Use the steps below to build, as in parent OpenSees.
 mkdir build
 cd build
 call "C:\Program Files (x86)\Intel\oneAPI\setVars.bat" intel64 mod
 conan install .. --build missing --settings compiler.runtime="static"
 cmake .. -DBLA_STATIC=ON -DMKL_LINK=static -DMKL_INTERFACE_FULL=intel_lp64 -DMUMPS_DIR="..\..\mumps\build"
 cmake --build . --config Release --target OpenSees -j8
 cmake --build . --config Release --target OpenSeesPy -j8
 copy "C:\Program Files (x86)\Intel\oneAPI\compiler\2024.2\bin\libiomp5md.dll" .\Release
-----------------------------------------------------------------
Files
  - CMakeLists.txt
  - conanfile.py
have been modified to accomodate conan's upgrade from 1.x to 2.x.
-----------------------------------------------------------------

# OpenSees Source Code Repository

This git repository contains all revisions to OpenSees source code since Version 2.3.2.

Older revisions of the code are available upon request.

If you plan on collaborating or even using OpenSees as your base code it is highly recommended that
you FORK this repo to your own account and work on it there. We will not allow anybody to write to
this repo. Only PULL requests will be considered. To fork the repo click on the FORK at the top of this page.

For a brief outline on forking we suggest:
https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow

For a brief introduction to using your new FORK we suggest:
https://www.atlassian.com/git/tutorials/saving-changes

## Documentation
The documentation for OpenSees is being moved to a parellel github repo:
https://github.com/OpenSees/OpenSeesDocumentation

The documentation (in its present form) can be viewed in the browser using the following url:
https://OpenSees.github.io/OpenSeesDocumentation

## Build Instructions
Steps to build OpenSees on Windows, Linux, and Mac:
https://opensees.github.io/OpenSeesDocumentation/developer/build.html

## Modeling Questions
Issues related to modeling questions will be closed. Instead, post your modeling questions on the OpenSees 
message board or in the OpenSees Facebook group.
+ https://opensees.berkeley.edu/community
+ https://facebook.com/groups/opensees
