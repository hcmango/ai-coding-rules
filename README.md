# AI Coding Rules

这是一套我在日常开发里自用的 AI 编程规则和项目模板，适用于 Codex CLI、Claude Code、Antigravity、Cursor 等编码 Agent。

现在的强模型本身已经懂常见的编码规范，在全局文件里堆满“保持代码整洁”“注意解耦”这类泛化要求，既占上下文，也解决不了具体项目里的协作问题。实际用下来，我最后只保留了模型没法自己猜出来的三类文档：多 Agent 怎么分工派活、单个仓库里各目录和文件的联动关系，以及项目已经拍板或否决过的历史决策。

## 文件说明

| 文件 | 解决什么问题 | 放在哪里 |
| :--- | :--- | :--- |
| [DISPATCH.md](DISPATCH.md) | 多 Agent 协作时分工不清、派活后返工、改完不验收 | 放进主 Agent 的全局规则（如 `~/.gemini/GEMINI.md`） |
| [templates/PROJECT_AGENTS.md](templates/PROJECT_AGENTS.md) | 模型不了解当前仓库的目录分工、联动改动、禁改区域和验收方式 | 复制到业务仓库根目录并改名为 `AGENTS.md` |
| [templates/DECISIONS.md](templates/DECISIONS.md) | 新会话不知道之前做过哪些取舍，反复提出已经否决过的方案 | 放到业务仓库的 `docs/DECISIONS.md` |

如果你在同一个项目里同时使用多个工具（比如 Codex 和 Claude Code），把项目规则的正文只维护在根目录的 `AGENTS.md` 里即可。其他工具的入口文件（如 `CLAUDE.md`）只写一行引用，不复制正文，免得改了一处忘了另一处：

```markdown
遵循当前仓库根目录的 `AGENTS.md`，如有冲突，以 `AGENTS.md` 为准。
```

## 相关项目

- [macos-quota-menubar](https://github.com/hcmango/macos-quota-menubar)：一个原生 Swift 编写的 macOS 菜单栏工具，用来查看 Codex、Grok Bot 和 Antigravity CLI 的实时额度，也是我用这套分工和验证方法持续维护的开源项目。

## 关于作者

我是硬核芒果派（hcmango），有 5 年后端开发经验，做过技术负责人，现在用 AI 转全栈做独立产品。平时在下面这些地方分享实际项目的架构拆解、AI 协作方法和开源工具：

- GitHub：[github.com/hcmango](https://github.com/hcmango)
- B 站：[硬核芒果派](https://space.bilibili.com/24226360)
- X：[@hardcoreMG](https://x.com/hardcoreMG)
- 微信公众号：搜索「硬核芒果派」

采用 MIT License 开源，详见 [LICENSE](LICENSE)。
