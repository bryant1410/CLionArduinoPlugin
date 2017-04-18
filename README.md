# CLion Arduino Plugin

This is a JetBrains CLion plugin that integrates [Arduino CMake](https://github.com/francoiscampbell/arduino-cmake) into the IDE.

The current features are to create an Arduino CMake project in one click, and to create new sketch files.

For those asking how to upload, you need to specify the serial port in the CMakeLists.txt file. For example:

    set(${CMAKE_PROJECT_NAME}_BOARD uno)
    set(${CMAKE_PROJECT_NAME}_PORT /dev/ttys0)

This will create the 'upload' configuration in your Run Configurations and you can click the Run button or use the keyboard shortcut to upload.

Future features are to add menu option to easily change the board type, port number, import existing Arduino projects, etc.

## Update on status:
It seems that arduino-cmake (the backing plugin) development has pretty much stalled, which is the root cause of most of the issues here, so I've got my own fork and I've tried to implement most of the fixes from previous forks of the project, which are also mostly dead. This project was just an exercise in making a JetBrains plugin that turned out well, but I don't have a lot of free time on my hands to do this though, what with full-time university and what not, so I can't give a definite date on what will be fixed when, but I will make an effort to get it done.

## Release Notes

**1.2.2**

*   Fixed .ino and .pde files not refactorable. Increased compatibility for Servo library</li>

**1.2.1**

*   Re-compiled for Java 6

**1.2.0**

*   Added new project creation to Welcome Screen and File menu

**1.1.0**

*   Compatiblity with Arduino SDK 1.6 on Mac OS X

**1.0.2**

*   Removed Groovy runtime, no longer necessary

**1.0.1**

*   Fixed organization

**1.0**

*   Convert a project to Arduino CMake. This replaces CMakeLists.txt with a default one, deletes the default main.cpp file, copies in the Arduino CMake toolchain files, and deletes the build direcory to start fresh
*   Associates .ino and .pde files as C++ source, so you get syntax highlighting and prediction, etc.
*   Create a new sketch file in any directory. If you omit the extension, it will add .ino automatically
*   Adds import for Arduino.h to all newly created sketch files to enable code completion
*   Compiled with Java 6 for compatibility with OS X out of the box
