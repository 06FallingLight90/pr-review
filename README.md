# pr-review

普适的 PR/MR 审查技能（Agent Skill），不绑定特定项目或技术栈。审查不仅找出 bug，更要回答四个问题：改动是否与项目既有结构/理念/契约一致、是否符合贡献原则（CONTRIBUTING）、PR 声称的功能是否真的实现到位、实现中隐藏了哪些问题。

## 仓库结构

```
.
├── README.md
└── skills/
    └── pr-review/          # 技能本体
        └── SKILL.md        # 九步审查流程 + 检查清单 + 汇报模板
```

## 覆盖流程

拉取改动（含记录原始分支）→ 理解意图与范围 → 一致性核对（契约/结构/理念）→ 贡献原则（CONTRIBUTING）核对 → 功能实现程度评估 → 潜在问题排查清单 → 汇报与修复 → 测试验证 → 合并关闭与工作区收尾（切回原分支、拉取最新、清理确认）。

## 安装到 Trae 全局技能

以 junction 链接接入，实时同步本仓库改动：

```powershell
New-Item -ItemType Junction -Path "$env:USERPROFILE\.trae-cn\skills\pr-review" -Target "<本仓库路径>\skills\pr-review"
```

## 触发场景

- 审查 PR / MR / commit / 分支差异（给出链接、编号或 diff）
- 评估改动与文档/协议/项目结构的一致性
- 合并前最终检查、结构性判断（文件放置、方案取舍）
