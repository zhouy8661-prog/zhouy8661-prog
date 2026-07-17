<h1 align="center">
  <span style="color:#58A6FF">Zhou Yue</span>
</h1>

<h3 align="center">UE5 Technical Designer</h3>

<p align="center">
  <b>Gameplay Systems</b> &nbsp;|&nbsp;
  <b>Blueprint Architecture</b> &nbsp;|&nbsp;
  <b>Data Driven Design</b>
</p>

<p align="center">
  <a href="https://github.com/zhouy8661-prog/UE5-Tech-Design"><img src="https://img.shields.io/badge/技术文档-UE5_Tech_Design-58A6FF?style=for-the-badge&logo=unrealengine&logoColor=white" /></a>
  <a href="https://github.com/zhouy8661-prog/portfolio"><img src="https://img.shields.io/badge/Portfolio-Web-3FB950?style=for-the-badge&logo=vercel&logoColor=white" /></a>
</p>

---

## 🎮 Featured Projects

<table>
<tr>
<td width="50%">
<h3 align="center">归渊 · 木府</h3>
<p align="center">
  <img src="https://img.shields.io/badge/UE5-5.4-0D1117?logo=unrealengine&logoColor=white" />
  <img src="https://img.shields.io/badge/Blueprint-100%25-58A6FF" />
  <img src="https://img.shields.io/badge/Genre-Action_Adventure-F0883E" />
</p>
<p>
UE5 第三人称动作冒险游戏。负责核心系统设计与实现，包括存档系统、对话系统、AI 行为树、战斗系统等完整 Gameplay 框架。
</p>
<p>
  <a href="#">📁 Repository (Private)</a>
</p>
</td>
<td width="50%">
<h3 align="center">归渊 · 闽南版</h3>
<p align="center">
  <img src="https://img.shields.io/badge/UE5-5.4-0D1117?logo=unrealengine&logoColor=white" />
  <img src="https://img.shields.io/badge/Blueprint-100%25-58A6FF" />
  <img src="https://img.shields.io/badge/Theme-Minnan_Culture-F0883E" />
</p>
<p>
基于归渊项目的闽南文化主题版本。融合地域文化元素的关卡设计、角色系统重构与玩法扩展。
</p>
<p>
  <a href="#">📁 Repository (Private)</a>
</p>
</td>
</tr>
<tr>
<td width="50%">
<h3 align="center">48h Game Jam</h3>
<p align="center">
  <img src="https://img.shields.io/badge/UE5-5.4-0D1117?logo=unrealengine&logoColor=white" />
  <img src="https://img.shields.io/badge/Duration-48h-F0883E" />
</p>
<p>
48 小时游戏开发挑战作品。在极限时间内完成核心玩法循环、快速原型搭建与迭代。
</p>
<p>
  <a href="#">📁 Repository</a>
</p>
</td>
<td width="50%">
<h3 align="center">UE5 Tech Design Docs</h3>
<p align="center">
  <img src="https://img.shields.io/badge/Docs-9_Systems-58A6FF" />
  <img src="https://img.shields.io/badge/Format-Markdown-3FB950" />
</p>
<p>
基于 UE5 学习笔记整理的 9 大系统技术方案文档。涵盖存档、AI、战斗、运动、UI、动画等核心系统。
</p>
<p>
  <a href="https://github.com/zhouy8661-prog/UE5-Tech-Design">📁 View Repository →</a>
</p>
</td>
</tr>
</table>

---

## 📚 Technical Documentation

> 基于 UE5 学习笔记整理的 9 大系统技术方案，每个系统均包含：系统概述 → 系统设计 → 数据设计 → 开发设计

| # | System | Core Content |
|---|--------|-------------|
| 01 | **存档系统** | SaveGame / GameInstance / Interface 模块化架构 |
| 02 | **AI 行为树** | BehaviorTree / EQS / AI Perception 完整 AI |
| 03 | **战斗攻击** | 血量计算 / 伤害检测 / 锁定 / 处决 / 暗杀 / QTE |
| 04 | **角色运动** | 状态机 / 跳跃 / 滑铲 / 滑翔 / 瞬移 |
| 05 | **技能系统** | 物理对象 / 时空穿越 / 重力改变 / 投掷 |
| 06 | **UI 界面** | 主菜单 / 设置 / 小地图 / 加载 / 对话 |
| 07 | **动画系统 (ALS)** | IK / 蒙太奇 / 根运动 / 姿势快照 / 布娃娃 |
| 08 | **材质后处理** | 描边 / 醉酒 / 濒死 / 掩码剔除 / 高亮 |
| 09 | **蓝图通讯** | 接口 / 结构体 / 事件分发器 / 组件引用 |

<p align="center">
  <a href="https://github.com/zhouy8661-prog/UE5-Tech-Design">
    <img src="https://img.shields.io/badge/View_All_Docs-→-58A6FF?style=for-the-badge" />
  </a>
</p>

---

