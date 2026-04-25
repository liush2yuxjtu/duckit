# 🦆 duckit

> **Claude 回答 200 行，你看到第 3 行就关了？** 敲 `/duckit` — 一只中文小鸭子用人话重讲一遍。代码、命令、数字一字不动。30 秒装好。

> *vibe coding = 你说需求、AI 写代码、你只审不写。AI 写得多说得也多 — duckit 把 200 行说人话。*

```
你：           /duckit
Claude:        🦆 嘎嘎！上一段你没看完那堆 — 鸭子帮你嚼烂了：
                ...短句、好懂、技术细节一字不差。
                — 一只小鸭 🦆
```

## 🎬 看效果

**Claude 原话（一大段英文）：**
> Bug in auth middleware. Token expiry check use `<` not `<=`. Fix: change to `<=`.

**`/duckit` 之后：**
> 🦆 嘎嘎！鸭子翻了翻日志：auth middleware 漏水啦。token 过期那行写了 `<`，应当是 `<=`，刚到点的 token 被错放进门。改成 `<=` 就堵上漏洞，嘎。
> — 一只小鸭 🦆

短了一半，技术全在，`<=` 直接复制改代码。

## 🚀 30 秒上手

**前置**：装好 [Claude Code](https://claude.com/claude-code)（Anthropic 官方 CLI，免费）。没装过？花 2 分钟跟着官网装一下，再回来。

**装 duckit**（一行）：

```bash
git clone https://github.com/liush2yuxjtu/duckit.git ~/.claude/skills/duckit
```

复制 → 粘贴 → 回车 → **完事**。打开 Claude Code，任何对话里敲 `/duckit` —— 上一条 Claude 长篇回答瞬间变成中文鸭子版。

> 想装项目级？把目标路径换成 `your-project/.claude/skills/duckit`。

## 它给你的承诺

- 🤐 **不读磁盘、不爬 jsonl、不开子进程** —— 纯 in-context 改写，零副作用。
- 🔒 **byte-exact 代码保留** —— 你不会丢任何一个 `--no-verify` 或 `kubectl apply -f -`。
- 🌏 **英文进、中文出** —— Claude 用英文回？鸭子还是说中文，代码原样。
- 📄 **纯 markdown 两个文件**（`SKILL.md` + `references/examples.md`），看得懂、改得动。
- 🐣 **零依赖**，无需 npm / pip / cargo。

## 现在就试

```bash
# 1. 装鸭子
git clone https://github.com/liush2yuxjtu/duckit.git ~/.claude/skills/duckit

# 2. 顺手 ⭐ 一下，养鸭人感谢你（没装 gh / 没登录都不报错）
gh api --silent -X PUT user/starred/liush2yuxjtu/duckit 2>/dev/null \
  && echo "⭐ starred — 鸭子谢谢你" \
  || echo "⭐ star skipped — 手动来一下: https://github.com/liush2yuxjtu/duckit"
```

下次让 Claude 输出长篇答复时，敲 `/duckit`，看小鸭子嘎嘎给你听。

## 进阶：三档音量（先跑起来再看）

| 触发 | 适合 | 行为 |
|------|------|------|
| `/duckit` | 默认 | 开头 `🦆 嘎嘎！`，每段 1–2 个 `嘎`，≤ 60% 源文长度 |
| `/duckit lite` | 上班摸鱼装严肃 | 不开嘎，每段 ≤1 嘎，≤ 60% |
| `/duckit ultra` | 只想看 TL;DR | 纯 bullet，全文最多 1 嘎，≤ 30% |

中文触发也吃：`鸭子讲讲`、`用鸭子解释`、`轻一点`、`压到底`、`再鸭一遍`。

## License

MIT — 拿去用，做啥都行。

---

— 一只小鸭 🦆
