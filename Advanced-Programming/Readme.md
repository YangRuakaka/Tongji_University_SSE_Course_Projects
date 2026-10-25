# 高级程序语言设计

本目录归档了我在同济大学本科阶段学习高级程序语言设计时完成的部分 C / C++ 作业，以及对应的题目、编程规范和实验资料。内容涵盖基础语法、程序控制结构、函数与递归、数组与字符串、指针、结构体及类，并包含消灭星星与汉诺塔综合演示的相关文件。

这些文件保留了课程学习期间的实现与组织方式，可用于回顾解题思路、输入处理和多文件程序设计。

## 目录导航

| 目录 | 收录内容 |
| --- | --- |
| [weeklyAssignment](./weeklyAssignment/) | 第 3～7 章作业源码、部分章节题目 PDF、输入处理示例和补充练习。 |
| [pptAssignment](./pptAssignment/) | 顺序结构、选择结构、循环结构、输入错误处理、字符串长度及表达式求值等专题题目。 |
| [assignmentCodeStyle](./assignmentCodeStyle/) | 课程源程序格式、编译要求和作业提交规范。 |
| [Tutorial](./Tutorial/) | Visual Studio 2022 警告处理、输入输出重定向及管道运算符说明。 |
| [Popstar](./Popstar/) | 消灭星星综合作业的题目、游戏逻辑与 Windows 控制台交互代码。 |
| [Hanoi](./Hanoi/) | 汉诺塔综合演示的题目、程序入口、菜单、函数声明和控制台工具。 |

## 章节作业

| 目录 | 主要内容 |
| --- | --- |
| [chapter3](./weeklyAssignment/chapter3/) | 输入输出、数值计算、分支与循环、格式化输出和输入合法性检查；部分题目包含 C 与 C++ 两种实现。 |
| [chapter4](./weeklyAssignment/chapter4/) | 函数分解、递归与多文件程序组织。 |
| [chapter5](./weeklyAssignment/chapter5/) | 数组、字符数组、字符串处理与 `string` 类。 |
| [chapter6](./weeklyAssignment/chapter6/) | 指针、字符遍历及相关函数练习。 |
| [chapter7](./weeklyAssignment/chapter7/) | 结构体、结构体嵌套、函数重载、类与对象。 |
| [InputSolution](./weeklyAssignment/InputSolution/) | C 和 C++ 输入失败后的状态恢复与重新输入。 |
| [additionalWorks](./weeklyAssignment/additionalWorks/) | 按原作业编号保留的补充练习与实验课代码。 |

章节目录保留原有题号与文件名；部分题目将入口、函数实现和头文件分开存放。阅读时可先查看题目要求，再对照对应编号的源码。

## 综合作业

### 消灭星星（Popstar）

项目以二维数组表示棋盘，围绕相邻同色块识别、消除、下落与棋盘整理组织游戏逻辑，并通过 Windows 控制台提供文本和鼠标交互。

- `popstar-main.cpp`：程序入口与功能菜单。
- `popstar-base.cpp`、`popstar-tools.cpp`：基础操作与游戏处理函数。
- `popstar-console.cpp`：控制台界面及交互相关实现。
- `popstar.h`、`cmd_console_tools.*`：函数声明与控制台工具。

菜单包含可消除项标识、单次消除、完整关卡和控制台伪图形界面等模式，可用于观察游戏逻辑与交互代码的分工。

### 汉诺塔（Hanoi）

本目录保留了综合演示作业的部分材料。`hanoi_main.cpp` 负责程序入口，`hanoi_menu.cpp` 提供菜单，`hanoi.h` 声明相关函数，`cmd_console_tools.*` 提供控制台操作支持。

当前归档中的 `hanoi_multiple_solutions.cpp` 仅包含模板注释，尚未提供菜单项对应的执行函数，因此现有文件不足以构建完整的汉诺塔演示程序。菜单内容可结合题目 PDF 了解原作业要求。

## 编译与运行

本目录以 Windows / Visual Studio 下的课程开发环境为主要背景，未收录统一的工程文件或构建脚本。不同题目是独立程序，需要分别组织和编译。

1. 单文件作业：为所选 `.c` 或 `.cpp` 建立独立的控制台项目。
2. 多文件作业：将同一题目的入口文件、实现文件和头文件加入同一项目。
3. 消灭星星：将 `popstar-main.cpp`、`popstar-base.cpp`、`popstar-console.cpp`、`popstar-tools.cpp` 和 `cmd_console_tools.cpp` 一同编译，并保留对应头文件。

多个练习各自包含 `main()`，应避免将不同题目的入口放入同一可执行项目。部分源码使用 `windows.h`、`conio.h`、`_getch()` 或 MSVC 相关接口，运行时需要相应的 Windows 开发环境。中文注释与字符串出现乱码时，可尝试按 GBK / GB18030 兼容编码打开源文件，并核对编译器的字符集设置。

## 参考说明

源码反映了我在入门阶段的学习过程，题目要求、实现方式和完成程度以各文件为准。参考时建议结合原题独立分析，并使用正常输入与边界输入验证结果；不同学年的作业安排应以当年的课程要求为准。

[返回仓库首页](../README.md)
