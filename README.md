# Memory Skill

跨对话记忆系统——让 Claude 在对话结束时保存结构化记忆，下次对话恢复上下文。

## 安装

将 `SKILL.md` 放到你项目的 `.claude/skills/memory/` 目录下：

```bash
mkdir -p .claude/skills/memory
cp SKILL.md .claude/skills/memory/
```

或通过 Claude Code 安装 `.skill` 包。

## 使用

### 对话中标记重要内容

直接说 **"标记一下"**、**"这个重要"**、**"记住这个"**，Claude 会标记当前讨论的内容，最终保存时必定包含。

### 结束对话时保存

说 **"这次对话结束了，帮我记下来"**、**"总结一下"**、**"save this session"**，Claude 会：

1. 扫描整段对话，提取关键信息
2. 生成结构化记忆文件到 `.claude/memory/YYYY-MM-DD-主题.md`
3. 更新索引文件 `MEMORY_INDEX.md`

### 新对话加载记忆

说 **"加载记忆"**、**"继续上次的"**、**"load memory"**，Claude 会列出所有记忆文件供你选择加载。

## 存储结构

```
项目根目录/.claude/memory/
├── MEMORY_INDEX.md                 # 索引文件
├── 2026-06-21-实现跨项目记忆技能.md
├── 2026-06-20-修复登录模块bug.md
└── ...
```

每个项目独立存储，互不影响。

## 许可

MIT
