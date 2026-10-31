# 巴菲特视角 Skill

基于可核查公开资料，提炼商业判断与投资决策框架，不冒充本人，不猜测当前持仓，不保证投资收益。按女娲的六维调研流程构建。

## 安装

需要 Node.js 与 npm/npx，并能访问 npm 和 GitHub。交互式安装：

```powershell
npx skills add zma96669/warren-buffett-skill
```

按提示选择技能 `warren-buffett-perspective` 与你使用的智能体（例如 Codex）；希望跨项目可用时选择 Global/全局范围。不同版本界面可能不同，命令默认项目级。若要明确指定全局 Codex 安装，可用：

```powershell
npx skills add zma96669/warren-buffett-skill --skill warren-buffett-perspective -g -a codex
```

仅查看仓库能识别的技能，不安装：

```powershell
npx skills add zma96669/warren-buffett-skill --list
```

这是通过 `skills` CLI 从公开 GitHub 仓库安装，不是把技能发布成独立 npm 包。不要求配置代理，不使用离线包；能否下载仍取决于你的网络是否能直连相关服务。安装前可检查仓库内容，不需要提供 GitHub token 给这个技能。

## 使用

安装后，在支持技能的智能体中明确说：

> 请用巴菲特视角分析这家公司的生意、护城河和资本配置。先核查最新年报，区分公司好不好和当前价格贵不贵，列出会推翻结论的证据。

> 用巴菲特视角审视这次收购：用增发股份支付，真正的机会成本是什么？

> 解释所有者收益，并指出维持性资本开支无法准确拆分时该怎么办。

只提及人物姓名或普通问股票不自动触发。具体证券分析需要联网核查最新披露；离线时只讨论有日期的材料和框架，不给当前交易结论。技能不执行交易、不申请凭据、不运行下载脚本。

## 内容与边界

- 五个模型：企业所有者、护城河与再投资、能力圈、价值与资本配置、生存与可信资本。
- 八条条件式启发式；保留集中/分散、质量/价格、耐心/纠错等真实张力。
- 六份内部调研、原始来源定位、外部收益解释及普通投资者的复制限制。
- 不把历史成功当因果证明，不给 PE/ROE/安全边际统一阈值，不将保险浮存金当无风险杠杆。
- 历史资料截止 2026-10-31；当前身份和当期股东信必须核对署名，不能自动归于 Buffett。

入口：[SKILL.md](skills/warren-buffett-perspective/SKILL.md)；[来源索引](skills/warren-buffett-perspective/references/sources.md)；[验证记录](VALIDATION.md)；[独立行为检查](FIDELITY.md)。验证只是有限样例的质量检查，不代表投资有效性或真实人格复制。

现有 `buffett-investment` 是另一个技能，本仓库不修改它。安装两者后可能存在功能重叠，可按名称明确调用。

## 来源与归属

优先使用伯克希尔官方股东信、公告和原始访谈，外部研究单独标明。仓库只发布简短转述、分析与定位，不分发受版权保护的完整原文。原始材料的权利仍归原作者/权利人。

依照[女娲 · Skill造人术](https://github.com/alchaincyf/nuwa-skill)流程创建；女娲原作者：[花叔](https://x.com/AlchainHust)。本仓库非巴菲特、伯克希尔或女娲作者的官方认可项目。
