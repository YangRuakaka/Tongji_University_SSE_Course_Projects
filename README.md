# 同济大学软件学院本科课程作业与项目

本仓库整理了我在同济大学软件学院本科阶段完成的部分课程作业、实验与课程项目，保留了当时的题目资料、源代码、工程文件及实验文档。内容以 **C / C++** 为主，涵盖高级程序语言设计、程序设计范式、数据结构与离散数学。

这些材料记录了从基础编程练习到数据结构应用、算法实现及团队项目开发的学习过程。仓库按历史课程与作业目录组织，各题目通常为独立程序。

## 课程与项目导航

| 课程 | 收录内容 | 详细说明 |
| --- | --- | --- |
| 高级程序语言设计 | 章节作业、补充练习、输入处理示例、汉诺塔与消灭星星综合作业，以及题目和代码规范资料 | [Advanced-Programming](./Advanced-Programming/Readme.md) |
| 程序设计范式 | 9 项基础作业、五子棋 AI 与自走棋团队项目 | [Programming-Paradigms](./Programming-Paradigms/README.md) |
| 数据结构课程设计 | 考试系统、约瑟夫问题、迷宫、表达式树、家谱、字符串检索、电网、排序、二叉排序树与 N 皇后等 10 个课题 | [数据结构课程设计](./dataStructureAndConcreteMath/README.md#数据结构课程设计) |
| 离散数学 | 命题逻辑、真值表与主范式、关系闭包、最小生成树和最优二元树等 7 个实验目录 | [离散数学实验](./dataStructureAndConcreteMath/README.md#离散数学实验) |

## 仓库结构

```text
Tongji_University_SSE_Course_Projects/
├── Advanced-Programming/
│   ├── weeklyAssignment/           # 章节作业、补充练习与输入处理
│   ├── pptAssignment/              # 课堂专题题目
│   ├── assignmentCodeStyle/        # 代码格式与编译要求
│   ├── Tutorial/                   # 开发环境与输入输出说明
│   ├── Hanoi/                      # 汉诺塔综合演示资料与程序框架
│   └── Popstar/                    # 消灭星星控制台游戏
├── Programming-Paradigms/
│   ├── assignment_1-1/ … 1-3/     # 股票价格与交易问题
│   ├── assignment_2-1/ … 2-3/     # 时间区间与调度问题
│   ├── assignment_3-1/ … 3-3/     # 重复元素与距离约束问题
│   ├── fiveInARow/                 # 五子棋 AI
│   └── Teamfight_Tactics/          # 自走棋团队项目
└── dataStructureAndConcreteMath/
    ├── 数据结构程序设计/            # 10 个独立课程设计课题
    └── concrete math/              # 离散数学实验
```

`concrete math` 为历史目录名，其内容按配套课程资料归入离散数学。

## 代表性项目

| 项目 | 内容与实现重点 |
| --- | --- |
| [消灭星星](./Advanced-Programming/Popstar/) | 控制台游戏，将主程序、基础逻辑、工具函数与界面交互拆分为多个源文件。 |
| [五子棋 AI](./Programming-Paradigms/fiveInARow/) | 棋盘状态表示、棋型评估、模拟落子与 Alpha-Beta 搜索，通过文本指令与外部程序交互。 |
| [Teamfight Tactics](./Programming-Paradigms/Teamfight_Tactics/README.md) | 基于 Cocos2d-x 3.17.2 的自走棋团队项目，涉及战斗逻辑、玩家与 AI、场景交互及客户端与服务端通信；成员分工和贡献记录见项目文档。 |
| [数据结构课程设计](./dataStructureAndConcreteMath/数据结构程序设计/) | 将链表、栈、树、图、字符串匹配和排序应用于独立课题，附源码、Visual Studio 工程与 DOCX 文档。 |

## 开发环境与运行

已有 Visual Studio C++ 工程使用 `v143` 工具集；建议在 Windows 上使用 Visual Studio 2022，并安装相应的 C++ 工具与 Windows SDK。具体配置以各项目的 `.vcxproj` 为准。

1. 根据课程文档选择具体题目，先阅读题目或实验资料，再查看实现。
2. 对有工程文件的作业，优先打开对应的 `.vcxproj`；部分 `.sln` 仍保留旧目录路径，需要重新关联项目。
3. 单文件作业可单独创建 C 或 C++ 项目；多文件作业应加入所需实现文件。多个独立题目的 `main()` 不应合并到同一可执行程序中。
4. 中文源码多采用 GBK / GB18030 兼容编码，出现乱码时应先检查文件编码。涉及 Windows 控制台、Windows Socket 或 MSVC 扩展的程序，需要对应平台环境。

汉诺塔目录保留的是未完成的程序框架；自走棋项目未附 Cocos2d-x 引擎目录，构建前需要补齐依赖。各课程文档提供了更具体的归档状态与使用说明。

## 资料使用与贡献说明

本仓库保留本科阶段的历史实现，便于回顾题目、交流思路与对照学习；课程要求和开发环境可能随年份变化。参考时请结合原题与具体输入验证程序行为。

团队项目保留原有贡献者及分工记录。仓库部分目录附有 `LICENSE`，使用或分发相关内容时请查看对应目录的许可文件，并保留作者署名与版权声明。
