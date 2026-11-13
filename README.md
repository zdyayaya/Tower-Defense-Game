# Tower-Defense-Game 塔防游戏
基于 Unity 的屋脊兽主题 3D 策略塔防游戏，包含五种守护单位、三档难度关卡
A Unity-based 3D strategy tower defense game themed around traditional Chinese roof-ridge beasts, featuring five types of guardian units and three difficulty levels.

中文介绍：
> 守一方屋檐，护一境安宁。

这是一款以中国传统屋脊兽为灵感的 3D 策略塔防游戏，使用 Unity 和 C# 开发。玩家需要在网格地图上部署龙、狮子、狻猊、獬豸与仙人，规划位置和朝向，搭配输出、控制与辅助能力，抵御不断来袭的敌人，守住据点。

游戏将屋脊兽文化主题与塔防玩法结合，提供简单、普通、困难三个关卡，以及可翻页的《脊兽录》，让玩家在布阵与战斗之外了解这些守护形象。

## 游戏特色

- **五种守护单位**：群体吐息、击退、毒雾、投射物攻击、治疗与护盾，各有不同的战场作用。
- **位置与朝向策略**：在可建造地块上部署单位，从四个方向中选择朝向，通过格子预览查看作用范围。
- **三档难度**：简单、普通、困难分别对应不同关卡，敌人的移动速度、攻击伤害与生成节奏随难度变化。
- **限时守护挑战**：当前正式关卡的计时目标为游戏内 90 秒；敌人生成逐渐加快，需要持续调整防线。
- **金币循环**：击败敌人获得掉落金币，用于部署更多单位；支持手动拾取与自动收集。
- **文化图鉴与设置**：提供《脊兽录》、背景音乐和音效音量调节，以及自动拾取设置保存。

## 守护单位

| 单位 | 部署费用 | 能力与定位 |
| --- | --- | --- |
| 龙 | 10 | 以吐息攻击范围内的敌人，提供群体伤害 |
| 狮子 | 15 | 对范围内敌人造成伤害并击退，延缓敌人推进 |
| 狻猊 | 10 | 生成毒雾，对范围内敌人持续造成伤害 |
| 獬豸 | 10 | 发射追踪投射物，攻击单个目标 |
| 仙人 | 15 | 为作用范围内的友方防御单位恢复生命并提供护盾 |

## 玩法与操作

1. 在主菜单选择难度，进入关卡，观察敌人的行进路线。
2. 点击底部单位按钮，将鼠标移动到可建造地块，预览部署位置与范围。
3. 左键点击地块完成放置，再点击方向箭头确认朝向，单位随后开始发挥作用。
4. 收集敌人掉落的金币，补充防线，搭配不同单位应对来袭敌人。
5. 在关卡计时结束时保持据点生命值大于零即可获胜；生命值归零则失败。

| 操作 | 功能 |
| --- | --- |
| 鼠标左键 | 选择单位、放置单位、确认方向、拾取金币及操作界面 |
| 鼠标悬停方向箭头 | 预览对应方向的作用范围 |
| 鼠标左键点击已部署单位 | 查看该单位的作用范围 |
| 鼠标右键 | 取消当前部署；已放置但尚未确认方向的单位会退还本次部署费用 |
| `Esc` | 暂停或继续游戏；部署过程中按下会先取消当前部署 |
| `R` | 失败结算按钮出现后，重新开始当前关卡 |

## 开发环境

| 项目 | 版本或配置 |
| --- | --- |
| Unity 编辑器 | `2022.3.62f3c1` |
| 开发语言 | C# |
| 渲染管线 | Universal Render Pipeline（URP）`14.0.12` |
| 界面 | Unity UI（uGUI）、TextMesh Pro `3.0.7` |
| Windows 构建目标 | Intel 64-bit（x86_64） |


## 项目结构

```text
Assets/
├── Assets/
│   ├── Scenes/         # 主菜单、三个正式关卡及原型场景
│   ├── Scripts/
│   │   ├── Core/       # 游戏进度、生命值、难度与路径
│   │   ├── Enemy/      # 敌人行为与生成
│   │   ├── Tower/      # 守护单位、投射物与技能
│   │   ├── Grid/       # 地块与建造规则
│   │   ├── Items/      # 金币与方向选择
│   │   ├── System/     # 货币与据点生命值
│   │   ├── UI/         # 菜单、设置、暂停与部署交互
│   │   └── Music/      # 音乐与音效管理
│   ├── Prefabs/        # 单位、敌人、地块与特效预制体
│   └── UI/             # 共享游戏 HUD 与界面资源
├── HandBook/           # 《脊兽录》图鉴预制体与图片
├── Book/               # 翻页交互脚本
└── Editor/             # 编辑器回归检查工具
Packages/               # Unity 包依赖
ProjectSettings/        # Unity 项目配置
PROJECT_NOTES.md        # 开发维护记录
```
English introduction

2. Click a unit button at the bottom of the screen, then move the cursor over a buildable tile to preview its position and range.
3. Left-click the tile to place the unit, then click a direction arrow to confirm its facing direction and activate it.
4. Collect coins dropped by enemies, reinforce your defenses, and combine different units to handle incoming threats.
5. Keep your base's health above zero until the level timer ends to win. If its health reaches zero, you lose.

| Input | Action |
| --- | --- |
| Left mouse button | Select and place units, confirm directions, collect coins, and interact with the interface |
| Hover over a direction arrow | Preview the effective range for that direction |
| Left-click a deployed unit | View the unit's effective range |
| Right mouse button | Cancel the current deployment; a placed unit whose direction has not been confirmed refunds its deployment cost |
| `Esc` | Pause or resume the game; if a deployment is in progress, cancel it before pausing |
| `R` | Restart the current level after a defeat, once the result screen buttons appear |

## Development Environment

| Component | Version or Configuration |
| --- | --- |
| Unity Editor | `2022.3.62f3c1` |
| Language | C# |
| Render pipeline | Universal Render Pipeline (URP) `14.0.12` |
| UI | Unity UI (uGUI), TextMesh Pro `3.0.7` |
| Windows build target | Intel 64-bit (x86_64) |

## Project Structure

```text
Assets/
├── Assets/
│   ├── Scenes/         # Main menu, three gameplay levels, and prototype scenes
│   ├── Scripts/
│   │   ├── Core/       # Game progress, health, difficulty, and paths
│   │   ├── Enemy/      # Enemy behavior and spawning
│   │   ├── Tower/      # Guardian units, projectiles, and abilities
│   │   ├── Grid/       # Tiles and building rules
│   │   ├── Items/      # Coins and direction selection
│   │   ├── System/     # Currency and base health
│   │   ├── UI/         # Menus, settings, pause, and deployment interactions
│   │   └── Music/      # Music and sound effect management
│   ├── Prefabs/        # Unit, enemy, tile, and effect prefabs
│   └── UI/             # Shared gameplay HUD and UI assets
├── HandBook/           # Roof Beast Compendium prefab and images
├── Book/               # Page-turning interaction scripts
└── Editor/             # Editor regression check tools
Packages/               # Unity package dependencies
ProjectSettings/        # Unity project configuration
PROJECT_NOTES.md        # Development and maintenance notes
```
