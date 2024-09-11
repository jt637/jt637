# How to Set Up Debugging C code in Visual Studio for Computer Science Students

### Intro
  Debugging is an essential process for computer science students and programmers in general. Visual Studio, one of the most popular compilers, offers a visual debugger that can be used to test and fix software. To set up the debugger, you will need an operating system with a user interface and the Visual Studio compiler. Once you have met these prerequisites, there are four simple steps to follow. First, create a new C project in Visual Studio. Second, create your .c and .h files. Third, create a CMakeLists.txt file that will generate a Makefile and an executable. Fourth, point the debugger to your executable file, and then you can run the debugger. Debugging allows you to execute your code line by line, examine variables, and detect and fix errors. By following these simple steps, you can utilize the power of the visual debugger in Visual Studio to become a better programmer.

### What You Will Need to Utilize This Debugger
 1. **An Operating System with a User Interface**
    - Visual Studio uses a Visual Debugger. You cannot utilize the full power of the    debugger if you do not have a User Interface.

 2.  **The Visual Studio Compiler**
        - If you are on windows you can download from this link https://visualstudio.microsoft.com/downloads/
        -If you are on linux, on your desktop go to the search bar. Type 'terminal' and press 'Enter' to launch the terminal.
        -In the terminal type ```sudo snap install --classic code```
        - Now the rest of instruction set will be the same whether you are on Windows or linux

### How to setup Debugging
 1. **Create Your C Project in Visual Studio**
    - When you first launch Visual Studio you will be prompted with this screen
    ![image](files://X:/Documents/english/instruction_set/create_new_project.PNG)
    - Select "Create New Project"
 2. **Creating Your .c and .h Files**
    - On the right hand panel after you create your project you will see the layout and contents of your project directory.
    - Click the small page icon to create a new file. Name the file ```test.c```
    ![image](https://user-images.githubusercontent.com/65826366/229682380-ae2da4b1-6f94-4ab4-a307-7da57011edff.png)

        - This is where you are going to put your program, all of your functions and your main function.
        - Create these functions,
        ```
        #include stdio.h

        int doSomething(char[] parameter){
            printf("Hello World!", parameter);
        }
        ```
        - And your main functions will look like this,
        ```
        void main(){
            char[] name = "Justin"
            doSomething(name);
        }
        ```
    - Make another file called ```test.h```
    - This file will contain all of the function names of that you are using in your .c file minus the main function.
        - for example, if your .c file contains the functions above, your .h file will look like this
        ```
        int doSomething(int parameter);
        ```
 3. **Now You are Ready to Make a CMakeLists.txt !**
    - Again click the add file button, and name this file CMakeLists.txt . This file will combine all of your other files into one executable.
    - The format of this program is very simple. Because our project only has two files the CMakeLists will look like this
    ```
        cmake_minimum_required(VERSION 2.8)
        project(calc-2.4.0)
        set(SOURCE_EXE test.c test.h)
        add_definitions(-Wall -O2)
        include_directory(${CMAKE_CURRENT_SOURCE_DIR})
        add_executable(tester ${SOURCE_EXE})
    ```
    - Now right-click this file on the right-hand panel and click ```Generate  CMake cache```
    - You have now created an executable. Click on the debugger on the left panel and then in the dropdown menu select the name of the executable. In this case the file is named "tester".
4. **Debugging**
    - Now that you are in the debugging menu, when you click the run button your program will launch in debugging mode.
    - Click the red dot to the left of the 7th line.
    - Click the Run button. The program will run until the 7th line and stop.
    - Click this arrow button to step the the next line. In the left panel you should see a list of the variables. This will show you your char[] name variable and its contents.
    - This is how you set up the debugger for a very simple program in Visual Studio.
