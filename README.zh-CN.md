# Codex App Explain Skill 中文说明

这是一个面向 `Codex App` 的公开教学 skill，用于分层讲解与重新讲解：
概念解释、推导拆解、slide 或 PDF 段落说明，以及有限范围内的作业步骤讲解。

这个公开仓库现在还明确公开了稳定的模式拆分：

- `short-concept mode`：单个概念或单个局部卡点
- `prerequisite-chain mode`：隐藏前置概念链
- `paper-sentence mode`：显式逐句 / 逐段读 paper
- `full-layered mode`：完整重建与推导

在 `paper-sentence mode` 里，如果原文引用块含有 OCR 噪声或很差的
ASCII 风格符号，本 skill 允许做最小的 Unicode 可读性清理。这个清理
只修显示，不改原句含义，不把原文改写成 paraphrase 或 explanation。

## 仓库交付物

- 可安装 skill：
  [codex-app-explain](./codex-app-explain)
- 配套引用文件：
  教学原则、source binding、route adaptation、mode split
- 根目录文档：
  安装方式、范围说明、隐私边界

## 安装 / 使用

- `Codex App`：从本仓库路径 `codex-app-explain` 安装
- GitHub 安装目标：
  - repo：`<owner>/codex-app-explain-skill`
  - path：`codex-app-explain`
- 安装后重启 `Codex App`，让新 skill 被发现。

## 触发示例

- `Explain this definition step by step.`
- `Where does this derivation step come from?`
- `Teach me this equation from basic to rigorous.`

## 非触发示例

- `Remember my formatting preference.`
- `Find this file for me.`
- `Write the full assignment for me.`

## 隐私边界

这个公开版 skill 保持通用、可复用。

- 不包含个人 memory 文件、本地 profile 数据或私有 companion workflow。
- 公开源码中不内置任何个人绝对路径。
- 所有示例都保持通用，不绑定课程、机构或个人身份。

## Companion Boundary

这个仓库负责的是 teaching workflow 这一半。

- 它负责 route selection、source binding、前置概念处理，以及何时停下。
- 它不负责持久化的个人 memory，也不负责用户私有格式偏好。
- 如果宿主环境还有单独的 output-rules skill，那么 notation 和 layout
  应由那个 companion 负责；本 skill 继续只负责教学路线。
- 逐句读 paper 里的原文引用可读性清理，属于这里的阅读 workflow 行为；
  如果还有单独的 rendering-rules companion，它可以发布更窄的符号清理
  子集来保持显示一致。

## 仓库结构

- `codex-app-explain/`：可安装的 `Codex App` skill
- `codex-app-explain/references/`：公开引用文件
- `CHANGELOG.md`：版本记录
- `LICENSE`：`MIT`

英文：

- [README.md](./README.md)
