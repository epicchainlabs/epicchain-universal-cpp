# EpicChain-Universal-Cpp

## Portable EpicChain for All Things

**EpicChain-Universal-Cpp** is a groundbreaking C++ development toolkit crafted to make EpicChain's blockchain capabilities accessible across a broad spectrum of platforms. Our goal is to provide a versatile and high-performance solution that enables the integration of EpicChain functionalities into environments ranging from high-end servers to constrained microcontrollers. By harnessing the power and efficiency of C++, this toolkit aims to bridge the gap between modern blockchain technologies and resource-limited systems.

### Why Opt for C/C++?

Many contemporary blockchain frameworks are built using high-level programming languages that may not be well-suited for use in environments with limited computing resources, such as embedded systems or microcontrollers. C and C++ offer a combination of performance and portability that is well-suited for developing lightweight and efficient blockchain applications. These languages are compatible with nearly all other programming languages, allowing for the creation of modular components that can be integrated into diverse projects across various platforms.

#### C++ Standard

In **EpicChain-Universal-Cpp**, we currently use C++11 to ensure broad compatibility with existing tools and compilers. However, we are planning to migrate to C++17 as soon as it is feasible, provided that it does not disrupt compatibility with any existing modules or tools. Adherence to the [CppCoreGuidelines](https://epic-chain.org/docs/) is highly encouraged to maintain high standards of code quality and consistency throughout the project.

#### IDE Recommendations

For an optimal development experience with **EpicChain-Universal-Cpp**, we recommend using the Visual Studio Code (VSCode) IDE, along with the following extensions:
- **C/C++** (Version 0.23.0-insiders2 or later) for basic C++ support.
- **C++ Intellisense** (Version 0.2.2 or later) for advanced code completion and navigation.
- **GoogleTest Adapter** (Version 1.8.3 or later) for seamless integration with Google Test framework.

#### Code Style Guidelines

To ensure a consistent and readable codebase, **EpicChain-Universal-Cpp** adopts the Mozilla C++ style with an indentation level of 3 spaces. For configuring VSCode to match this style, use the following settings:
```json
{
    "[cpp]": {
        "editor.tabSize" : 3,
        "editor.detectIndentation": false
    },
    "C_Cpp.clang_format_fallbackStyle": "{ BasedOnStyle : Mozilla , ColumnLimit : 0, IndentWidth: 3, AccessModifierOffset: -3}"
}
```

**Variable Naming Style** in this project follows conventions inspired by the C# language, employing CamelCase for naming variables and methods. Public variables begin with uppercase letters, while private and local variables start with lowercase letters. This approach is intended to maintain compatibility with reference projects and ensure a coherent codebase.

#### Code Quality Tools

To uphold code quality standards, use the `make lint` command for automatic code formatting with `clang-format` and practice verification with `clang-tidy`. These tools help maintain clean and efficient code.

### Main Modules

**EpicChain-Universal-Cpp** is organized into three main modules, each located within the `src` directory:

- **common**: This module contains shared components, such as data structures and cryptographic algorithms, that are used across different versions of EpicChain.
- **epicchain**: This module pertains to EpicChain Blockchain version 3 and beyond and includes:
  - **cli**: The command-line interface for interacting with EpicChain.
  - **epicchain**: Core functionalities related to the blockchain itself.
  - **nvm**: The EpicChain Virtual Machine (EpicChainVM) version 3, now maintained as a separate project from the core blockchain.
- **epicchain**: This module focuses on EpicChain Blockchain version 2 and comprises:
  - **cli2**: The command-line interface for version 2.
  - **epicchain**: Core blockchain functionalities specific to version 2.

#### Detailed Module Breakdown

- **common**: Houses essential data structures and cryptographic tools that are applicable to various EpicChain versions.
  
- **epicchain** (Version 3 and beyond):
  - **mempool**: Manages peer-to-peer protocol and networking functionalities.
  - **smart**: Handles ApplicationEngine and SmartContract processes.
  - **ledger**: Responsible for blockchain data persistence.
  - **consensus**: Implements the dBFT (delegated Byzantine Fault Tolerance) consensus mechanism.

- **epicchain**:
  - **core**: Contains the main functionalities for EpicChain version 2.
  - **nvm**: Implements EpicChainVM 2.x, depending exclusively on the core functionalities.
  - **smart**: Manages ApplicationEngine and SmartContract functionalities.
  - **mempool**: Handles peer-to-peer protocol and networking.
  - **ledger**: Responsible for blockchain persistence.
  - **consensus**: Implements the dBFT consensus mechanism.

### Building the Project

#### Dependencies

Before you start building, ensure that the required dependencies, such as `openssl` and `gtest`, are installed. These dependencies are included as a git submodule. Initialize and update the submodules using:
```bash
make vendor
```

#### On Linux

To build the project on Linux, execute the following commands:
```bash
make
make cli
```
These commands will compile the `epicchain-cli` and place the binary in the `bin` folder. To run tests, use:
```bash
make test
```

#### On Windows and Other Platforms

Support for Windows and other platforms is planned for future updates. Detailed instructions will be provided as the project evolves.

### Testing

Testing is an integral part of the development process. Navigate to the `tests` directory and run:
```bash
make tests
```
Additionally, generate HTML coverage reports with `lcov`:
```bash
make coverage
```
Ensure `lcov` is installed (e.g., `apt install lcov`) to use coverage reporting features.

### Versioning

**EpicChain-Universal-Cpp** follows semantic versioning guidelines ([semver](https://semver.org)). Version numbers are aligned with the EpicChain reference implementation. For instance, a version like `ref2.9-v0.2.1` indicates **EpicChain-Universal-Cpp** version 0.2.1 for EpicChain reference version 2.9.x. The `0.x` versioning will persist until the project reaches a stable release.

### Project Roadmap

The roadmap for **EpicChain-Universal-Cpp** includes:
1. **Core**: Establishing the fundamental components of the toolkit.
2. **VM**: Developing the virtual machine and its interoperation layer.
3. **Ledger**: Implementing persistence mechanisms, even in volatile memory.
4. **Mempool**: Managing transaction pooling and broadcasting.
5. **Consensus**: Creating and refining consensus algorithms.

### How to Achieve These Goals

The primary focus is on delivering a comprehensive and portable implementation as swiftly and efficiently as possible. While optimization will follow, the initial goal is to provide a functional and testable system. Safety and reliability are prioritized, even if the solution is not fully optimized at the outset.

### License

**EpicChain-Universal-Cpp** is currently licensed under the MIT License. We may consider migrating to the Apache 2.0 License in the future, depending on project needs.

**EoicChain Community** (2024)
