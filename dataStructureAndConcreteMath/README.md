# 数据结构课程设计与离散数学实验 | Data Structures Course Projects and Discrete Mathematics Labs

[简体中文](#简体中文) | [English](#english)

## 简体中文

本目录整理本科阶段的数据结构课程设计与离散数学实验，收录 **10 个数据结构课题**和 **7 个离散数学程序目录**。归档内容包括 C++ 源码、配套 DOCX 文档和 Visual Studio 工程，记录了链表、树、图、字符串匹配、排序，以及命题逻辑和关系运算等知识的具体实现。

| 课程模块 | 内容 | 目录 |
| --- | --- | --- |
| 数据结构课程设计 | 面向具体应用的数据组织、算法实现与控制台交互 | [数据结构程序设计](./数据结构程序设计/) |
| 离散数学实验 | 命题逻辑、关系闭包、最小生成树与最优二元树 | [concrete math](./concrete%20math/) |

`concrete math` 为保留的历史目录名称；配套文档所属课程为《离散数学》。

### 数据结构课程设计

每个课题为独立程序，包含对应的 `.cpp` 源文件、`.vcxproj` 工程及 DOCX 文档。

| 课题 | 实现内容 | 主要数据结构与方法 |
| --- | --- | --- |
| [考试系统](./数据结构程序设计/考试系统/) | 录入、查询、增加、修改、删除和统计考生报名信息 | 单链表、记录维护、菜单交互 |
| [约瑟夫生死游戏](./数据结构程序设计/约瑟夫生死游戏/) | 根据人数、起始位置、报数间隔和保留人数，模拟淘汰过程并输出结果 | 循环链表、存活状态标记、循环计数 |
| [迷宫](./数据结构程序设计/迷宫/) | 生成迷宫、搜索入口至出口的通路并显示路径 | 二维数组、随机方向选择、递归搜索与回溯 |
| [表达式](./数据结构程序设计/表达式/) | 构建算术表达式树，输出中序表达式、波兰式和逆波兰式，并计算结果 | 自定义栈、运算符优先级、二叉树遍历 |
| [家谱](./数据结构程序设计/家谱/) | 建立和维护家庭成员及亲属层次，支持成员查找与关系管理 | 孩子—兄弟表示法、树的递归查找与修改 |
| [关键字检索](./数据结构程序设计/关键字检索/) | 读取指定文本文件，统计关键字出现次数 | 文件逐行读取、KMP 字符串匹配 |
| [电网](./数据结构程序设计/电网/) | 根据节点间的线路费用计算最小生成树及总造价 | 边排序、Kruskal 算法、并查集 |
| [排序](./数据结构程序设计/排序/) | 对随机数据运行八种排序算法，记录耗时、比较次数和交换或移动计数 | 冒泡、选择、直接插入、希尔、快速、堆、归并和基数排序 |
| [二叉树](./数据结构程序设计/二叉树/) | 根据输入关键字建立二叉排序树，进行插入、查找和遍历 | 二叉搜索树、节点比较与递归操作 |
| [N 皇后](./数据结构程序设计/N皇后/) | 枚举满足行、列和对角线约束的皇后摆放方案，并输出方案及数量 | 递归回溯、约束检查 |

关键字检索目录附有 [`myfile.txt`](./数据结构程序设计/关键字检索/myfile.txt)，可用于了解文件输入方式。排序程序中的操作计数由各算法分别记录；比较结果时，应结合源码确认计数含义，并保持输入规模和数据条件一致。

### 离散数学实验

| 实验目录 | 实现内容 | 主要方法 |
| --- | --- | --- |
| [1-1](./concrete%20math/1-1/) | 根据命题 `P`、`Q` 的真值，计算合取、析取、蕴含和等值 | 布尔运算及逻辑联接词转换 |
| [1-2](./concrete%20math/1-2/) | 读取命题公式，生成真值表及主范式，支持括号 | 变量枚举、公式求值、主析取范式与主合取范式 |
| [2](./concrete%20math/2/) | 枚举满足给定逻辑条件的变量赋值，并输出指定变量的取值 | 穷举法、命题逻辑推理 |
| [3](./concrete%20math/3/) | 根据输入的关系矩阵计算自反、对称或传递闭包 | 关系矩阵及闭包运算 |
| [4](./concrete%20math/4/) | 根据无向图的边和权值计算最小生成树 | 邻接矩阵、Prim 算法 |
| [5](./concrete%20math/5/) | 合并带权节点构造最优二元树，并遍历输出前缀编码 | Huffman 编码思想、二叉树构造与遍历 |
| [Warshall](./concrete%20math/Warshall/) | 计算并输出关系矩阵的传递闭包 | Warshall 算法、布尔矩阵更新 |

实验名称按源码实际功能整理。`1-2` 目录所附 DOCX 文件名为“命题逻辑推理”，与该目录源码中的真值表和主范式功能存在差异，阅读时请分别核对。

最优二元树实验保留了当时的实现：程序读取节点数 `n` 后，仍使用固定常量 `N = 13` 初始化和构造树。复现该实验前需核对节点数与输入数据，不能直接按任意节点规模使用。

### 工程组织与运行

#### 开发环境

现有工程使用 **Visual Studio 2022 的 `v143` C++ 工具集**，Windows SDK 配置为 `10.0`，包含 Win32 与 x64 配置。部分程序使用 `conio.h`、`_getch()`、`windows.h` 或 MSVC 提供的字符串函数，建议优先在 Windows 环境中复现。

#### 打开与运行

1. 进入具体课题或实验目录，先阅读配套 DOCX 文档，再查看对应源码。
2. 使用 Visual Studio 打开该目录内的 `.vcxproj`，安装所需的 C++ 工具集与 Windows SDK。
3. 选择所需的平台和构建配置，分别编译、运行各个程序；每个源文件均有独立入口。
4. 文件读取类程序需确认工作目录和输入路径。关键字检索程序可输入示例文件的实际路径。

两个 `.sln` 文件保留了历史项目路径，其中考试系统和离散数学 `1-1` 的引用已与当前目录结构不一致。若解决方案提示项目无法加载，可直接打开以下实际存在的工程：

- 考试系统：[`数据结构程序设计.vcxproj`](./数据结构程序设计/考试系统/数据结构程序设计.vcxproj)。
- 离散数学 `1-1`：[`concrete math.vcxproj`](./concrete%20math/1-1/concrete%20math.vcxproj)。

#### 源文件编码

源码保留了原始中文编码，可按 GB18030 / GBK 兼容编码读取。若注释或控制台文本出现乱码，应先检查编辑器和编译器的字符集设置。迁移至 macOS、Linux 或其他编译器时，还需处理 Windows 接口与 MSVC 扩展的差异。

### 归档说明

这些程序反映了本科阶段对课程问题的理解与实现。阅读时可结合题目文档，使用小规模输入跟踪数据结构变化，再检查边界情况和算法复杂度；历史代码中的实现限制也可作为后续复盘的材料。

本目录保留原有 [MIT 许可证](./LICENSE)。

[返回仓库首页](../README.md#简体中文)

## English

This directory archives undergraduate data structures course projects and discrete mathematics labs, with **10 data structures projects** and **7 discrete mathematics program directories**. It includes C++ source code, accompanying DOCX documents, and Visual Studio projects. The implementations cover linked lists, trees, graphs, string matching, sorting, propositional logic, and operations on relations.

| Course module | Content | Directory |
| --- | --- | --- |
| Data structures course projects | Data organization, algorithm implementation, and console interaction for concrete applications | [Data Structures Projects](./数据结构程序设计/) |
| Discrete mathematics labs | Propositional logic, relation closures, minimum spanning trees, and optimal binary trees | [concrete math](./concrete%20math/) |

`concrete math` is the original directory name retained in the archive. The accompanying documents identify the course as Discrete Mathematics.

### Data Structures Course Projects

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

### Discrete Mathematics Labs

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

### Build and Run

#### Development Environment

The existing projects use the **Visual Studio 2022 `v143` C++ toolset**, specify Windows SDK `10.0`, and include Win32 and x64 configurations. Some programs use `conio.h`, `_getch()`, `windows.h`, or MSVC-specific string functions. Windows is therefore the recommended environment for reproducing the original programs.

#### Opening and Running a Project

1. Open the directory for an individual project or lab. Read its accompanying DOCX document before reviewing the source code.
2. Open the directory's `.vcxproj` file in Visual Studio, with the required C++ toolset and Windows SDK installed.
3. Select the desired platform and build configuration, then build and run each program separately. Each source file has its own entry point.
4. For programs that read files, check the working directory and input path. The keyword search program accepts the actual path to the example text file.

The two `.sln` files retain historical project paths. Their references to the exam registration project and discrete mathematics lab `1-1` no longer match the current directory structure. If a solution reports that a project cannot be loaded, open the corresponding existing project directly:

- Exam registration: [`数据结构程序设计.vcxproj`](./数据结构程序设计/考试系统/数据结构程序设计.vcxproj).
- Discrete mathematics `1-1`: [`concrete math.vcxproj`](./concrete%20math/1-1/concrete%20math.vcxproj).

#### Source File Encoding

The source files retain their original Chinese encoding and can be read using a GB18030 / GBK-compatible encoding. If comments or console text appear garbled, first check the editor and compiler character set settings. Porting to macOS, Linux, or another compiler also requires addressing Windows APIs and MSVC extensions.

### Archive Notes

These programs document undergraduate approaches to the course problems. Read them alongside the assignment documents, trace data structure changes using small inputs, and then examine boundary cases and algorithmic complexity. Limitations in the historical implementations can also serve as material for later review.

This directory retains its original [MIT License](./LICENSE).

[Back to the repository overview](../README.md#english)
