# 🦆 duckit

> **Claude 回答 200 行，你看到第 3 行就关了？** 敲 `/duckit` — 一只中文小鸭子用人话重讲一遍，代码、命令、数字一字不动。30 秒装好。

> *vibe coding = 你说需求、AI 写代码、你只审不写。AI 写得多说得也多 — duckit 把 200 行说人话。*

```
你：           /duckit
Claude:        🦆 嘎嘎！上一段你没看完那堆 — 鸭子帮你嚼烂了：
                ...短句、好懂、技术细节一字不差。
                — 一只小鸭 🦆
```

duckit 是 Claude Code 的一个 **skill**（丢进 `~/.claude/skills/` 自动激活的小插件，无依赖）。敲 `/duckit`，上一条 assistant 消息瞬间变中文鸭子语：代码 / 命令 / 路径 / 错误串 / 版本号 **byte-exact 不变**，你照样复制粘贴跑。

## 看效果

**Claude 原话（一大段英文）：**
> Bug in auth middleware. Token expiry check use `<` not `<=`. Fix: change to `<=`.

**`/duckit` 之后：**
> 🦆 嘎嘎！鸭子翻了翻日志：auth middleware 漏水啦。token 过期那行写了 `<`，应当是 `<=`，刚到点的 token 被错放进门。改成 `<=` 就堵上漏洞，嘎。
> — 一只小鸭 🦆

短了一半，技术全在，`<=` 直接复制改代码。

## 装它（一行）

```bash
git clone https://github.com/liush2yuxjtu/duckit.git ~/.claude/skills/duckit
```

复制 → 粘贴 → 回车 → **完事**。打开 Claude Code，任何对话里敲 `/duckit`。

> 想装项目级？把目标路径换成 `your-project/.claude/skills/duckit`。

## 三档音量

| 触发 | 适合 | 行为 |
|------|------|------|
| `/duckit` | 默认 | 开头 `🦆 嘎嘎！`，每段 1–2 个 `嘎`，≤ 60% 源文长度 |
| `/duckit lite` | 上班摸鱼装严肃 | 不开嘎，每段 ≤1 嘎，≤ 60% |
| `/duckit ultra` | 只想看 TL;DR | 纯 bullet，全文最多 1 嘎，≤ 30% |

也吃中文触发：`鸭子讲讲`、`用鸭子解释`、`轻一点`、`压到底`、`再鸭一遍`。

## 它的承诺

- **不读磁盘、不爬 jsonl、不开子进程** — 纯 in-context 改写，零副作用。
- **byte-exact 代码保留** — 你不会丢任何一个 `--no-verify`。
- **英文进、中文出** — Claude 用英文回？鸭子还是说中文，代码原样。
- **纯 markdown 两个文件**（`SKILL.md` + `references/examples.md`），看得懂、改得动。

## License

MIT — 拿去用，做啥都行。

---

— 一只小鸭 🦆
