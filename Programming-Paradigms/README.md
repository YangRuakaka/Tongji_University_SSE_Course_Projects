# Programming Paradigms Coursework and Projects

**English** | [简体中文](./README.zh-CN.md)

This directory contains individual assignments and team projects from the Programming Paradigms course at Tongji University's School of Software Engineering, primarily written in C++. The collection ranges from standalone array and interval exercises to Gomoku search algorithms and a Cocos2d-x auto-battler, documenting undergraduate practice in problem modeling, program organization, and team development.

## Practice Assignments

| Assignment | Problem | Main approach in the current implementation |
| --- | --- | --- |
| [assignment_1-1](./assignment_1-1/) | For each day's stock price, calculate the number of days until the next higher price | Traverse arrays using pointers and search subsequent prices for each element |
| [assignment_1-2](./assignment_1-2/) | Calculate the maximum profit from one purchase followed by one sale | Enumerate purchase dates and compare subsequent sale prices |
| [assignment_1-3](./assignment_1-3/) | Calculate the maximum stock-trading profit with a cooldown period | Dynamic programming with holding, sold, and eligible-to-buy states; accepts a user-defined cooldown |
| [assignment_2-1](./assignment_2-1/) | Determine whether one person can watch every movie in a given schedule in full | Sort by start time and check adjacent intervals for overlap |
| [assignment_2-2](./assignment_2-2/) | Calculate the minimum number of screening rooms needed to show all movies as scheduled | Sort intervals and determine when screening rooms can be reused |
| [assignment_2-3](./assignment_2-3/) | Merge overlapping movie screening intervals | Sort intervals, update endpoints, and merge overlapping intervals |
| [assignment_3-1](./assignment_3-1/) | Determine whether an integer array contains duplicate elements | Use standard-library sorting and compare adjacent elements |
| [assignment_3-2](./assignment_3-2/) | Determine whether two equal elements have an index distance of at most `k` | Maintain a window with a queue and check for duplicates within it using a hash set |
| [assignment_3-3](./assignment_3-3/) | Determine whether two elements satisfy both index-distance and value-difference constraints | Maintain a window with a queue and compare value differences within it |

Each assignment includes a separate entry-point program and a Visual Studio project. The table describes the existing source code; it does not imply that the implementation uses the optimal algorithm for each problem.

## Projects

### Gomoku AI

[fiveInARow](./fiveInARow/) includes board representation, pattern evaluation, candidate-move ordering, simulated moves, and Alpha-Beta pruning. The program communicates with an external game environment through text commands such as `START`, `PLACE`, `TURN`, and `END`; see the [source code](./fiveInARow/fiveInARow.cpp) for the input/output protocol.

The project provides a way to study heuristic evaluation and game-tree search through board states. Running it requires protocol-compliant input or a compatible game environment.

### Teamfight Tactics Auto-Battler

[Teamfight_Tactics](./Teamfight_Tactics/README.md) is a team course project built with Cocos2d-x 3.17.2. It includes practice mode, online matches, card and combat systems, AI players, and visual and audio assets.

The project documentation preserves team responsibilities, individual contribution records, and the development timeline. Yukun Yang coordinated testing and contributed to combat logic, champion modules, mode control, battle scenes, and champion artwork. See the [project README](./Teamfight_Tactics/README.md) for details.

## Build and Run

1. For each practice assignment, open the `.vcxproj` in its directory and build it with the Visual Studio 2022 C++ toolset. Assignments have separate `main()` functions and should run as independent programs.
2. The top-level `程序设计范式作业.sln` retains some historical directory names. If projects fail to load, open the existing project files directly or update the solution paths locally.
3. The Gomoku project file is `fiveInARow/Submit Version.vcxproj`. Send commands according to the protocol defined in the source code.
4. The auto-battler depends on Cocos2d-x and Windows Sockets (Winsock). Restore its environment using the [build instructions](./Teamfight_Tactics/README.md#build-and-run).

Some source files use GBK / GB18030-compatible encoding, and some exercises use Windows / MSVC interfaces such as `conio.h` and `_getch()`. Match the source encoding and platform environment when reading or building them.

## Reference Notes

This directory preserves implementations from the course for reviewing problems, comparing algorithms, and understanding program structure. Check input constraints, boundary conditions, and complexity against the original assignment requirements; retain contributor information when referring to team projects.

[Back to Repository Home](../README.md) · [License](./LICENSE)
