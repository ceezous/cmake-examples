- 从`output-from-build.md`来看，生成的目标文件似乎是被放在了`.vcxproj`里面;
- buil的结果似乎在`hello_headers.lastbuildstate`里可以看到;
- Visual Studio中各种filters的名称似乎和CMakeLists.txt中，处理的对象名称有关;
- 关于`Windows SDK`: [Microsoft Windows SDK](https://zh.wikipedia.org/wiki/Microsoft_Windows_SDK);
- 01-D不知道为什么不能被build，显示错误为`LNK1181	cannot open input file 'Release\hello_library.lib'`;
- `CMakeLists.txt`中的target似乎是指哪些被执行操作的“变量”;
- 大写的变量似乎都是系统的保留字;
- 01-E在被build的时候也发生了找不到文件的问题，似乎和**build平台在windows下**有关;
- 关于`target`
  - [Why does CMake make a distinction between a "target" and a "command"?](https://stackoverflow.com/questions/11971917/why-does-cmake-make-a-distinction-between-a-target-and-a-command)
    - In general, targets comprise **executables** or **libraries** which are **defined** by calling add_executable or add_library and which can have many properties set.
- install的作用

## commands
- add_library()
  - The add_library() function is used to create a library from some source files.
  - As mentioned in the previous example, we pass the source files directly to the add_library call, as recommended for modern CMake.
- target_include_directories()
  - In this example (01-C), we include directories in the library using the target_include_directories() function with the scope set to PUBLIC.
- add_executable()
- target_link_libraries()
  - When creating an executable that will use your library you must tell the compiler about the library. This can be done using the target_link_libraries() function.