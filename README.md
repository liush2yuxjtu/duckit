# 🦆 duckit

> 把 Claude 上一句长篇大论，让一只小鸭子用人话讲给你听。

```
你：           "/duckit"
Claude:        🦆 嘎嘎！上一段你没看完那堆 — 鸭子帮你嚼烂了：
                ...短句、好懂、技术细节一字不差。
                — 一只小鸭 🦆
```

**一句话**：Claude 的回答太长，没耐心读？输入 `/duckit`，让小鸭子重讲一遍 — 中文、可爱、保留所有 code 与命令。

---

## ✨ 它到底干啥

- 抓取当前对话里 **上一条 assistant 消息**（不读磁盘、不爬 jsonl、不开子进程）。
- 把长篇技术解释翻译成 **中文鸭子语**：短句、好懂、偶尔 `嘎`。
- **代码、路径、命令、错误串、数字 byte-exact 不变** — 你照样能复制粘贴跑。
- 三档音量：`full`（默认）/ `lite`（少 quack）/ `ultra`（极简 bullet）。

英文回答？也能用 — 鸭子只说中文，但代码原样保留。

## 🎬 30 秒 demo

**Claude 原话（英文，一大段）：**
> Bug in auth middleware. Token expiry check use `<` not `<=`. Fix: change to `<=`.

**`/duckit` 之后：**
> 🦆 嘎嘎！鸭子翻了翻日志：auth middleware 漏水啦。token 过期那行写了 `<`，应当是 `<=`，刚到点的 token 被错放进门。改成 `<=` 就堵上漏洞，嘎。
> — 一只小鸭 🦆

短了一半，技术全在，还能复制 `<=` 直接改代码。

## 🚀 安装（30 秒）

```bash
git clone https://github.com/liush2yuxjtu/duckit.git ~/.claude/skills/duckit
```

打开 Claude Code，在任何对话里输入 `/duckit` — 上一条 assistant 消息瞬间变成鸭子版。

不想全局装？想做项目级 skill？

```bash
git clone https://github.com/liush2yuxjtu/duckit.git \
  /path/to/your/project/.claude/skills/duckit
```

无依赖、无脚本、无 build。一个 `SKILL.md` + 一个 `references/examples.md`，纯 markdown。

## 🎚️ 三档音量

| 触发 | 行为 |
|------|------|
| `/duckit` | 默认 `full`：开头 `🦆 嘎嘎！`，每段 1–2 个 `嘎`，长度 ≤ 60% 源文 |
| `/duckit lite` | 不开嘎、每段 ≤1 嘎、长度 ≤ 60% — 适合上班摸鱼时还要装严肃 |
| `/duckit ultra` | 纯 bullet、全文最多 1 嘎、长度 ≤ 30% — 给"我只想看 TL;DR"的你 |

也吃中文触发：`鸭子讲讲`、`用鸭子解释`、`轻一点`、`压到底`、`再鸭一遍`。

## 🦆 为什么写它

vibe coding 的时代，Claude 一段回答动辄 200 行。你滚到一半就走神了。  
但里面真有用的就那 3 句话 + 1 个命令。

duckit = **强制压缩 + 萌化**。  
小鸭子比 senior engineer 容易读懂。代码块照旧 byte-exact，你不会丢任何一个 `--no-verify`。

## 🤝 贡献 / 反馈

- 想改鸭子语气？编辑 `SKILL.md` 的 modes 表 + hard rules。
- 想加示例？在 `references/examples.md` 里加一对 source / duck。
- PR / issue 全都欢迎，鸭子来者不拒。

## 📝 License

MIT — 拿去用，做啥都行。

---

— 一只小鸭 🦆
