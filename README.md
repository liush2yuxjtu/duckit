# 🦆 duckit

> Claude 回答 200 行，你看到第 3 行就关了？输入 `/duckit` — 中文短句、保留所有代码、可爱小鸭子讲给你听。

```
你：           /duckit
Claude:        🦆 嘎嘎！上一段你没看完那堆 — 鸭子帮你嚼烂了：
                ...短句、好懂、技术细节一字不差。
                — 一只小鸭 🦆
```

**没耐心读 Claude 的长篇大论？** duckit 是一个 Claude Code skill，把上一条 assistant 消息压成中文鸭子语 — 代码、命令、路径、数字 **byte-exact 不变**，你照样复制粘贴跑。

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

完事。打开 Claude Code，任何对话里敲 `/duckit` — 上一条回答瞬间变鸭子版。

> 项目级 skill？把目标路径换成 `your-project/.claude/skills/duckit` 即可。

无依赖、无脚本、无 build。纯 markdown 两个文件 (`SKILL.md` + `references/examples.md`)。

## 三档音量

| 触发 | 适合 | 行为 |
|------|------|------|
| `/duckit` | 默认 | 开头 `🦆 嘎嘎！`，每段 1–2 个 `嘎`，长度 ≤ 60% 源文 |
| `/duckit lite` | 上班摸鱼装严肃 | 不开嘎，每段 ≤1 嘎，长度 ≤ 60% |
| `/duckit ultra` | 只想看 TL;DR | 纯 bullet，全文最多 1 嘎，长度 ≤ 30% |

也吃中文触发：`鸭子讲讲`、`用鸭子解释`、`轻一点`、`压到底`、`再鸭一遍`。

## 它干啥（30 秒）

- 抓当前对话里 **上一条 assistant 消息**（纯 in-context，不读磁盘、不爬 jsonl）。
- 翻成 **中文鸭子语**：短句、好懂、偶尔 `嘎`。英文回答也能吃 — 鸭子只说中文，代码原样。
- **保 byte-exact**：所有 `code`、命令、路径、错误串、数字、版本号 — 一字不动。
- 三档音量自由切。

## 为什么写它

vibe coding 时代，Claude 一段回答 200 行。你滚到一半就走神。  
真正有用的 3 句话 + 1 个命令藏在中间。

duckit = **强制压缩 + 萌化**。小鸭子比 senior engineer 好读 10 倍。代码块照旧 byte-exact，你不会丢任何一个 `--no-verify`。

## 贡献

- 改鸭子语气：编辑 `SKILL.md` 的 modes 表 + hard rules
- 加示例：往 `references/examples.md` 塞 source/duck 一对
- PR / issue 来者不拒，鸭子收

## License

MIT — 拿去用，做啥都行。

---

— 一只小鸭 🦆
