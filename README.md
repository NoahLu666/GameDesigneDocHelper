# GameDesigneDocHelper

公司内部游戏立项文档助手包，默认面向微信小程序多人联机游戏平台。

当前主入口是总控 skill：

- `proposal-workflow-pack/skills/li-xiang-zhu-shou/SKILL.md`

这个 skill 会：

- 先判断项目类型
- 有竞品时先检索再提问
- 按游戏类型切换追问重点
- step by step 生成立项文档
- 输出飞书友好的 Markdown 文档
- 支持手动触发 `/老板评审`
- 支持手动触发 `/立项复盘`

## 仓库结构

```text
GameDesigneDocHelper/
  README.md
  proposal-workflow-pack/
    README.md
    workflow.md
    references/
    templates/
    skills/
      li-xiang-zhu-shou/
        SKILL.md
      proposal-intake/
        SKILL.md
      proposal-outline/
        SKILL.md
      proposal-draft/
        SKILL.md
      proposal-retro/
        SKILL.md
```

## 使用方式

1. clone 仓库

```powershell
git clone https://github.com/NoahLu666/GameDesigneDocHelper.git
```

2. 打开主 skill

```text
proposal-workflow-pack/skills/li-xiang-zhu-shou/SKILL.md
```

3. 将该 skill 导入到 agent 使用

4. 默认输出飞书友好的 `.md` 文件

在飞书云文档中可直接上传 `.md` 文件，并选择“创建飞书云文档”。

## 手动指令

- `/老板评审`
  以老板 / CEO 视角对当前立项文档做尖锐评审

- `/立项复盘`
  生成 workflow 复盘文件，方便后续测试者提交复盘结果

## 说明

- 这套工具主要用于立项文档，不是完整量产策划案工具
- 商业化部分在立项阶段只保留方向性描述
- 核心玩法、操作、地图、敌人、角色、build 和 MVP 验证方式需要重点展开