## 🧩 Blueprint Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    GameInstance                          │
│         ┌──────────────┬──────────────┐                 │
│         │  SaveManager │  DialogueMgr │  ...            │
│         └──────────────┴──────────────┘                 │
│                          │                              │
│         ┌────────────────┴────────────────┐             │
│         │        Level Blueprint          │             │
│         └────────────────┬────────────────┘             │
│                          │                              │
│    ┌─────────────────────┼─────────────────────┐        │
│    │               Player Pawn                  │        │
│    │  ┌──────────┬──────────┬──────────────┐   │        │
│    │  │Movement  │ Combat   │ Interaction  │   │        │
│    │  │Component │ Component│ Component    │   │        │
│    │  └──────────┴──────────┴──────────────┘   │        │
│    └─────────────────────┬─────────────────────┘        │
│                          │                              │
│    ┌─────────────────────┼─────────────────────┐        │
│    │              AI Controller                 │        │
│    │  ┌──────────┬──────────┬──────────────┐   │        │
│    │  │Behavior  │Perception│ EQS Query    │   │        │
│    │  │Tree      │          │              │   │        │
│    │  └──────────┴──────────┴──────────────┘   │        │
│    └───────────────────────────────────────────┘        │
│                          │                              │
│    ┌─────────────────────┴─────────────────────┐        │
│    │              SaveGame Object              │        │
│    │  ┌──────────────────────────────────┐     │        │
│    │  │  ST_WorldState[]  DT_Dialogue    │     │        │
│    │  └──────────────────────────────────┘     │        │
│    └───────────────────────────────────────────┘        │
└─────────────────────────────────────────────────────────┘
```

> Architecture follows: **GameInstance → Level → Pawn → Component → SaveGame**  
> Communication via: **Blueprint Interface + Event Dispatcher + Struct**

---

## ⚙️ Engineering Practice

<table>
<tr>
<td width="33%">
<h4>📐 Coding Standards</h4>
<ul>
<li>BP_ prefix for Blueprints</li>
<li>ST_ prefix for Structs</li>
<li>DT_ prefix for DataTables</li>
<li>E_ prefix for Enums</li>
<li>BPI_ prefix for Interfaces</li>
</ul>
</td>
<td width="33%">
<h4>📁 Folder Structure</h4>
<ul>
<li>Content/Blueprints/</li>
<li>Content/Data/Structs/</li>
<li>Content/Data/DataTables/</li>
<li>Content/UI/</li>
<li>Content/AI/</li>
</ul>
</td>
<td width="34%">
<h4>🔧 Best Practices</h4>
<ul>
<li>Interface over CastTo</li>
<li>Struct over scattered vars</li>
<li>Event Dispatcher for broadcast</li>
<li>Cached Pose for reuse</li>
<li>Async save for performance</li>
</ul>
</td>
</tr>
</table>

---

## 🐞 Problem Solving

<details>
<summary><b>📌 Save System: Cross-Level Data Transfer</b></summary>
<br>

**Problem:** Save UI on level 00 cannot read data from level 01

**Root Cause:** Level Blueprints are isolated; variables reset on level transition

**Solution:** GameInstance as persistent data hub → SaveGame → Level Blueprint

```
UI → Interface → SaveManager → SaveGame → DataStruct → Disk
```
</details>

<details>
<summary><b>📌 AI Focus: Enemy Switches Between Targets</b></summary>
<br>

**Problem:** During possession switching, AI oscillates between original body and possessed body

**Root Cause:** AI was focusing on fixed Player Pawn reference instead of dynamic target

**Solution:** Focus on the current target actor from Blackboard, not hardcoded Player Pawn
</details>

<details>
<summary><b>📌 Animation: Landing Slide During AI Patrol</b></summary>
<br>

**Problem:** Enemy slides forward during landing animation, breaking AI navigation

**Root Cause:** Movement Mode set to None during landing, causing AI navigation request to be eliminated

**Solution:** Restore Movement Mode to Walking + manually restart patrol task after landing
</details>

<details>
<summary><b>📌 Widget: UI Layout Distortion</b></summary>
<br>

**Problem:** UI elements deform across different screen resolutions

**Root Cause:** No size constraints or anchor configurations

**Solution:** SizeBox + Anchor for constraint; Overlay for multi-layer stacking
</details>

---

## 📝 Latest Updates

```
2026 July
├── ✔ Refactored Save System (GameInstance + Interface architecture)
├── ✔ Completed Dialogue System with DataTable integration
├── ✔ Built AI Behavior Tree with EQS intelligent pursuit
├── ✔ Implemented Execution & Stealth Kill systems
├── ✔ Created 9-system Technical Design Documentation
└── ✔ Published GitHub Developer Portal
```

---

## 🛠 Technical Skills

<p align="center">
  <img src="https://img.shields.io/badge/Unreal_Engine-5.4-0D1117?style=for-the-badge&logo=unrealengine&logoColor=white" />
  <img src="https://img.shields.io/badge/Blueprint-Architecture-58A6FF?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Gameplay_Framework-Systems-F0883E?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Behavior_Tree-AI-3FB950?style=for-the-badge" />
  <img src="https://img.shields.io/badge/UMG-UI_Design-58A6FF?style=for-the-badge" />
  <img src="https://img.shields.io/badge/DataTable-Data_Driven-F0883E?style=for-the-badge" />
  <img src="https://img.shields.io/badge/State_Machine-Animation-3FB950?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Git-Version_Control-58A6FF?style=for-the-badge&logo=git&logoColor=white" />
</p>

---

## 📬 Contact

<p align="center">
  <a href="https://github.com/zhouy8661-prog">
    <img src="https://img.shields.io/badge/GitHub-zhouy8661--prog-0D1117?style=for-the-badge&logo=github&logoColor=white" />
  </a>
  <a href="mailto:your.email@example.com">
    <img src="https://img.shields.io/badge/Email-Contact-58A6FF?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
</p>

---

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=zhouy8661-prog&color=58A6FF&style=flat-square" alt="Profile views" />
</p>

<p align="center">
  <i>"Building game systems, not just game features."</i>
</p>
