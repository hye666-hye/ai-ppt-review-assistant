# AI PPT Review Assistant

**自动检查 PPT 与 Word/报告内容是否一致，并生成逐页修改建议。**

这个项目来自一个真实高频场景：PPT 往往从旧版本、开题材料、阶段汇报中复制修改而来，最终交付前容易出现“内容已经在 Word/报告里更新了，但 PPT 还停留在旧版本”的问题。

本项目将这个过程产品化为一个 AI/规则混合的 PPT 内容审查工作流：以 Word、论文终稿、项目报告等材料作为权威依据，对 PPT 逐页进行内容一致性检查，识别旧版本残留、数据冲突、研究路线不一致、术语错误和表达风险，并输出可直接照着修改的 HTML 审查报告。

> 面向 HR 的一句话：这是一个 **AI PPT 内容审查与修改助手**。  
> 面向技术面试官的一句话：这是一个 **source-of-truth driven cross-document consistency review workflow**。

## Demo 截图

![Demo overview](assets/screenshots/demo-contact-sheet.png)

| 页面 | 说明 |
|---|---|
| ![](assets/screenshots/demo-structure-alignment.png) | 结构/结果页：识别被拆碎的结论句、校验标题与内容是否一致 |
| ![](assets/screenshots/demo-conclusion-check.png) | 结论页：检查是否保留旧版本表达、是否需要收敛语气 |
| ![](assets/screenshots/demo-result-consistency.png) | 结果页：核对指标、单位、样品名称和主结论 |
| ![](assets/screenshots/demo-quality-gate.png) | 质量门禁：输出页级风险说明和修改方向 |

## 核心功能

- **读取权威文档**：解析 Word/报告中的标题、章节、关键结论、研究路线和指标。
- **拆解 PPT 页面**：逐页抽取标题、正文、表格、图片说明和结论句。
- **发现不一致**：识别旧版本遗留、开题语言、术语漂移、数据冲突、方法不一致等问题。
- **生成修改建议**：为每页输出“保留 / 修改 / 删除 / 重做”的处理方向。
- **可视化报告**：生成 HTML 报告，方便用户逐页核对和修改。
- **Office 自动化增强**：支持发现 PPT 中一句话被拆成多个文本框的问题，并辅助合并文本框，保留字号/颜色/上下标等格式。

## 典型场景

- 毕业论文终稿 → 答辩 PPT 内容审查
- 项目报告 → 汇报 PPT 内容审查
- 需求文档 → 产品汇报材料审查
- 商业方案 → 路演 PPT 审查
- 课程报告 → 展示 PPT 审查

## 输出样例

查看脱敏样例报告：[`examples/outputs/sample_review_report.html`](examples/outputs/sample_review_report.html)

报告会按页展示：

```text
PPT 页码 → 原内容 → 对应依据 → 问题说明 → 修改方向 → 优先级
```

## 技术栈

- Python
- python-docx
- python-pptx
- OpenXML
- pandas / openpyxl
- HTML / CSS
- Rule-based QA + AI workflow design

## 项目结构

```text
ai-ppt-review-assistant/
├─ index.html                         # 项目级作品集 HTML 首页
├─ README.md                          # 项目说明
├─ docs/
│  ├─ architecture.md                  # 系统架构
│  └─ workflow.md                      # 审查流程
├─ examples/
│  └─ outputs/sample_review_report.html
├─ assets/screenshots/                 # 脱敏截图
└─ src/ai_ppt_review_assistant/         # 示例代码骨架
```

## 简历写法

```text
AI PPT 内容审查与修改助手｜AI 办公自动化项目
- 基于“PPT 与原始报告内容不一致”的高频办公痛点，设计了一套 AI 辅助审查流程，可自动读取 Word/报告和 PPT，逐页发现内容冲突、旧版本残留和表达风险。
- 输出可视化 HTML 审查报告，将每页 PPT 的原文、对应依据、问题说明和修改建议结构化展示，降低人工核对成本。
- 项目支持扩展到毕业答辩、项目汇报、商业方案、投标材料和课程展示等场景。
- 技术栈：Python、python-docx、python-pptx、OpenXML、HTML/CSS、Office 自动化、AI 工作流设计。
```

## 隐私说明

本仓库仅包含脱敏截图、示例报告和代码骨架；不包含真实论文、真实 PPT、学校模板或任何私人文件。
