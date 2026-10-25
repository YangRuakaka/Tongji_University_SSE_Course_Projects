# Data Structures Course Projects and Discrete Mathematics Labs

**English** | [简体中文](./README.zh-CN.md)

This directory archives undergraduate data structures course projects and discrete mathematics labs, with **10 data structures projects** and **7 discrete mathematics program directories**. It includes C++ source code, accompanying DOCX documents, and Visual Studio projects. The implementations cover linked lists, trees, graphs, string matching, sorting, propositional logic, and operations on relations.

| Course module | Content | Directory |
| --- | --- | --- |
| Data structures course projects | Data organization, algorithm implementation, and console interaction for concrete applications | [Data Structures Projects](./数据结构程序设计/) |
| Discrete mathematics labs | Propositional logic, relation closures, minimum spanning trees, and optimal binary trees | [concrete math](./concrete%20math/) |

`concrete math` is the original directory name retained in the archive. The accompanying documents identify the course as Discrete Mathematics.

## Data Structures Course Projects

Each project is an independent program with a corresponding `.cpp` source file, `.vcxproj` project, and DOCX document.

| Project | Implementation | Main data structures and methods |
| --- | --- | --- |
| [Exam Registration System](./数据结构程序设计/考试系统/) | Enter, search, add, update, delete, and count candidate registration records | Singly linked list, record management, menu interaction |
| [Josephus Elimination Game](./数据结构程序设计/约瑟夫生死游戏/) | Simulate elimination and report the outcome using the number of participants, starting position, counting interval, and number of survivors | Circular linked list, survival flags, cyclic counting |
| [Maze](./数据结构程序设计/迷宫/) | Generate a maze, search for a route from entrance to exit, and display the path | Two-dimensional arrays, randomized direction selection, recursive search, backtracking |
| [Arithmetic Expressions](./数据结构程序设计/表达式/) | Build an expression tree, output infix, Polish, and reverse Polish notation, and evaluate the result | Custom stack, operator precedence, binary tree traversal |
| [Family Tree](./数据结构程序设计/家谱/) | Build and maintain family members and their hierarchy, with member lookup and relationship management | First-child/next-sibling representation, recursive tree search and modification |
| [Keyword Search](./数据结构程序设计/关键字检索/) | Read a specified text file and count occurrences of a keyword | Line-by-line file input, KMP string matching |
| [Power Grid](./数据结构程序设计/电网/) | Compute a minimum spanning tree and total construction cost from connection costs between nodes | Edge sorting, Kruskal's algorithm, disjoint-set union |
| [Sorting](./数据结构程序设计/排序/) | Run eight sorting algorithms on random data and record elapsed time, comparisons, and swap or movement counts | Bubble, selection, insertion, Shell, quick, heap, merge, and radix sort |
| [Binary Search Tree](./数据结构程序设计/二叉树/) | Build a binary search tree from input keys, with insertion, lookup, and traversal | Binary search tree, key comparisons, recursive operations |
| [N-Queens](./数据结构程序设计/N皇后/) | Enumerate queen placements that satisfy row, column, and diagonal constraints, then display the solutions and their count | Recursive backtracking, constraint checking |

The keyword search directory includes [`myfile.txt`](./数据结构程序设计/关键字检索/myfile.txt) as an example of file input. Each sorting algorithm records its own operation counts. When comparing results, check the source code to understand what is counted, and use consistent input sizes and data conditions.

## Discrete Mathematics Labs

| Lab directory | Implementation | Main methods |
| --- | --- | --- |
| [1-1](./concrete%20math/1-1/) | Compute conjunction, disjunction, implication, and equivalence from the truth values of propositions `P` and `Q` | Boolean operations and logical connective transformations |
| [1-2](./concrete%20math/1-2/) | Read a propositional formula and generate its truth table and canonical normal forms, with support for parentheses | Variable assignment enumeration, formula evaluation, canonical disjunctive and conjunctive normal forms |
| [2](./concrete%20math/2/) | Enumerate assignments that satisfy given logical conditions and output the values of selected variables | Exhaustive search, propositional reasoning |
| [3](./concrete%20math/3/) | Compute the reflexive, symmetric, or transitive closure of an input relation matrix | Relation matrices and closure operations |
| [4](./concrete%20math/4/) | Compute a minimum spanning tree from the edges and weights of an undirected graph | Adjacency matrix, Prim's algorithm |
| [5](./concrete%20math/5/) | Merge weighted nodes to construct an optimal binary tree and traverse it to output prefix codes | Huffman coding principles, binary tree construction and traversal |
| [Warshall](./concrete%20math/Warshall/) | Compute and output the transitive closure of a relation matrix | Warshall's algorithm, Boolean matrix updates |

Lab descriptions follow the actual behavior of the source files. The DOCX filename in `1-2` refers to “Propositional Reasoning,” while the source code implements truth tables and canonical normal forms. Check the document and implementation separately when reading this lab.

The optimal binary tree lab retains its original implementation: after reading the node count `n`, the program still uses the fixed constant `N = 13` to initialize nodes and construct the tree. Check the node count against the input data before reproducing this lab; the implementation cannot be used directly with an arbitrary number of nodes.

## Build and Run

### Development Environment

The existing projects use the **Visual Studio 2022 `v143` C++ toolset**, specify Windows SDK `10.0`, and include Win32 and x64 configurations. Some programs use `conio.h`, `_getch()`, `windows.h`, or MSVC-specific string functions. Windows is therefore the recommended environment for reproducing the original programs.

### Opening and Running a Project

1. Open the directory for an individual project or lab. Read its accompanying DOCX document before reviewing the source code.
2. Open the directory's `.vcxproj` file in Visual Studio, with the required C++ toolset and Windows SDK installed.
3. Select the desired platform and build configuration, then build and run each program separately. Each source file has its own entry point.
4. For programs that read files, check the working directory and input path. The keyword search program accepts the actual path to the example text file.

The two `.sln` files retain historical project paths. Their references to the exam registration project and discrete mathematics lab `1-1` no longer match the current directory structure. If a solution reports that a project cannot be loaded, open the corresponding existing project directly:

- Exam registration: [`数据结构程序设计.vcxproj`](./数据结构程序设计/考试系统/数据结构程序设计.vcxproj).
- Discrete mathematics `1-1`: [`concrete math.vcxproj`](./concrete%20math/1-1/concrete%20math.vcxproj).

### Source File Encoding

The source files retain their original Chinese encoding and can be read using a GB18030 / GBK-compatible encoding. If comments or console text appear garbled, first check the editor and compiler character set settings. Porting to macOS, Linux, or another compiler also requires addressing Windows APIs and MSVC extensions.

## Archive Notes

These programs document undergraduate approaches to the course problems. Read them alongside the assignment documents, trace data structure changes using small inputs, and then examine boundary cases and algorithmic complexity. Limitations in the historical implementations can also serve as material for later review.

This directory retains its original [MIT License](./LICENSE).

[Back to the repository overview](../README.md)
