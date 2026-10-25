# Undergraduate Coursework and Projects

**English** | [简体中文](./README.zh-CN.md)

This repository collects selected coursework, lab exercises, and course projects that I completed during my undergraduate studies at the School of Software Engineering, Tongji University. It preserves the original assignment materials, source code, project files, and lab documentation. Most implementations use **C / C++**, covering Advanced Programming, Programming Paradigms, Data Structures, and Discrete Mathematics.

These materials document my progression from foundational programming exercises to data structure applications, algorithm implementation, and team development. The repository retains its original course and assignment organization; most exercises are standalone programs.

## Courses and Projects

| Course | Included materials | Documentation |
| --- | --- | --- |
| Advanced Programming | Chapter assignments, supplementary exercises, input handling examples, Tower of Hanoi and Popstar assignments, problem statements, and coding guidelines | [Advanced Programming](./Advanced-Programming/Readme.md) |
| Programming Paradigms | Nine foundational assignments, a Gomoku AI, and an auto-battler developed as a team project | [Programming Paradigms](./Programming-Paradigms/README.md) |
| Data Structures | Ten projects: examination registration, the Josephus problem, mazes, expression trees, family trees, keyword search, power grids, sorting, binary search trees, and N-Queens | [Data Structures Course Projects](./dataStructureAndConcreteMath/README.md#data-structures-course-projects) |
| Discrete Mathematics | Seven lab directories covering propositional logic, truth tables and canonical normal forms, relation closures, minimum spanning trees, and optimal binary trees | [Discrete Mathematics Labs](./dataStructureAndConcreteMath/README.md#discrete-mathematics-labs) |

## Repository Structure

```text
Tongji_University_SSE_Course_Projects/
├── Advanced-Programming/
│   ├── weeklyAssignment/           # Chapter assignments, extra exercises, and input handling
│   ├── pptAssignment/              # Topic-based assignment materials
│   ├── assignmentCodeStyle/        # Source formatting and compilation requirements
│   ├── Tutorial/                   # Development environment and I/O notes
│   ├── Hanoi/                      # Tower of Hanoi materials and program skeleton
│   └── Popstar/                    # Console-based Popstar game
├── Programming-Paradigms/
│   ├── assignment_1-1/ … 1-3/     # Stock prices and trading problems
│   ├── assignment_2-1/ … 2-3/     # Time intervals and scheduling problems
│   ├── assignment_3-1/ … 3-3/     # Duplicate detection and distance constraints
│   ├── fiveInARow/                 # Gomoku AI
│   └── Teamfight_Tactics/          # Auto-battler developed as a team project
└── dataStructureAndConcreteMath/
    ├── 数据结构程序设计/            # Ten standalone data structures projects
    └── concrete math/              # Discrete mathematics labs
```

`concrete math` is a historical directory name. Its contents are classified as Discrete Mathematics based on the accompanying course materials.

## Selected Projects

| Project | Scope and implementation |
| --- | --- |
| [Popstar](./Advanced-Programming/Popstar/) | A console game that separates the entry point, core logic, utility functions, and interface interactions across multiple source files. |
| [Gomoku AI](./Programming-Paradigms/fiveInARow/) | Board representation, pattern evaluation, simulated moves, and alpha–beta search, with a text protocol for communication with an external program. |
| [Teamfight Tactics](./Programming-Paradigms/Teamfight_Tactics/README.md) | An auto-battler developed as a team project with Cocos2d-x 3.17.2, covering combat logic, human and AI players, scene interactions, and client–server communication. Team roles and contribution records are documented in the project README. |
| [Data Structures Course Projects](./dataStructureAndConcreteMath/数据结构程序设计/) | Standalone applications of linked lists, stacks, trees, graphs, string matching, and sorting, with source code, Visual Studio projects, and DOCX documentation. |

## Development Environment and Execution

The existing Visual Studio C++ projects use the `v143` toolset. Visual Studio 2022 on Windows, with the corresponding C++ tools and Windows SDK installed, is the suggested environment. Refer to each project's `.vcxproj` for its specific configuration.

1. Select an exercise from the course documentation, then read its assignment or lab materials before reviewing the implementation.
2. For exercises with project files, open the corresponding `.vcxproj`. Some `.sln` files retain outdated directory references and require their project paths to be updated.
3. Create a separate C or C++ project for a single-file exercise, or include all required implementation files for a multi-file exercise. Keep the `main()` functions of independent exercises in separate executables.
4. Most Chinese source files use GBK / GB18030-compatible encodings. Check the file encoding if text appears garbled. Programs using Windows console APIs, Windows Sockets (Winsock), or MSVC extensions require the corresponding platform environment.

The Tower of Hanoi directory contains an incomplete program skeleton. The auto-battler archive does not include the Cocos2d-x engine directory; the required engine dependency must be supplied before building. Each course README provides further details about the archived materials and their use.

## Use and Attribution

This repository preserves undergraduate implementations for revisiting assignments, discussing approaches, and comparative study. Course requirements and development environments may differ across years. Use the original problem statements and concrete inputs to verify program behavior.

Team projects retain their original contributor and responsibility records. Some directories include a `LICENSE` file; consult the license in the relevant directory before using or redistributing its contents, and retain author attribution and copyright notices.
