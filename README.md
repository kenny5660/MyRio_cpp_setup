# MyRio c++ toolchain with OpenCv setup using plugin VisualGDB for Visual Studio 2017
1. [Download toolchain](https://yadi.sk/d/SXJelTVlKoA0qQ) and unpack to "C:\" for example. It contains official NI toolchain for MyRio, pre-compile OpenCV static libs (debug and release version), and lib for MyRio GPIO periphery.
2. Download Visual GDB plugin from [official site(pay or trial version)](https://visualgdb.com/download/) or [from torrent](http://newtracker.icu/viewtopic.php?t=5674513) and install.
3. Download and install [LabVIEW 2018 myRIO Toolkit](http://www.ni.com/download/labview-myrio-toolkit-2018/7421/en/) from official site. After that you can connect MyRio via USB.
4. Create new project by template "Linux project wizard"
5. Choose option "Create a project from a custom template", and choose template file "C:\arm_Myrio_2017\Project_templates\MyRio_template.vgdbxpt"(It's mine path, your path may be different). And press next.
6. Choose "Build the project locally with a cross-compiler". Then in "Cross-toolchain" choose "Locate a cross-toolchain by finding its gdb.exe", pick "C:\arm_Myrio_2017\sysroots\i686-nilrtsdk-mingw32\usr\bin\arm-nilrt-linux-gnueabi\arm-nilrt-linux-gnueabi-gdb.exe" and then click "Yes". At "Deployment computer" pick "Create new SSH connection", connect to MyRio by wifi or usb and enter valid params. Then click finish. You will see truble with link program, click "Ignore".
7. **Note, without this step the compiler will not be able to find standard includes such as "iostream" and similar.** Press "Alt+Enter", You will see "Project Properties". On the right, click "Linux project", set "Sysroot path" by value "C:\arm_Myrio_2017\sysroots\cortexa9-vfpv3-nilrt-linux-gnueabi" (It's mine path, your path may be different).
8. Building project will be OK. If all ok, You are a great programmer!
P.S. You can see file main.cpp with test program, which blink by MyRio GPIO A0, read GPIO A1, create and save test picture by OpenCv.  
