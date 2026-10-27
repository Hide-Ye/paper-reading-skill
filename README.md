# Paper 辅助阅读 · Paper Reading Assistant

> 根据阅读目的和相关知识基础调整讲解的论文助读 skill。
> A paper-reading skill that adapts explanations to your goal and relevant background.

[中文](#中文) | [English](#english)

## 中文

为了组会分享、项目启发和了解前沿读论文，需要关注的重点不同。这个 skill 帮助 AI 助手围绕你的目标讲解，并用轻量 memory 记住大致知识储备，让后续阅读更有针对性。

### 它怎么工作

1. **直接从需求出发**：复用你已经说过的目标和背景，只补问会影响当前讲解的信息，不进行全面的开场调查。
2. **按需补前置知识**：围绕当前论文，读到需要的概念再补充。阅读目的与知识基础分别判断，适用于不同经验的读者。
3. **按场景调整重点**：组会关注问题、创新和证据；项目关注迁移前提和最小验证；前沿了解关注方法定位与相关工作。
4. **支持详细跟读和分支展开**：逐段跟读时沿原文顺序，术语、推导和实验可以单独展开，结束后回到主线。
5. **依据论文讲解**：核对版本、输入、输出和外部条件，区分原文结论、推断和教学例子，并给出关键证据位置。
6. **保持可纠正的轻量记忆**：例如“接触过 VAE，仍需直观解释”。允许遗忘和纠正，不强制考试，不因旧记录而永久跳过基础。
7. **页面和语音可选**：依宿主能力提供；没有音频工具时只能提供明确标注的口播稿。

### 记忆的范围

memory 用于调整讲解重心，可以独立于你自己的论文笔记数据库存在。它不要求同步个人资料库，也不承担完整学习管理系统的职责。

存储位置由用户配置或宿主可用的持久化能力决定，不固定为某台机器的绝对路径。个人 memory 与分发的 skill 文件分开保存。没有持久化能力时仍可在当前对话中使用，但不能保证跨会话保留；你可以纠正或移除记忆。

### 使用

将本仓库的 `SKILL.md` 放入目标助手支持的 skill 目录，目录名使用 `paper-reading`：

```text
paper-reading/
└── SKILL.md
```

机器标识为 `paper-reading`，中文标题仍为“Paper 辅助阅读”。具体安装位置和启用方式以目标宿主说明为准；本仓库不包含安装器，也未完成各平台兼容性实测。

启用后发送 PDF、链接或 arXiv 编号，例如：

> 我想为组会逐段读这篇论文。会 Python，扩散模型只接触过一点，先从摘要开始，需要的基础边读边补。

### 能力与依赖

- 基础模式需要助手能读取用户提供的论文内容并进行文字讲解。只有摘要时先做摘要层面的工作。
- 从 URL 获取全文、长期记忆、文件写入、交互页面及音频生成由宿主提供，不随本仓库附带。
- 不要求安装名为 canvas 或 voice 的特定 skill；缺少这些能力时继续使用文字或 Markdown。
- 当前更新经过结构校验和有限场景抽查；这不等于多平台、多模型或真实音频生成验证。

## English

Different reading goals call for different emphasis. This skill guides an AI assistant through a paper and uses lightweight memory of the reader's background to tailor future explanations.

### How it works

1. **Start from the request**: Reuse known goals and background. Ask only for information that changes the next explanation.
2. **Introduce prerequisites as needed**: Focus on the current paper rather than collecting a comprehensive profile. Treat reading goals and subject familiarity as separate dimensions.
3. **Adapt the emphasis**: Lab meetings focus on the problem, novelty and evidence; projects on transfer conditions and a minimal validation; field overviews on positioning and related work.
4. **Offer walkthroughs and expandable branches**: Detailed reading follows the paper's order. Explain a concept, derivation or experiment separately, then return to the main thread.
5. **Ground explanations in evidence**: Check versions, inputs, outputs and externally supplied conditions. Distinguish source claims, inference and teaching examples, with locations for key evidence.
6. **Keep memory lightweight and correctable**: For example, “has encountered VAEs but still benefits from intuition.” Allow forgetting and corrections without compulsory tests or permanently skipping a concept.
7. **Make pages and audio optional**: Use host capabilities when available. Without audio generation, provide a clearly labeled narration script.

### Memory scope

Memory helps adjust explanations. It can remain independent of a personal paper-notes database and does not require synchronization or a complete learning-management system.

Use the user's configured storage or an available persistent host facility, keeping personal memory separate from distributed skill files. Without persistence, adaptation still works within the current conversation, but cross-session recall is unavailable. Users can correct or remove remembered information.

### Usage

Place `SKILL.md` in a `paper-reading` folder within the target assistant's supported skill location:

```text
paper-reading/
└── SKILL.md
```

The machine-readable identifier is `paper-reading`; the Chinese title remains “Paper 辅助阅读”. Follow the host's installation and activation instructions. This repository does not include an installer, and compatibility has not been tested across platforms.

Send a paper PDF, URL or arXiv ID, for example:

> Help me read this paper paragraph by paragraph for a lab meeting. I know Python and have only briefly encountered diffusion models. Start with the abstract and introduce prerequisites as needed.

### Capabilities and dependencies

- The basic mode requires access to the supplied paper text and text responses. An abstract alone supports an abstract-level explanation.
- URL retrieval, persistent memory, file writes, interactive pages and audio generation are supplied by the host.
- No specific skill named canvas or voice is required. Text or Markdown remains the fallback.
- This update has structural validation and limited scenario spot checks, not multi-platform, multi-model or real audio-generation verification.
