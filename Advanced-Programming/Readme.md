# Advanced Programming

**English** | [简体中文](./README.zh-CN.md)

This directory archives selected C / C++ assignments I completed for the Advanced Programming course during my undergraduate studies at Tongji University, together with the corresponding problem statements, coding guidelines, and lab materials. Topics include basic syntax, control flow, functions and recursion, arrays and strings, pointers, structures, and classes. It also includes materials for the Popstar and Tower of Hanoi integrated assignments.

The files retain their original implementations and organization from the course, providing a record of problem-solving approaches, input handling, and the organization of programs across multiple source files.

## Directory Guide

| Directory | Contents |
| --- | --- |
| [weeklyAssignment](./weeklyAssignment/) | Source code for Chapters 3–7, problem statements in PDF for selected chapters, input-handling examples, and supplementary exercises. |
| [pptAssignment](./pptAssignment/) | Topic-based problem statements covering sequential execution, selection, iteration, input-error handling, string length, and expression evaluation. |
| [assignmentCodeStyle](./assignmentCodeStyle/) | Course guidelines for source formatting, compilation, and assignment submission. |
| [Tutorial](./Tutorial/) | Notes on Visual Studio 2022 warnings, input/output redirection, and pipe operators. |
| [Popstar](./Popstar/) | The Popstar assignment specification, game logic, and Windows console interaction code. |
| [Hanoi](./Hanoi/) | The Tower of Hanoi demonstration specification, program entry point, menu, function declarations, and console utilities. |

## Chapter Assignments

| Directory | Main Topics |
| --- | --- |
| [chapter3](./weeklyAssignment/chapter3/) | Input/output, numerical calculations, branching and loops, formatted output, and input validation; selected problems include both C and C++ implementations. |
| [chapter4](./weeklyAssignment/chapter4/) | Functional decomposition, recursion, and the organization of programs across multiple source files. |
| [chapter5](./weeklyAssignment/chapter5/) | Arrays, character arrays, string processing, and the `string` class. |
| [chapter6](./weeklyAssignment/chapter6/) | Pointers, character traversal, and related function exercises. |
| [chapter7](./weeklyAssignment/chapter7/) | Structures, nested structures, function overloading, classes, and objects. |
| [InputSolution](./weeklyAssignment/InputSolution/) | Recovery from input failures and repeated input in C and C++. |
| [additionalWorks](./weeklyAssignment/additionalWorks/) | Supplementary exercises and lab code retained under their original assignment identifiers. |

Chapter directories retain the original problem identifiers and filenames. Some assignments store the entry point, function implementations, and header files separately. Start with the problem statement, then read the source files with the corresponding identifier.

## Integrated Assignments

### Popstar

The project represents the game board as a two-dimensional array. Its game logic covers identifying adjacent blocks of the same color, removing blocks, applying gravity, and compacting the board. Text and mouse interaction are provided through the Windows console.

- `popstar-main.cpp`: program entry point and feature menu.
- `popstar-base.cpp`, `popstar-tools.cpp`: basic operations and game-processing functions.
- `popstar-console.cpp`: console interface and interaction implementation.
- `popstar.h`, `cmd_console_tools.*`: function declarations and console utilities.

The menu includes modes for highlighting removable blocks, performing a single elimination, completing a level, and using a console-based graphical interface. These modes illustrate how game logic and interaction code are organized separately.

### Tower of Hanoi

This directory retains part of the integrated demonstration assignment. `hanoi_main.cpp` provides the program entry point, `hanoi_menu.cpp` implements the menu, `hanoi.h` declares the related functions, and `cmd_console_tools.*` supplies console operations.

In the current archive, `hanoi_multiple_solutions.cpp` contains only template comments, without the execution functions required by the menu options. The available files therefore do not provide a complete buildable Tower of Hanoi demonstration. Read the menu alongside the assignment PDF to understand the original requirements.

## Building and Running

The assignments were primarily developed for Windows / Visual Studio. This directory does not include a shared project file or build script. Each assignment is an independent program and should be configured and compiled separately.

1. Single-file assignments: create a separate console project for the selected `.c` or `.cpp` file.
2. Assignments with multiple source files: add the entry point, implementation files, and headers for the same assignment to one project.
3. Popstar: compile `popstar-main.cpp`, `popstar-base.cpp`, `popstar-console.cpp`, `popstar-tools.cpp`, and `cmd_console_tools.cpp` together, retaining the corresponding headers.

Several exercises define their own `main()` functions. Keep entry points from different assignments in separate executable projects. Some source files use `windows.h`, `conio.h`, `_getch()`, or MSVC-specific interfaces and require the corresponding Windows development environment. If Chinese comments or strings appear garbled, try opening the source files with a GBK / GB18030-compatible encoding and check the compiler's character-set settings.

## Reference Notes

The source code documents my early programming studies. Consult the individual files for each assignment's requirements, implementation, and completion status. When using the material as a reference, analyze the original problem independently and verify the results with ordinary and boundary inputs. Assignment arrangements may differ between academic years; follow the requirements for the relevant course offering.

[Return to the repository overview](../README.md)
