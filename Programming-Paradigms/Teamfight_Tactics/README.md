# Teamfight Tactics Auto-Battler Course Project

**English** | [简体中文](./README.zh-CN.md)

Teamfight_Tactics is an auto-battler developed as a team project for Tongji University's Programming Paradigms course, implemented in C++ with Cocos2d-x 3.17.2. Drawing on the gameplay of Dota Auto Chess, Teamfight Tactics, and Battle of Golden Spatula (《金铲铲之战》), the project combines card purchasing, team composition, automated combat, and multiplayer communication.

This directory archives the client and server source code, game assets, and Visual Studio projects. The original team repository is [MinmusLin/Teamfight_Tactics](https://github.com/MinmusLin/Teamfight_Tactics).

## Feature Overview

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

## Code Structure

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

## Team Responsibilities

| Member | Student ID | Main responsibilities and modules |
| --- | --- | --- |
| Jishen Lin (team lead) | 2250758 | Backend coordination, task assignment, and code review; project framework and network environment; practice and online modes; `AppDelegate`, `Battle`, `HoverButton`, `Champion`, `Control` and its derived classes, `ChampionAttributesLayer`, `PlacementMarkerLayer`, `ScoreBoardLayer`, `LocationMap`, `Player` and its derived classes, `Scene` and its derived classes, and `Server` |
| Shuyi Liu | 2251730 | Frontend coordination; practice and online modes; `Champion`, `ChampionAttributesLayer`, `PlacementMarkerLayer`, `ScoreBoardLayer`, and `Scene` and its derived classes; artwork for icons, buttons, battle champions, Little Legends, visual elements, and scenes; audio engine, background music, and sound effects |
| Zhaozhen Yang | 2252712 | AI player algorithm coordination; practice mode; `Player` and its derived class `AIPlayer` |
| Yukun Yang | 2252843 | Testing coordination; practice and online modes; `Battle`, `Champion`, `OfflineModeControl`, `HumanPlayer`, `OfflineModeBattleScene`, and `OnlineModeBattleScene`; battle champion artwork |

### Archived Contribution Record

| Member | Student ID | Lines of code recorded in the original documentation | Workload share recorded in the original documentation |
| --- | --- | ---: | ---: |
| Jishen Lin (team lead) | 2250758 | 4710 | 35% |
| Shuyi Liu | 2251730 | 1385 | 25% |
| Zhaozhen Yang | 2252712 | 467 | 15% |
| Yukun Yang | 2252843 | 2282 | 25% |

These figures are preserved from the original course project documentation and have not been recalculated for the current archive. Lines of code and workload shares use different measures; artwork, testing, design, and collaboration also form part of the team's contributions.

## Build and Run

### Environment and Dependencies

| Item | Requirement or archive status |
| --- | --- |
| Operating system | Windows; both client and server use Windows Sockets (Winsock) |
| Development environment | The original project used Microsoft Visual Studio 2022; the existing projects specify the `v143` toolset |
| Game engine | Cocos2d-x 3.17.2, including the engine source, property files, and third-party libraries referenced by the projects |
| Client platform | The project provides Debug / Release configurations for Win32 (x86) |
| Server platform | The project includes Win32 and x64 configurations; restore the overall client solution using Win32 |
| Assets | Preserve `Resources/` and its relative paths for loading scenes, fonts, and audio |

The original project's `.gitignore` excludes `cocos2d/`, and the engine is absent from this directory. The client project and solution still reference property files and the `libcocos2d`, Spine, and Recast projects under `../cocos2d/`, so opening the solution directly may result in dependency-loading failures.

### Restore and Launch

1. Prepare Cocos2d-x 3.17.2 and its Windows build dependencies. Restore the engine as `cocos2d/` in this directory, or adjust the project references locally.
2. Open the [client solution](./proj.win32/Teamfight_Tactic.sln) in Visual Studio 2022, confirm that the C++ toolset and engine dependencies load, and select a Win32 configuration to build. The server can also be opened separately through [Server.vcxproj](./Server/Server.vcxproj).
3. Check the resource working directory. The existing `.vcxproj.user` sets the client's debug working directory to `Resources/`, and the source loads images, fonts, and audio using relative paths. Preserve the corresponding directory layout when running independently.
4. Practice mode uses local AI players. For online mode, start the server first, then enter the IPv4 address and port displayed by the server in the client. Enter the match after establishing the connection.

This procedure is based on the existing project files and source code. A complete build and online play still require verification in a Windows environment.

## Development History

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

## Archive and Attribution

This project documents undergraduate team development practice. When citing its source code or describing the project, retain the original authors and team responsibilities, and refer to [LICENSE](./LICENSE).

[Back to Course Directory](../README.md) · [Back to Repository Home](../../README.md)
