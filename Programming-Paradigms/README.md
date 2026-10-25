# 程序设计范式课程作业与项目 | Programming Paradigms Coursework and Projects

[简体中文](#简体中文) | [English](#english)

## 简体中文

本目录收录同济大学软件学院《程序设计范式》课程的个人作业与团队项目，主要使用 C++。内容从数组与区间处理等独立练习，延伸到五子棋搜索算法和基于 Cocos2d-x 的自走棋游戏，记录本科阶段对问题建模、程序组织与团队开发的实践。

### 基础作业

| 作业 | 题目内容 | 当前实现的主要方法 |
| --- | --- | --- |
| [assignment_1-1](./assignment_1-1/) | 为每日股票价格计算下一次价格上涨所需的等待天数 | 数组与指针遍历，逐项查找后续更高价格 |
| [assignment_1-2](./assignment_1-2/) | 计算一次买入、一次卖出可获得的最大收益 | 枚举买入日期，比较后续卖出价格 |
| [assignment_1-3](./assignment_1-3/) | 计算包含交易冷却期的股票最大收益 | 动态规划，区分持有、卖出与可购买状态；支持输入冷却期 |
| [assignment_2-1](./assignment_2-1/) | 判断一个人能否完整观看给定安排中的全部电影 | 按开始时间排序，检查相邻时间区间是否重叠 |
| [assignment_2-2](./assignment_2-2/) | 计算按计划播放全部电影所需的最少放映厅数 | 区间排序与放映厅复用判断 |
| [assignment_2-3](./assignment_2-3/) | 合并相互重叠的电影播放时间区间 | 区间排序、端点更新与重叠区间合并 |
| [assignment_3-1](./assignment_3-1/) | 判断整数数组中是否存在重复元素 | 标准库排序与相邻元素比较 |
| [assignment_3-2](./assignment_3-2/) | 判断是否存在数值相等且下标距离不超过 `k` 的两个元素 | 队列维护窗口，在窗口内使用哈希集合检查重复 |
| [assignment_3-3](./assignment_3-3/) | 判断两个元素是否同时满足下标距离与数值差约束 | 队列维护窗口，在窗口内比较元素差值 |

各作业均包含独立入口程序及 Visual Studio 工程。表中按现有源码描述实现，不表示已经采用对应问题的最优算法。

### 综合项目

#### 五子棋 AI

[fiveInARow](./fiveInARow/) 包含棋盘表示、棋型评估、候选落点排序、模拟落子与 Alpha-Beta 剪枝搜索。程序通过 `START`、`PLACE`、`TURN`、`END` 等文本指令与外部对弈环境交互；输入输出协议见 [源码](./fiveInARow/fiveInARow.cpp)。

该项目适合结合棋局状态理解启发式评估与博弈搜索。运行时需提供符合协议的输入或配套对弈环境。

#### Teamfight Tactics 自走棋

[Teamfight_Tactics](./Teamfight_Tactics/) 是基于 Cocos2d-x 3.17.2 的团队课程项目，包含练习模式、联机对战、卡牌与战斗系统、AI 玩家及图像音频资源。

项目文档保留了团队分工、个人贡献记录和开发时间线。其中，杨宇琨负责项目测试统筹，并参与战斗逻辑、英雄模块、模式控制、对战场景与战斗英雄绘制。完整介绍见 [项目 README](./Teamfight_Tactics/README.md#简体中文)。

### 构建与运行

1. 基础作业可分别打开对应目录中的 `.vcxproj`，使用 Visual Studio 2022 的 C++ 工具集构建。多个作业具有各自的 `main()`，应作为独立程序运行。
2. 顶层 `程序设计范式作业.sln` 保留了部分历史目录名；若出现项目加载失败，可直接打开实际存在的项目文件，或在本地更新解决方案路径。
3. 五子棋项目的工程文件为 `fiveInARow/Submit Version.vcxproj`，运行时按源码协议发送指令。
4. 自走棋项目依赖 Cocos2d-x 引擎和 Windows Socket，需按其 [构建说明](./Teamfight_Tactics/README.md#构建与运行) 恢复环境。

部分源文件使用 GBK / GB18030 兼容编码，部分练习使用 `conio.h`、`_getch()` 等 Windows / MSVC 接口。阅读和构建时需匹配源码编码及平台环境。

### 参考说明

本目录保留课程学习时的实现，适合用于回顾题目、比较算法与理解程序结构。参考时请结合当年的题目要求检查输入约束、边界条件和复杂度；引用团队项目时保留贡献者信息。

[返回仓库首页](../README.md#简体中文) · [许可证](./LICENSE)

## English

This directory contains individual assignments and team projects from the Programming Paradigms course at Tongji University's School of Software Engineering, primarily written in C++. The collection ranges from standalone array and interval exercises to Gomoku search algorithms and a Cocos2d-x auto-battler, documenting undergraduate practice in problem modeling, program organization, and team development.

### Practice Assignments

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

### Projects

#### Gomoku AI

[fiveInARow](./fiveInARow/) includes board representation, pattern evaluation, candidate-move ordering, simulated moves, and Alpha-Beta pruning. The program communicates with an external game environment through text commands such as `START`, `PLACE`, `TURN`, and `END`; see the [source code](./fiveInARow/fiveInARow.cpp) for the input/output protocol.

The project provides a way to study heuristic evaluation and game-tree search through board states. Running it requires protocol-compliant input or a compatible game environment.

#### Teamfight Tactics Auto-Battler

[Teamfight_Tactics](./Teamfight_Tactics/README.md#english) is a team course project built with Cocos2d-x 3.17.2. It includes practice mode, online matches, card and combat systems, AI players, and visual and audio assets.

The project documentation preserves team responsibilities, individual contribution records, and the development timeline. Yukun Yang coordinated testing and contributed to combat logic, champion modules, mode control, battle scenes, and champion artwork. See the [project README](./Teamfight_Tactics/README.md#english) for details.

### Build and Run

1. For each practice assignment, open the `.vcxproj` in its directory and build it with the Visual Studio 2022 C++ toolset. Assignments have separate `main()` functions and should run as independent programs.
2. The top-level `程序设计范式作业.sln` retains some historical directory names. If projects fail to load, open the existing project files directly or update the solution paths locally.
3. The Gomoku project file is `fiveInARow/Submit Version.vcxproj`. Send commands according to the protocol defined in the source code.
4. The auto-battler depends on Cocos2d-x and Windows Sockets (Winsock). Restore its environment using the [build instructions](./Teamfight_Tactics/README.md#build-and-run).

Some source files use GBK / GB18030-compatible encoding, and some exercises use Windows / MSVC interfaces such as `conio.h` and `_getch()`. Match the source encoding and platform environment when reading or building them.

### Reference Notes

This directory preserves implementations from the course for reviewing problems, comparing algorithms, and understanding program structure. Check input constraints, boundary conditions, and complexity against the original assignment requirements; retain contributor information when referring to team projects.

[Back to Repository Home](../README.md#english) · [License](./LICENSE)
