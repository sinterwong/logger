# MLogger

## Description
MLogger is a C++ library that encapsulates the glog logging system, providing a simplified interface for logging within C++ applications. It is designed to be easy to integrate and use.

## Prerequisites
Before you begin, ensure you have the following installed:
- [Git](https://git-scm.com/)
- [CMake](https://cmake.org/download/) (version 3.10 or higher)
- A C++ compiler that supports C++20 (e.g., GCC, Clang, MSVC)
- The project uses `glog`, `gflags`, and `googletest` as Git submodules, which will be initialized during the setup process. No separate installation of these libraries is required.

## Getting Started

### Building the Project
Follow these steps to clone the repository, initialize submodules, and build the project:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/mlogger.git # Replace with the actual URL
    cd mlogger
    ```

2.  **Initialize Git submodules:**
    MLogger uses Git submodules for its dependencies (glog, gflags, googletest).
    ```bash
    git submodule update --init --recursive
    ```

3.  **Configure the project with CMake:**
    Create a build directory and run CMake from there:
    ```bash
    mkdir build
    cd build
    cmake ..
    ```
    *Optional: Specify a generator for CMake if needed, e.g., `cmake .. -G "Visual Studio 17 2022"` for Visual Studio.*
    *Optional: You can customize the build type (default is `RelWithDebInfo`): `cmake .. -DCMAKE_BUILD_TYPE=Debug` or `cmake .. -DCMAKE_BUILD_TYPE=Release`.*


4.  **Build the project:**
    ```bash
    cmake --build .
    ```
    *Optional: For multi-configuration generators (like Visual Studio), specify the configuration: `cmake --build . --config Release`.*
    The compiled library (`liblogger.so` or `logger.dll`) will be located in `build/<target_arch>/lib` and executables (if any) in `build/<target_arch>/bin`.

## Running Tests
The project includes unit tests built with GoogleTest. Tests are enabled by default (`BUILD_TESTS=ON`).

1.  **Build the project (if not already done):**
    Follow the steps in the "Building the Project" section. Ensure tests are enabled (which they are by default).

2.  **Run the tests:**
    The test executable `main` will be located in `build/<target_arch>/bin/tests/`.
    Navigate to your build directory and run the tests:
    ```bash
    cd build
    # The exact path to the test executable might vary slightly based on your CMake configuration and generator.
    # It's typically in a subdirectory like 'bin/tests' or directly in 'tests' relative to the build root.
    ./<target_arch>/bin/tests/main
    ```
    Or, if you are in the `build` directory, you can use CTest:
    ```bash
    ctest
    ```

## Contributing
Contributions are welcome! If you'd like to contribute, please follow these general guidelines:
1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Make your changes.
4.  Ensure your code adheres to the existing style.
5.  Write unit tests for your changes.
6.  Ensure all tests pass.
7.  Submit a pull request.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
Copyright (c) 2025 Sinter Wong
