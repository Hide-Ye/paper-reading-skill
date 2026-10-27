# Paper 辅助阅读 · Paper Reading Assistant

> 根据阅读目的和相关知识基础调整讲解的论文助读 skill。
> A paper-reading skill that adapts explanations to your goal and relevant background.

[中文](#中文) | [English](#english) | [Codex 安装](#在-codex-中安装与调用) | [⬇ 下载 / Download ZIP](https://github.com/Hide-Ye/paper-reading-skill/archive/refs/heads/main.zip)

## 中文

为了组会分享、项目启发和了解前沿读论文，需要关注的重点不同。这个 skill 帮助 AI 助手围绕你的目标讲解，并用轻量 memory 记住大致知识储备，让后续阅读更有针对性。

### 快速下载与使用

**[下载 ZIP（main 分支）](https://github.com/Hide-Ye/paper-reading-skill/archive/refs/heads/main.zip)** · [单独查看 SKILL.md](https://github.com/Hide-Ye/paper-reading-skill/blob/main/SKILL.md)

1. **下载并解压**：点击上面的 ZIP 链接，无需安装 Git。也可以在仓库首页选择 **Code → Download ZIP**。
2. **安装到助手**：在目标助手支持的 skill 目录中新建 `paper-reading` 文件夹，将解压得到的 `SKILL.md` 放进去。具体目录及重新加载方式以该助手的说明为准。
3. **开始阅读**：确认助手已加载 `paper-reading`，然后发送论文和阅读目的。例如：

> 请使用 paper-reading 帮我为组会逐段读这篇论文。我会 Python，扩散模型只接触过一点，先从摘要开始，需要的基础边读边补。

安装后的结构：

```text
<助手的 skill 目录>/
└── paper-reading/
    └── SKILL.md
```

**熟悉 Git 的用户**也可以下载到当前目录，然后按第 2 步安装：

```bash
git clone https://github.com/Hide-Ye/paper-reading-skill.git paper-reading
```

下载本身不会自动让助手加载 skill。本项目提供指令文件，不是独立应用；助手需要支持加载自定义 skill。机器标识为 `paper-reading`，中文标题仍为“Paper 辅助阅读”。

下载链接指向 `main` 的最新内容，尚未合并的 PR 不包含在内。本仓库不包含通用安装器，也未完成各平台兼容性实测。

### 在 Codex 中安装与调用

当前仓库提供独立 skill。推荐在 Codex **聊天输入框**粘贴下面的指令，由内置安装器处理：

```text
$skill-installer 请从 GitHub 仓库 https://github.com/Hide-Ye/paper-reading-skill 安装论文阅读 skill。
使用 main 分支，skill 位于仓库根目录（路径 .），安装目录名为 paper-reading。
安装前检查是否已有同名 skill；如果存在，先说明差异，不直接覆盖。
完成后告诉我实际安装位置及是否已被 Codex 识别。
```

安装后，在下一轮发送：

```text
$paper-reading 请辅助我逐段阅读这篇论文：[论文链接或 PDF]。
我的阅读目的是组会分享，必要的前置知识边读边补，先从摘要开始。
```

如果安装后没有出现，重启 Codex 再试。以上是发给 Codex 的消息，不是终端命令。

**手动安装备选**：将下载的 `SKILL.md` 放到用户目录下的 `~/.agents/skills/paper-reading/SKILL.md`；Windows 对应 `%USERPROFILE%\.agents\skills\paper-reading\SKILL.md`。仅供当前仓库使用时，可放到仓库内的 `.agents/skills/paper-reading/SKILL.md`。选择一种安装位置，避免重复安装。

此处安装的是 skill，尚未打包或发布为插件市场中的 plugin。安装与发现方式依据 [OpenAI 官方 Skills 文档](https://learn.chatgpt.com/docs/build-skills)；安装器的实际目标目录以执行结果为准。本项目尚未进行完整安装实测。

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

### 能力与依赖

- 基础模式需要助手能读取用户提供的论文内容并进行文字讲解。只有摘要时先做摘要层面的工作。
- 从 URL 获取全文、长期记忆、文件写入、交互页面及音频生成由宿主提供，不随本仓库附带。
- 不要求安装名为 canvas 或 voice 的特定 skill；缺少这些能力时继续使用文字或 Markdown。
- 当前更新经过结构校验和有限场景抽查；这不等于多平台、多模型或真实音频生成验证。

## English

Different reading goals call for different emphasis. This skill guides an AI assistant through a paper and uses lightweight memory of the reader's background to tailor future explanations.

### Quick download and start

**[Download ZIP (main branch)](https://github.com/Hide-Ye/paper-reading-skill/archive/refs/heads/main.zip)** · [View SKILL.md](https://github.com/Hide-Ye/paper-reading-skill/blob/main/SKILL.md)

1. **Download and extract**: Use the ZIP link above; Git is not required. You can also choose **Code → Download ZIP** on the repository homepage.
2. **Install in your assistant**: Create a `paper-reading` folder in the assistant's supported skill directory and copy the extracted `SKILL.md` into it. Follow the host's instructions for the location and reloading.
3. **Start reading**: Confirm that the assistant has loaded `paper-reading`, then send your paper and reading goal. For example:

> Use paper-reading to help me read this paper paragraph by paragraph for a lab meeting. I know Python and have only briefly encountered diffusion models. Start with the abstract and introduce prerequisites as needed.

Installed layout:

```text
<assistant skill directory>/
└── paper-reading/
    └── SKILL.md
```

**If you use Git**, download into your current directory with the following command, then follow step 2:

```bash
git clone https://github.com/Hide-Ye/paper-reading-skill.git paper-reading
```

Downloading does not automatically load the skill. This project supplies instructions, not a standalone application; your assistant must support custom skills. The identifier is `paper-reading`; the Chinese title remains “Paper 辅助阅读”.

The download tracks the latest `main` contents and excludes unmerged PRs. This repository does not include a universal installer, and compatibility has not been tested across platforms.

### Install and invoke in Codex

This repository currently supplies a standalone skill. Paste this into the Codex **chat input**:

```text
$skill-installer Install the paper-reading skill from https://github.com/Hide-Ye/paper-reading-skill.
Use branch main, skill path . (repository root), and installation folder name paper-reading.
If the skill already exists, explain the differences before overwriting.
Report the installed location and whether Codex recognizes it.
```

On the next turn, use:

```text
$paper-reading Walk me through this paper paragraph by paragraph: [paper URL or PDF].
I am preparing a lab meeting. Introduce prerequisites as needed and start with the abstract.
```

Restart Codex if the installed skill does not appear. These are chat messages, not terminal commands.

**Manual alternative**: place `SKILL.md` at `~/.agents/skills/paper-reading/SKILL.md` (Windows: `%USERPROFILE%\.agents\skills\paper-reading\SKILL.md`). For repository-only use, choose `.agents/skills/paper-reading/SKILL.md` inside the repository instead. Choose one location to avoid duplicates.

This installs a skill, not a published marketplace plugin. See the [official OpenAI Skills documentation](https://learn.chatgpt.com/docs/build-skills). The installer reports its actual destination; this project has not completed an end-to-end installation test.

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

### Capabilities and dependencies

- The basic mode requires access to the supplied paper text and text responses. An abstract alone supports an abstract-level explanation.
- URL retrieval, persistent memory, file writes, interactive pages and audio generation are supplied by the host.
- No specific skill named canvas or voice is required. Text or Markdown remains the fallback.
- This update has structural validation and limited scenario spot checks, not multi-platform, multi-model or real audio-generation verification.
