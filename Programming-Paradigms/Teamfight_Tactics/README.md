# Teamfight Tactics 自走棋课程项目 | Teamfight Tactics Auto-Battler Course Project

[简体中文](#简体中文) | [English](#english)

## 简体中文

Teamfight_Tactics 是同济大学《程序设计范式》课程的团队项目，使用 C++ 与 Cocos2d-x 3.17.2 实现。项目参考《Dota 自走棋》《云顶之弈》和《金铲铲之战》的玩法，围绕卡牌购买、阵容组织、自动战斗和多人通信开展综合开发实践。

本目录归档客户端源码、服务端源码、游戏资源与 Visual Studio 工程。原团队仓库为 [MinmusLin/Teamfight_Tactics](https://github.com/MinmusLin/Teamfight_Tactics)。

### 功能概览

| 模块 | 项目内容 |
| --- | --- |
| 场景与交互 | 初始界面、菜单与设置、玩家昵称、小小英雄移动、场景切换与按钮交互 |
| 卡牌与阵容 | 多种英雄卡牌、商店购买、卡牌升级、布阵与英雄属性展示 |
| 战斗系统 | 自动战斗、生命值与法力值显示、技能释放、武器动画与战斗音效 |
| 成长与策略 | 金币与经验、羁绊加成、强化符文、商店推荐与 AI 布阵 |
| 练习模式 | 人类玩家与多个 AI 玩家对战 |
| 联机模式 | 独立服务端、客户端连接与房间交互、玩家信息与战场数据交换 |
| 视听资源 | 场景、按钮、英雄与小小英雄图像，背景音乐及交互音效 |

以上为课程开发记录与源码中的功能范围；当前归档的完整运行需要先恢复引擎依赖。

### 代码结构

```text
Teamfight_Tactics/
├── Classes/                 # 客户端游戏逻辑
│   ├── AppDelegate/         # 应用初始化与生命周期
│   ├── Battle/              # 战斗逻辑
│   ├── Button/              # 按钮交互
│   ├── Champion/            # 英雄与卡牌
│   ├── Control/             # 模式控制与网络客户端
│   ├── Layer/               # 属性、布阵标记与计分界面
│   ├── LocationMap/         # 棋盘位置映射
│   ├── Player/              # 人类与 AI 玩家
│   └── Scene/               # 菜单、准备、战斗与符文场景
├── Resources/               # 图像、音频与字体
├── Server/                  # Windows Socket 服务端
├── proj.win32/              # Windows 客户端工程、入口与公共配置
└── LICENSE
```

客户端按场景、模式控制、玩家、英雄和战斗等职责拆分。`Control` 与 `Player` 的派生类分别承载不同游戏模式和玩家行为；服务端负责连接管理及对局信息交换。

### 团队分工

| 成员 | 学号 | 主要职责与参与模块 |
| --- | --- | --- |
| 林继申（组长） | 2250758 | 后端工作统筹、任务分配与代码审查；项目框架及网络环境；练习与联机模式；`AppDelegate`、`Battle`、`HoverButton`、`Champion`、`Control` 及派生类、`ChampionAttributesLayer`、`PlacementMarkerLayer`、`ScoreBoardLayer`、`LocationMap`、`Player` 及派生类、`Scene` 及派生类、`Server` |
| 刘淑仪 | 2251730 | 前端工作统筹；练习与联机模式；`Champion`、`ChampionAttributesLayer`、`PlacementMarkerLayer`、`ScoreBoardLayer`、`Scene` 及派生类；图标、按钮、战斗英雄、小小英雄、图像元素与场景绘制；音频引擎、背景音乐及音效 |
| 杨兆镇 | 2252712 | AI 玩家算法统筹；练习模式；`Player` 与派生类 `AIPlayer` |
| 杨宇琨 | 2252843 | 测试工作统筹；练习与联机模式；`Battle`、`Champion`、`OfflineModeControl`、`HumanPlayer`、`OfflineModeBattleScene`、`OnlineModeBattleScene`；战斗英雄绘制 |

#### 课程归档贡献记录

| 成员 | 学号 | 原文档记录的代码行数 | 原文档记录的工作量占比 |
| --- | --- | ---: | ---: |
| 林继申（组长） | 2250758 | 4710 | 35% |
| 刘淑仪 | 2251730 | 1385 | 25% |
| 杨兆镇 | 2252712 | 467 | 15% |
| 杨宇琨 | 2252843 | 2282 | 25% |

上述数值保留自课程项目原始文档，未按当前归档仓库重新统计。代码行数与工作量占比采用不同口径，图像绘制、测试、设计和协作等工作也属于团队贡献。

### 构建与运行

#### 环境与依赖

| 项目 | 要求或归档状态 |
| --- | --- |
| 操作系统 | Windows；客户端和服务端使用 Windows Socket |
| 开发环境 | 原项目使用 Microsoft Visual Studio 2022；现有工程指定 `v143` 工具集 |
| 游戏引擎 | Cocos2d-x 3.17.2，包含工程引用的引擎代码、属性文件及第三方库 |
| 客户端平台 | 工程提供 Debug / Release 的 Win32（x86）配置 |
| 服务端平台 | 工程包含 Win32 和 x64 配置；客户端整体方案按 Win32 配置恢复 |
| 资源 | 保留 `Resources/` 及其相对路径，供场景、字体和音频加载使用 |

`cocos2d/` 被原项目的 `.gitignore` 排除，当前目录未包含该引擎。客户端工程与解决方案仍引用 `../cocos2d/` 下的属性文件、`libcocos2d`、Spine 和 Recast 工程，因此直接打开解决方案可能出现依赖加载失败。

#### 恢复与启动流程

1. 准备 Cocos2d-x 3.17.2 及其 Windows 构建依赖，将引擎目录恢复到本目录的 `cocos2d/`，或在本地调整工程中的引用路径。
2. 使用 Visual Studio 2022 打开 [客户端解决方案](./proj.win32/Teamfight_Tactic.sln)，确认 C++ 工具集和引擎依赖均可加载，选择 Win32 配置进行构建。服务端也可通过 [Server.vcxproj](./Server/Server.vcxproj) 单独打开。
3. 检查资源工作目录。现有 `.vcxproj.user` 将客户端调试工作目录设为 `Resources/`，源码使用相对路径加载图像、字体和音频；独立运行时需保持相应目录关系。
4. 练习模式使用本地 AI 玩家。联机模式需先启动服务端，再在客户端输入服务端显示的 IPv4 地址和端口，完成连接后进入对局。

上述流程依据现有工程与源码整理，完整构建与联机运行仍需在 Windows 环境中验证。

### 开发记录

以下时间线整理自课程项目原始日志，保留当时的环境选择与迭代过程。

| 日期 | 开发内容 |
| --- | --- |
| 2023-11-22 | 配置 Python 2.7.10、CMake 3.28.0 与 Cocos2d-x 4.0 环境 |
| 2023-11-23 | 明确代码规范，学习 Markdown 文档编写 |
| 2023-11-24 | 学习 Cocos2d-x |
| 2023-11-29 | 在 GitHub 托管项目仓库 |
| 2023-12-03 | 学习 Git 与 GitHub Desktop，明确提交规范；从 Cocos2d-x 4.0 切换至 3.17.2，并编译测试项目 |
| 2023-12-04 | 明确仓库组成，配置 Boost 网络环境 |
| 2023-12-08 | 初步确定团队分工 |
| 2023-12-09 | 从 Boost 切换至 Socket；初步搭建项目框架，实现 `AppDelegate` |
| 2023-12-10 | 初步搭建 Socket 网络环境 |
| 2023-12-11 | 基本完成网络环境，初步实现 `Server` |
| 2023-12-12 | 基本确定分工与框架，实现 `HoverButton` 和 `GBKToUTF8` 单例 |
| 2023-12-16 | 绘制项目图标 |
| 2023-12-17 | 初步实现商店功能 |
| 2023-12-18 | 完善初始场景背景与交互细节，实现 `Champion` 鼠标事件监听 |
| 2023-12-19 | 完善框架；初步实现 `Champion`、`OfflineModeControl`、`Player` 与 `HumanPlayer`；实现 `InitialScene` 交互及 `LocationMap` 单例 |
| 2023-12-20 | 调整资源目录、`GBKToUTF8` 与 `LocationMap`；实现启动和菜单场景；初步实现练习模式准备场景与 `Battle`；确定英雄属性，完成战斗英雄绘制 |
| 2023-12-22 | 初步实现 `ChampionAttributesLayer` |
| 2023-12-23 | 实现英雄属性层与布阵标记层，绘制商店按钮；基本实现 `HumanPlayer` 和练习模式准备场景 |
| 2023-12-24 | 实现金币系统，调整命名空间，完善练习模式准备场景 |
| 2023-12-25 | 实现战斗、英雄、练习模式战斗场景、练习模式控制和计分层；整合团队工作，基本完成练习模式 |
| 2023-12-26 | 实现 `Control`、生命条与经验条效果、武器动画 |
| 2023-12-27 | 调整功能与平衡性；实现商店推荐和 AI 落子算法；完善玩家类及派生类，整合并完成练习模式 |
| 2023-12-28 | 完善商店推荐与 AI 落子算法，基本实现联机菜单场景 |
| 2023-12-29 | 初步实现联机控制、准备场景、战斗场景与联机模式；实现选择和设置场景、小小英雄移动及羁绊系统 |
| 2023-12-30 | 基本完成联机控制与场景，实现练习模式符文场景、音频引擎和天赋符文系统 |
| 2023-12-31 | 调整资源目录；完成联机控制、相关场景、参考场景和服务端；进行功能与平衡性测试，完成项目收尾 |

原开发日志截止日期：2023 年 12 月 31 日。早期环境尝试保留在时间线中，恢复项目时以当前工程及最终采用的 Cocos2d-x 3.17.2 为依据。

### 归档与引用

本项目用于记录本科课程中的团队开发实践。引用源码或介绍项目时，请保留原作者及团队分工信息，并参阅 [LICENSE](./LICENSE)。

[返回课程目录](../README.md#简体中文) · [返回仓库首页](../../README.md#简体中文)

## English

Teamfight_Tactics is an auto-battler developed as a team project for Tongji University's Programming Paradigms course, implemented in C++ with Cocos2d-x 3.17.2. Drawing on the gameplay of Dota Auto Chess, Teamfight Tactics, and Battle of Golden Spatula (《金铲铲之战》), the project combines card purchasing, team composition, automated combat, and multiplayer communication.

This directory archives the client and server source code, game assets, and Visual Studio projects. The original team repository is [MinmusLin/Teamfight_Tactics](https://github.com/MinmusLin/Teamfight_Tactics).

### Feature Overview

| Module | Project contents |
| --- | --- |
| Scenes and interaction | Initial screen, menus and settings, player nicknames, Little Legend movement, scene transitions, and button interaction |
| Cards and team composition | Multiple champion cards, shop purchases, card upgrades, unit placement, and champion attribute displays |
| Combat system | Automated combat, health and mana displays, ability activation, weapon animations, and combat sound effects |
| Progression and strategy | Gold and experience, synergy bonuses, augments, shop recommendations, and AI unit placement |
| Practice mode | A human player competes against multiple AI players |
| Online mode | Standalone server, client connections and room interaction, and exchange of player information and battlefield data |
| Visual and audio assets | Scene, button, champion, and Little Legend images, background music, and interaction sound effects |

These features reflect the course development records and source code. Running the complete archived project requires restoring the engine dependencies first.

### Code Structure

```text
Teamfight_Tactics/
├── Classes/                 # Client game logic
│   ├── AppDelegate/         # Application initialization and lifecycle
│   ├── Battle/              # Combat logic
│   ├── Button/              # Button interaction
│   ├── Champion/            # Champions and cards
│   ├── Control/             # Mode control and network client
│   ├── Layer/               # Attributes, placement markers, and scoreboard UI
│   ├── LocationMap/         # Board position mapping
│   ├── Player/              # Human and AI players
│   └── Scene/               # Menu, preparation, battle, and augment scenes
├── Resources/               # Images, audio, and fonts
├── Server/                  # Windows Sockets (Winsock) server
├── proj.win32/              # Windows client project, entry point, and shared configuration
└── LICENSE
```

The client separates responsibilities for scenes, mode control, players, champions, and combat. Derived classes of `Control` and `Player` implement the different game modes and player behaviors; the server manages connections and exchanges match information.

### Team Responsibilities

| Member | Student ID | Main responsibilities and modules |
| --- | --- | --- |
| Jishen Lin (team lead) | 2250758 | Backend coordination, task assignment, and code review; project framework and network environment; practice and online modes; `AppDelegate`, `Battle`, `HoverButton`, `Champion`, `Control` and its derived classes, `ChampionAttributesLayer`, `PlacementMarkerLayer`, `ScoreBoardLayer`, `LocationMap`, `Player` and its derived classes, `Scene` and its derived classes, and `Server` |
| Shuyi Liu | 2251730 | Frontend coordination; practice and online modes; `Champion`, `ChampionAttributesLayer`, `PlacementMarkerLayer`, `ScoreBoardLayer`, and `Scene` and its derived classes; artwork for icons, buttons, battle champions, Little Legends, visual elements, and scenes; audio engine, background music, and sound effects |
| Zhaozhen Yang | 2252712 | AI player algorithm coordination; practice mode; `Player` and its derived class `AIPlayer` |
| Yukun Yang | 2252843 | Testing coordination; practice and online modes; `Battle`, `Champion`, `OfflineModeControl`, `HumanPlayer`, `OfflineModeBattleScene`, and `OnlineModeBattleScene`; battle champion artwork |

#### Archived Contribution Record

| Member | Student ID | Lines of code recorded in the original documentation | Workload share recorded in the original documentation |
| --- | --- | ---: | ---: |
| Jishen Lin (team lead) | 2250758 | 4710 | 35% |
| Shuyi Liu | 2251730 | 1385 | 25% |
| Zhaozhen Yang | 2252712 | 467 | 15% |
| Yukun Yang | 2252843 | 2282 | 25% |

These figures are preserved from the original course project documentation and have not been recalculated for the current archive. Lines of code and workload shares use different measures; artwork, testing, design, and collaboration also form part of the team's contributions.

### Build and Run

#### Environment and Dependencies

| Item | Requirement or archive status |
| --- | --- |
| Operating system | Windows; both client and server use Windows Sockets (Winsock) |
| Development environment | The original project used Microsoft Visual Studio 2022; the existing projects specify the `v143` toolset |
| Game engine | Cocos2d-x 3.17.2, including the engine source, property files, and third-party libraries referenced by the projects |
| Client platform | The project provides Debug / Release configurations for Win32 (x86) |
| Server platform | The project includes Win32 and x64 configurations; restore the overall client solution using Win32 |
| Assets | Preserve `Resources/` and its relative paths for loading scenes, fonts, and audio |

The original project's `.gitignore` excludes `cocos2d/`, and the engine is absent from this directory. The client project and solution still reference property files and the `libcocos2d`, Spine, and Recast projects under `../cocos2d/`, so opening the solution directly may result in dependency-loading failures.

#### Restore and Launch

1. Prepare Cocos2d-x 3.17.2 and its Windows build dependencies. Restore the engine as `cocos2d/` in this directory, or adjust the project references locally.
2. Open the [client solution](./proj.win32/Teamfight_Tactic.sln) in Visual Studio 2022, confirm that the C++ toolset and engine dependencies load, and select a Win32 configuration to build. The server can also be opened separately through [Server.vcxproj](./Server/Server.vcxproj).
3. Check the resource working directory. The existing `.vcxproj.user` sets the client's debug working directory to `Resources/`, and the source loads images, fonts, and audio using relative paths. Preserve the corresponding directory layout when running independently.
4. Practice mode uses local AI players. For online mode, start the server first, then enter the IPv4 address and port displayed by the server in the client. Enter the match after establishing the connection.

This procedure is based on the existing project files and source code. A complete build and online play still require verification in a Windows environment.

### Development History

The timeline below is compiled from the original course project log and preserves the environment choices and development iterations recorded at the time.

| Date | Development work |
| --- | --- |
| 2023-11-22 | Configured Python 2.7.10, CMake 3.28.0, and Cocos2d-x 4.0 environments |
| 2023-11-23 | Established coding conventions and learned Markdown documentation |
| 2023-11-24 | Studied Cocos2d-x |
| 2023-11-29 | Hosted the project repository on GitHub |
| 2023-12-03 | Learned Git and GitHub Desktop and established commit conventions; switched from Cocos2d-x 4.0 to 3.17.2 and built a test project |
| 2023-12-04 | Defined the repository structure and configured a Boost networking environment |
| 2023-12-08 | Established initial team responsibilities |
| 2023-12-09 | Switched from Boost to Socket; set up the initial project framework and implemented `AppDelegate` |
| 2023-12-10 | Set up the initial Socket networking environment |
| 2023-12-11 | Largely completed the networking environment and implemented an initial version of `Server` |
| 2023-12-12 | Largely established responsibilities and the framework; implemented `HoverButton` and the `GBKToUTF8` singleton |
| 2023-12-16 | Created the project icon |
| 2023-12-17 | Implemented an initial version of the shop |
| 2023-12-18 | Refined the initial scene background and interaction details; implemented mouse-event listeners for `Champion` |
| 2023-12-19 | Refined the framework; implemented initial versions of `Champion`, `OfflineModeControl`, `Player`, and `HumanPlayer`; implemented `InitialScene` interactions and the `LocationMap` singleton |
| 2023-12-20 | Adjusted the resources directory, `GBKToUTF8`, and `LocationMap`; implemented startup and menu scenes; implemented initial versions of the practice-mode preparation scene and `Battle`; defined champion attributes and completed battle champion artwork |
| 2023-12-22 | Implemented an initial version of `ChampionAttributesLayer` |
| 2023-12-23 | Implemented champion attribute and placement marker layers and created shop buttons; largely implemented `HumanPlayer` and the practice-mode preparation scene |
| 2023-12-24 | Implemented the gold system, adjusted namespaces, and refined the practice-mode preparation scene |
| 2023-12-25 | Implemented combat, champions, the practice-mode battle scene, practice-mode control, and the scoreboard layer; integrated team contributions and largely completed practice mode |
| 2023-12-26 | Implemented `Control`, health and experience bar effects, and weapon animations |
| 2023-12-27 | Adjusted functionality and balance; implemented shop recommendations and AI placement algorithms; refined the player classes and derived classes, integrated contributions, and completed practice mode |
| 2023-12-28 | Refined shop recommendations and AI placement algorithms; largely implemented the online menu scene |
| 2023-12-29 | Implemented initial versions of online control, preparation and battle scenes, and online mode; implemented selection and settings scenes, Little Legend movement, and the synergy system |
| 2023-12-30 | Largely completed online control and scenes; implemented the practice-mode augment scene, audio engine, and augment system |
| 2023-12-31 | Adjusted the resources directory; completed online control, related scenes, the reference scene, and the server; tested functionality and balance and wrapped up the project |

The original development log ends on December 31, 2023. Early environment experiments remain in the timeline; use the current project files and the final choice of Cocos2d-x 3.17.2 when restoring the project.

### Archive and Attribution

This project documents undergraduate team development practice. When citing its source code or describing the project, retain the original authors and team responsibilities, and refer to [LICENSE](./LICENSE).

[Back to Course Directory](../README.md#english) · [Back to Repository Home](../../README.md#english)
