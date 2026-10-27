# Paper 辅助阅读 · Paper Reading Assistant

> 场景驱动的 AI 论文助读 skill：按阅读目的和个人知识库定制讲解
> A scenario-driven AI paper-reading skill tailored to your goal and your knowledge base

[中文](#中文) | [English](#english)

---

## 中文

读论文很累，往往不是因为论文太难，而是阅读方式没对上需求。为了组会分享去读，和为了给项目找灵感去读，要关注的地方完全不一样。这个 skill 让 AI 助手先弄清楚你**为什么读**，再决定**怎么带你读**。

### 它怎么工作

1. **先了解你**：第一次使用时，系统地了解你的学历、专业、研究方向、做过的项目和熟悉的工具，建立个人知识档案。
2. **问清阅读场景**：每次发来论文，先问这次为了什么读（组会分享 / 项目前置启发 / 专业前沿了解 / 课程作业 / 其他），要不要详细跟读，要文字版还是语音版。
3. **按场景换方案**
   - **组会分享**：以论文的创新点为主线，结合你的研究方向做引导式讲解，先提问让你自己想，再揭晓作者的做法；最后给出分享大纲、可能被问到的问题和论文的局限。
   - **项目启发**：侧重哪些方法可以迁移到你的项目、需要满足什么前提，以及数据和代码怎么复现。
   - **前沿了解**：侧重这篇论文在领域发展脉络中的位置和趋势，少讲细节，并推荐延伸阅读。
4. **树状讲解**：主线按作者思路往下讲，每个节点下挂可以展开的知识点分支（🌱 前置知识 / 🔍 细节推导 / 🧪 实验数据）；你已经会的直接跳过，想深入就说「展开 X」。
5. **可选详细跟读**：按原文章节逐段讲，每讲完一节停下来回答疑问。
6. **语音版**：把主线改成口语，分成每段 3 到 5 分钟的音频，适合健身或通勤时听。
7. **知识库持续积累**：每读完一篇，学会的知识点记进知识库，没懂的记成待学；读得越多，讲解越贴合你的水平。

### 适合谁

经常要读论文的本科生和研究生，尤其是觉得 AI 辅助读论文仍然很累、想要更有针对性讲解的人。

### 怎么用

把 `SKILL.md` 添加到支持 skill 的 AI 助手里（例如 Grok Bot），然后发送论文的 PDF、链接或 arXiv 编号即可。

---

## English

Reading papers is exhausting, often not because the paper is hard, but because the reading approach doesn't match your goal. Reading for a lab-meeting presentation and reading for project inspiration call for completely different focus. This skill makes the AI assistant first figure out **why you're reading**, then decide **how to guide you**.

### How it works

1. **Get to know you**: On first use, it builds a profile of your education, major, research direction, past projects, and familiar tools.
2. **Ask the reading scenario**: For each paper, it asks why you're reading (lab-meeting presentation / project inspiration / keeping up with the field / coursework / other), whether you want a detailed walkthrough, and whether you want text, audio, or both.
3. **Switch plans by scenario**
   - **Lab meeting**: Centered on the paper's novelty. Guided explanation tied to your research direction: it asks you to think first, then reveals the authors' approach. Ends with a talk outline, likely questions, and the paper's limitations.
   - **Project inspiration**: Focuses on which methods transfer to your project, under what conditions, and how to reproduce the data and code.
   - **Frontier overview**: Places the paper in the field's timeline and trends, light on details, with further-reading suggestions.
4. **Tree-structured explanation**: The main line follows the authors' reasoning; each node has expandable branches (🌱 prerequisites / 🔍 details & derivations / 🧪 experiments & data). Concepts you already know are skipped; say "expand X" to dig deeper.
5. **Optional detailed walkthrough**: Section-by-section reading, pausing after each section for questions.
6. **Audio version**: The main line rewritten in spoken style, split into 3–5 minute segments for the gym or commute.
7. **Growing knowledge base**: After each paper, concepts you've mastered are added to your knowledge base and gaps are logged as to-learn; the more you read, the better the explanations fit you.

### Who it's for

Undergraduate and graduate students who read papers often, especially those who still find AI-assisted reading tiring and want more targeted guidance.

### Usage

Add `SKILL.md` to an AI assistant that supports skills (e.g., Grok Bot), then send a paper's PDF, link, or arXiv ID.
