# Codex App Explain Skill 中文说明

这是一个面向 `Codex App` 的公开教学 skill，用于分层讲解与重新讲解：
概念解释、推导拆解、slide 或 PDF 段落说明，以及有限范围内的作业步骤讲解。

## 仓库交付物

- 可安装 skill：
  [codex-app-explain](./codex-app-explain)
- 配套引用文件：
  教学原则、source binding、route adaptation
- 根目录文档：
  安装方式、范围说明、隐私边界

## 安装 / 使用

- `Codex App`：从本仓库路径 `codex-app-explain` 安装
- GitHub 路径安装示例：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo <owner>/codex-app-explain-skill \
  --path codex-app-explain \
  --dest /tmp/codex-skill-install-test
```

安装后重启 `Codex App`，让新 skill 被发现。

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
- 不使用任何绝对本地路径。
- 所有示例都保持通用，不绑定课程、机构或个人身份。

## 仓库结构

- `codex-app-explain/`：可安装的 `Codex App` skill
- `codex-app-explain/references/`：公开引用文件
- `CHANGELOG.md`：版本记录
- `LICENSE`：`MIT`

英文：

- [README.md](./README.md)
