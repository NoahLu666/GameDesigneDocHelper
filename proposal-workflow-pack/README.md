# 策划案 Workflow Pack

这是一套给 Agent 导入使用的多-skill 工作流，目标是稳定地引导用户 step by step 产出公司内部立项文档，并在完成后进行复盘与自我优化。

默认场景是公司内部立项，而不是泛用文档写作：

- 固定平台为微信小程序
- 固定产品形态为多人联机游戏平台
- 默认所有项目都需要支持多人游玩
- 输出目标是内部评审可讨论、可推进的立项文档
- 不是完整量产策划案，不要求一次写完所有系统、关卡和数值

## 设计目标

- 让 Agent 先基于公司平台约束问对问题，再开始写
- 把输出拆成阶段产物，避免一次性胡写
- 强制保留假设、待验证项、证据来源
- 最终产出标准化文档，并附带复盘记录
- 最终默认交付飞书友好的 `.md`，便于直接上传到飞书云文档

## 当前推荐

优先使用总控 skill：

- `skills/li-xiang-zhu-shou/SKILL.md`

这一个 skill 已经把 Intake、Outline、Draft、Export、老板评审、立项复盘整合在一起。

## 兼容使用顺序

1. 导入 `skills/proposal-intake/SKILL.md`
2. 导入 `skills/proposal-outline/SKILL.md`
3. 导入 `skills/proposal-draft/SKILL.md`
4. 导入 `skills/proposal-retro/SKILL.md`
5. 需要参考结构时，再导入 `references/document-structure.md`
6. 需要直接出文档时，使用 `templates/proposal-template.md`

## 工作流分段

### 1. Intake

目标：把模糊想法收束成可写的项目简报。

输出：
- `00_project_brief.md`

### 2. Outline

目标：把项目简报映射到标准文档结构，并补齐关键缺口。

输出：
- `01_outline.md`
- `01_open_questions.md`

### 3. Draft

目标：按模板生成完整策划案，显式标记假设与待验证项。

输出：
- `02_proposal.md`

### 4. Retro

目标：回看本次工作过程，定位信息缺口、论证弱点、流程可优化点。

输出：
- `03_retro.md`
- `03_workflow_improvements.md`

### 5. Export

目标：把最终立项文档整理为飞书友好的 `.md` 文件。

输出：
- `项目名-立项文档-飞书版.md`

使用方式：
- 在飞书云文档中直接上传 `.md` 文件
- 选择“创建飞书云文档”

### 6. 老板评审

手动触发：`/老板评审`

输出：
- `老板评审.md`

### 7. 立项复盘

手动触发：`/立项复盘`

输出：
- `03_retro.md`
- `03_workflow_improvements.md`

## 标准输出约束

- Intake / Outline / Draft / Retro 阶段的工作产物统一使用 Markdown
- 工作流结束时，必须额外产出 1 份飞书友好的 `.md`
- 每份文档开头都包含：
  - 项目名称
  - 文档阶段
  - 版本号
  - 日期
  - 信息可信度等级
- 对不确定内容统一使用：
  - `[假设]`
  - `[待确认]`
  - `[待验证]`
- 不允许把未知内容伪装成已确认事实

## 推荐目录结构

```text
proposal-workflow-pack/
  README.md
  workflow.md
  references/
    document-structure.md
  templates/
    proposal-template.md
  skills/
    proposal-intake/
      SKILL.md
    li-xiang-zhu-shou/
      SKILL.md
    proposal-outline/
      SKILL.md
    proposal-draft/
      SKILL.md
    proposal-retro/
      SKILL.md
```
