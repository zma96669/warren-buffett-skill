# 验证记录

日期：2026-10-31。对象：`skills/warren-buffett-perspective/`。这是技能包工程检查与有限行为样例检查，不是投资绩效、适当性或人格保真的证明。

## 已完成的本地检查

| 检查 | 实际结果与限制 |
|---|---|
| 技能结构 | `skill-creator/scripts/quick_validate.py` 返回 `Skill is valid!`；检查 frontmatter、名称等，不能证明投资判断正确 |
| 安装器识别 | `npx --yes skills add ./outputs/warren-buffett-skill --list` 成功，仅识别一个技能 `warren-buffett-perspective`，未执行全局安装 |
| CLI/运行时 | 本次 CLI `skills` 1.7.4，Node.js v26.12.1，npm/npx 11.20.0，Windows PowerShell；其他版本/平台未实测 |
| 研究自包含 | 六个维度研究均位于技能内部；不依赖原有本地 Buffett 笔记、书籍文件或其他技能 |
| 来源结构 | 来源索引去重 26 个 URL：22 个伯克希尔原始页面/文件、2 个 CNBC 原始年会页面、1 个 SEC 申报、1 个 AQR 官方研究摘要 |
| 独立试答 | 不同于编写者的试答智能体只读实际技能及包内材料，离线回答五题；另由独立评分智能体评估，见 [FIDELITY.md](FIDELITY.md) |
| 独立作者审查 | 检查可运行性、事实归属和边界；发现并修正索引把 8-K 事件日写成同日文件的措辞，明确事件日 2018-07-17、签署日 2018-07-19 |
| 原技能隔离 | 未修改或覆盖原有 `buffett-investment`；新技能使用不同名称 |

来源精确计数：26 个去重 URL 中，**22 个伯克希尔原始页面/文件 + 2 个 CNBC 原始年会页面 + 1 个 SEC 申报 + 1 个 AQR 官方研究摘要**。同一信件出现在多个研究维度不算多份独立来源；公司公告和年报也不是独立于管理层的第三方鉴证。

本次评分针对三个已知立场题、一个超范围/时效题、一个自拟商店算例；测试题与实际回答摘要保存于评分报告。未测真实资金交易、复杂金融企业估值、所有模型/长对话组合，未做盲法风格实验或跨模型统计。不得把内部得分解读成真实人物认可。

## 来源核验的保留意见

- 历史信件为有界选读；未知的首次公开日不以落款补造。2007/2018 材料的发布日另有公司公告佐证。
- 年会章节点已核，但未做完整音轨逐句听校，时间戳未核。
- AQR 官方摘要已读，论文全文访问受限，未声称复核回归表或显著性。
- 2026-09-18 主席交接公告与 2025 年报原文件另作交叉读取；当期 CEO 信不能自动算作 Buffett 本人的信。
- 某些官网/SEC 端点会因请求环境返回访问限制；不能把一次可访问等同永久有效。未来使用必须重新核查当前事实。

## 发布验证

公开仓库：[zma96669/warren-buffett-skill](https://github.com/zma96669/warren-buffett-skill)。2026-10-31 首次发布后实际检查：

- 匿名 GitHub API 返回 HTTP 200，仓库 `private=false`。本地与远端 main 在发布内容提交 `0e5b884c7212045181c850b45c764c19542d7289` 一致；后续仅补记本报告。
- `npx --yes skills add zma96669/warren-buffett-skill --list` 从 GitHub 克隆成功，发现且仅发现 `warren-buffett-perspective`。
- 在隔离临时项目运行 `npx --yes skills add zma96669/warren-buffett-skill --skill warren-buffett-perspective -a codex --copy -y`，返回 `Installed 1 skill`。这不是全局安装，没有覆盖原有技能。
- 下载后的 8 个技能文件全部齐全；Windows Git 将 LF 转为 CRLF，标准化换行后逐文件内容完全一致。首次逐字节比较因换行不同未通过，未将其冒充原样相等。
- 匿名 Contents API 解码后的入口 SHA256 与本地一致：`89360c5d898a28dfcd1226dff21cecea874e1b384ccda08c81b5c097391360e4`。
- 单独请求 raw.githubusercontent.com 一次超时，改用匿名 GitHub Contents API 核对；Git 克隆及真实安装均已成功，但这不保证任何网络环境永久可下载。
- Markdown 本地链接、自包含、占位符及明显凭据/本机路径扫描通过；`git diff --cached --check` 通过。静态模式扫描不是完整安全审计。

不修改代理设置，不使用离线分发包，不上传 token、私钥、本机用户路径或临时测试目录。
