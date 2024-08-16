# Simple C++ Project

This repository contains a simple C++ project set up for use with Visual Studio Code. The project includes a basic C++ source file, along with configuration files for IntelliSense and file associations.

## Files

- **simple.cpp**: The main C++ source file.
- **c_cpp_properties.json**: Configuration file for IntelliSense, specifying paths, standards, and compiler options.
- **settings.json**: VSCode settings file with custom file associations and CMake settings.

## Project Structure

```plaintext
.
├── .vscode/
│   ├── c_cpp_properties.json
│   └── settings.json
└── simple.cpp

c_cpp_properties.json
This file configures IntelliSense for the project. Key configurations include:

includePath: Specifies the paths to the header files. The project is configured to include headers from TBB and the workspace.
compilerPath: Path to the GCC compiler.
cStandard: C standard used in the project (gnu11).
cppStandard: C++ standard used in the project (gnu++17).
settings.json
VSCode settings configured for the project:

cmake.configureOnOpen: Set to false to prevent automatic CMake configuration on opening the project.
files.associations: Maps common C++ standard library headers and other file types to the C++ language.
Requirements
GCC Compiler
Visual Studio Code
CMake (optional)
Getting Started
Clone the repository:

git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name


##Instructions

1. Replace `"yourusername"` and `"your-repo-name"` with your actual GitHub username and the repository name.
2. Update the **License** section if you are using a different license.

This `README.md` should give users a clear understanding of the project's structure and how to get started.

Designed By Sparsh Kumar used RISK V CPU



### 2. `.github/workflows/cpp.yml`

```yaml
name: C/C++ CI

on: [push, pull_request]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Install GCC
      run: sudo apt-get install g++-10

    - name: Build
      run: |
        g++-10 -std=gnu++17 -o simple simple.cpp

    - name: Run Tests
      run: ./simple
