C++ Windows/Linux cross-platform quickstart based on clang + CMake

Contains reasonable (IMO) presets to build the same application on different environments:

| OS | IDE | Compiler | Navigation |
| --- | --- | --- | --- |
| Linux | VSCode | clang | clangd |
| Windows | Visual Studio 2017+ | clang-cl | clangd |
| Windows | Visual Studio 2017+ | MSVC | IntelliSense |

For VSCode, the extensions "clangd" and "CMake Tools" are required.

Debug, Release, and RelWithDebInfo presets are provided for all environments.

(to be added: Linux / VSCode / gcc)
