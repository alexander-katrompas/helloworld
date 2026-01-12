# C++ Hello World (Header/Implementation Separation)

This repository is a minimal **C++ “Hello, World!”** program designed to demonstrate:

- Clean separation between **interface** (`main.h`) and **implementation** (`main.cpp`)
- Professional, readable commenting and basic C++ conventions
- A simple and uniform compile workflow suitable for beginner programming students

---

## Project Files

### `main.cpp` — Implementation / Program Entry Point
- Contains the `main()` function, which is the starting point of program execution.
- Includes `main.h`.
- Outputs `Hello, World!` to standard output using the C++ standard library.

### `main.h` — Interface / Shared Declarations
- Contains shared `#include` directives.
- Demonstrates the use of **header guards** to prevent multiple inclusion.
- Represents how interfaces are separated from implementation in professional C++ projects.

### `.gitignore`
This project includes a deliberately strict `.gitignore` file intended for instructional purposes.

```
#ignore everything
*
*/

#unignore .cpp and .h, and this file, and the README
!.gitignore
!*.cpp
!*.h
!*.md
```

Only the following files are tracked by Git:
- C++ source files (`.cpp`)
- C++ header files (`.h`)
- Markdown documentation (`.md`)
- The `.gitignore` file itself

All compiled binaries and temporary files are intentionally excluded.

---

## Requirements

You must have:

- A Linux environment (Ubuntu recommended, including via VM)
- The GNU C++ compiler (`g++`)

Verify installation:

```bash
g++ --version
```

---

## Compilation Instructions (Required)

This project is assumed to compile using the following command:

```bash
g++ -I ./ *.cpp
```

### Explanation of the command

- `g++`  
  Invokes the GNU C++ compiler.

- `-I ./`  
  Adds the current directory to the include search path, allowing the compiler to locate `main.h`.

- `*.cpp`  
  Compiles all C++ source files in the directory.

### Default Output

If no output file is specified, the compiler produces an executable named:

```
a.out
```

---

## Recommended Compilation (Explicit Output Name)

For clarity and best practice, you may instead compile with:

```bash
g++ -I ./ *.cpp -o hello
```

This produces an executable named `hello`.

---

## Running the Program

### If compiled without `-o`:

```bash
a.out
```

### If compiled with `-o hello`:

```bash
hello
```

### Expected Output

```
Hello, World!
```

---

## Notes for Beginner Students

### Why separate `.h` and `.cpp` files?
While small programs can exist in a single file, professional C++ programs rely on separation of concerns:

- **Headers (`.h`)** define interfaces and shared declarations
- **Source files (`.cpp`)** contain implementation logic

This structure scales to large, multi-file projects.

### What is a header guard?
Header guards prevent multiple inclusion of the same header during compilation, which avoids duplicate definition errors.

Typical pattern:

```cpp
#ifndef HELLOWORLD_MAIN_H
#define HELLOWORLD_MAIN_H

// declarations

#endif
```

### Why use `std::cout`?
`std::cout` is part of the C++ Standard Library and provides a safe, portable way to write output to the terminal.

---

## Directory Structure

```
.
├── main.cpp
├── main.h
├── README.md
└── .gitignore
```

---

## Troubleshooting

### Executable not found
Rrun executables using `./`:

```bash
./a.out
```

### Undefined reference to `main`
Ensure `main.cpp` exists and is included in the compile command.

### Permission denied
Rare, but can be fixed with:

```bash
chmod +x hello
```
---
