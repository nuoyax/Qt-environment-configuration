# Step 1:  environment configuration



Example with Qt 5.15.0
Using MSVC and VS2019
TODO: Add more details about configure
TODO: jom notes.
Prerequisites:

Perl http://www.activestate.com/activeperl
Python http://www.python.org/download/
Download Qt source zip from https://download.qt.io/archive/qt/5.12/5.12.10/



Extract, e.g. to C:\Qt\qt-5.15.0-src

Run x86 Native Tools Command Prompt for VS 2019

`cd C:\Qt\qt-5.15.0-src`

`mkdir ..\qt-5.15.0-static`

`set QTDIR=C:\Qt\qt-5.15.0-src\qtbase`

`set PATH=C:\Qt\qt-5.15.0-src\qtbase\bin;%PATH%`

`configure.bat -prefix d:\5.12.0_static-nod3d12 -debug-and-release -confirm-license -opensource -nomake examples -nomake tests -nomake tools -static -static-runtime -opengl  -no-feature-d3d12 -no-feature-accessibility -skip qtconnectivity`

`nmake`

`nmake install`

or
multi-thread accelerate to compile

`D:\Qt5.12\Tools\QtCreator\bin\jom\jom.exe  install`

notes: Fix Windows 7 issues by disabling `-no-feature-d3d12`

Some documentation for configure is at https://doc.qt.io/qt-5/configure-options.html

Install the Qt VS Tools extension https://marketplace.visualstudio.com/publishers/TheQtCompany

In Visual Studio Extensions -> Qt VS Tools -> Qt Options, add C:\Qt\qt-5.15.0-static and make it the default.

If working on an existing project, make sure to update Qt Installation in Extensions -> Qt Project Settings
