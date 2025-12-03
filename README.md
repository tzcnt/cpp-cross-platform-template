C++ Windows/Linux cross-platform quickstart based on clang + CMake

Contains reasonable (IMO) presets to build the same application on different environments:

| OS | IDE | Compiler | Navigation |
| --- | --- | --- | --- |
| Linux | VSCode | clang | clangd |
| Linux | VSCode | gcc   | clangd |
| Windows | Visual Studio 2017+ | clang-cl | clangd |
| Windows | Visual Studio 2017+ | MSVC | IntelliSense |
| MacOS   | VSCode | Apple Clang | clangd |

For VSCode, the extensions "clangd" and "CMake Tools" are required.

Debug, Release, and RelWithDebInfo presets are provided for all environments.

### Linux Setup
Minimum system packages: `cmake`, `ninja-build`, and `clangd`.
Additional system packages: `llvm`, `lldb-dap`.

Just open this folder in VSCode.

### Windows Setup
Install Visual Studio Community latest edition. In the VS installer select these additional components:
- LLVM
- CMake

Make sure "clangd" is available on your path.
1. Run "x64 Native Tools Command Prompt for VS \<version\>" from your Start Menu.
2. In the terminal, type `clangd --version` and it should print version info.

Then you can open this project folder in Visual Studio. Select a build configuration from the dropdown.

To open this project in VSCode, you need to first use the Visual Studio terminal which sets up necessary environment variables.
You will need to do this step every time.
1. Run "x64 Native Tools Command Prompt for VS \<version\>" from your Start Menu.
3. In the terminal, type `code` and press enter.
4. Open this project folder from the VSCode Open menu.
