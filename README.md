<p align="right">
  <a href="./README.md"><kbd>中文</kbd></a>
  <a href="./README.en.md"><kbd>English</kbd></a>
</p>

# 研究底稿工作流（Research Dossier Workflow）

这是一个 Codex Skill，用于把行业主题、文章、市场问题、政策议题、公司组合、投资主题或战略问题，转化为两类配套产出：

1. **可复核研究底稿**：保留问题树、证据、来源、缺口、反证和行动边界。
2. **研究报告初稿**：基于底稿生成可阅读的报告草稿，同时保留不确定性和待验证事项。

这个 Skill 适合需要“观点可追溯、证据可复核、结论不过度延伸”的研究场景。

## 它会产出什么

默认情况下，Skill 会同时产出两部分：

- **研究底稿**：决策问题、研究问题、证据缺口表、来源台账、结构化摘录、洞察候选、行动边界、下一步核验。
- **研究报告初稿**：标题与范围、执行摘要、背景、基于证据的分析、洞察框、风险与限制、建议或下一步、来源列表。

## 安装方式

使用 Codex Skill 安装器：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo smilelida/research-dossier-workflow \
  --path skills/research-dossier-workflow
```

安装后重启 Codex，让新 Skill 自动加载。

手动安装：

```bash
git clone https://github.com/smilelida/research-dossier-workflow.git
mkdir -p ~/.codex/skills
cp -R research-dossier-workflow/skills/research-dossier-workflow ~/.codex/skills/
```

## 使用示例

```text
Use $research-dossier-workflow.

Topic: [研究主题]
Audience: [谁会阅读或使用]
Decision: [读完后需要做什么决策]
Time horizon: [现在/90 天/1 年/3-5 年]
Known materials: [链接、文件、笔记、访谈或其他材料]
Privacy level: [public/internal/confidential]

Produce both:
1. a research dossier with research questions, evidence gaps, source ledger, structured extraction, insight candidates with counter-evidence, action boundary, and next verification steps;
2. a research report draft with executive summary, context, evidence-backed analysis, risks, next steps, and sources.
```

简短写法：

```text
Use $research-dossier-workflow to turn [topic] into a source-backed dossier and research report draft.
```

## 隐私与公开发布边界

这个公开版本不包含私有工作流细节、敏感主体标识、本机绝对路径、凭证、密钥、隐藏记忆或工作区专属假设。

Skill 本身也要求模型在生成公开材料前，移除私人姓名、内部项目名、本地路径、账号信息、凭证、敏感对象细节和敏感示例。

## 仓库结构

```text
.
├── README.md
├── README.en.md
├── LICENSE
└── skills/
    └── research-dossier-workflow/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

## License

MIT
