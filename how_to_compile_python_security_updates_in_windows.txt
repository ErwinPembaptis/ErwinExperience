Please do these steps orderly, thoroughly. That means, you must do it in order, from first to the last without skipping any step.

Minimum requirements:
- 15 Giga Bytes of free storage. You need this much because you will know later.
- Internet access, do not use your mobile data unless you are crazy (rich).
- Computer (either PC or a laptop) with a good propeller. Without it, your processors will likely to be burnt to ...
- If you have better processor the compilation will be faster.
- SSD will help you so much. So much that your computer will thank you.
- Silly but please set your Windows power plan (power mode) to "High Performance".

1. Unfortunately, you will have to install Visual Studio Community (it is different from Visual Studio Code!). For example, Visual Studio 2022 Community.
.... 1.1 In June 2024, the link to download the Visual Studio Community is (https://visualstudio.microsoft.com/vs/community/). Scroll down until the bottom of the page so that you can see that "Free Download" button.
.... 1.2 After you get that "VisualStudioSetup.exe" file, launch it.
.... 1.3 Check "Desktop development with C++". This will download the compiler we need.
.... 1.4 Check "Python development". This will download CPython so that the compiler can compile our CPython.
.... .... 1.4.1 After you check "Python development", in the right screen, check "Python native development tools". We will need this.

= Installation Details =
Visual Studio core editor
Desktop development with C++
Python development
- Included
  * Python language support
- Optional
  * xxx
  * xxx
  * Python native development tools <--- CHECK THIS!
  * xxx

.... 1.5 Wait for the installation to finish. This will take time (and mobile data).
2. Unfortunately again, you will also have to turn on .NET Framework 3.5 (includes .NET 2.0 and 3.0). You can turn that on inside "Turn Windows features on or off".
3. Get your CPython source code. For example, CPython 3.10.14 from (https://www.python.org/downloads/release/python-31014/).
4. Extract the compressed source where ever you would like so that you can see that cpython-x.xx.xx folder. For example, (cpython-3.10.14).
5. If you want to build the CPython with the installer, navigate to cpython-3.10.14/Tools/msi in your CMD.
.... 5.1 Type (buildrelease.bat -x64 --pgo). Flag -x64 will tell the compiler to build 64-bit version of the CPython. Flag --pgo will tell the compiler to use Profile Guided Optimization. Just know that it is some kind of optimisation, which is used by the python.org by default.
.... 5.2 Wait until it finish download everything and compile everything. This will take much time (and mobile data).
.... 5.3 Once finished, the installer can be found inside cpython-3.10.14/PCbuild/amd64/en-us/python-3.10.14-amd64.exe. The rest of the files inside the same folder contains all the logical and resources needed to perform an installation process. Do not touch them or run them manually. If you want to distribute it to other system, then you will also have to include that setup file with its friends (logical and resources files mentioned before) inside the same folder.
6. If you want to build the CPython without the installer, only executable CPython, navigate to cpython-3.10.14/PCbuild in your CMD.
.... 6.1 Type (build.bat -p x64 --pgo). If you do not want to use the PGO, type (build.bat -p x64 -c Release) but please remember that you are unoptimised now and will likely to be slower in certain cases.
.... 6.2 Wait until it finish download everything and compile everything. This will take much time (and mobile data).
.... 6.3 Once finished, the executable can be found inside cpython-3.10.14/PCbuild/amd64/python.exe. But it is very dirty because the folder still contains all the compilation files and I do not know how to clean it.
.... 6.4 If you run the step number 5, which I recommend to do, you will also find the executable cpython-3.10.14/PCbuild/amd64/python.exe.
