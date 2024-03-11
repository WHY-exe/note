# 1. CMake Directory Structure

There are two directories cmake use when building a project: the source directory and binary directory. 

1. The source directory is where the source code and the **CMakeLists** file for the project is located.
2. The binary directory is where cmake put the resulting object file(like the generated project files for the certain generator), and resulted binary file(static/shared libs, and exe)

The cmake won't write any file to the source directory, only to the binary directory. 

It is often encourage to seperate the binary directory and the source directory so that you could build binary with different option and leave a clean source tree(Trust me, you wouldn't want to see the generated file everywhere in your project directory). Some pratice would look like this:

```bash
# the root dir of your project
mkdir build
cd build
# now you are on the cmake binary dir
cmake <your_build option> ..
```



# 1. Specify the cmake version

Usually you would want to specify the cmake minimun version requirement and the **policy range** at the beginning of the **CMakeList.txt**

```cmake
cmake_minimum_required(VERSION <min>[...<policy_max>][FATAL_ERROR])
```

When the cmake version is less than the **min** requirement, the cmake would stop processing project and raise an error. Howerver, when the cmake version is greater than the **policy_max** it would normally process the project. **The policy_max only affect the cmake policy mechanism**

The FATAL_ERROR option is accepted but ignored by cmake 2.6 or higher

man link: [cmake_minimum_required — CMake 3.29.0-rc3 Documentation](https://cmake.org/cmake/help/latest/command/cmake_minimum_required.html)
