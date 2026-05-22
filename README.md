# cven-skills

一个可公开分发的 Agent Skills 仓库，采用通用的 `skills/<skill-name>/` 目录结构，方便被 Codex、CC Switch 和其他兼容 `SKILL.md` 的工具识别。

## 仓库结构

```text
cven-skills/
├── README.md
├── LICENSE
└── skills/
    └── fable-concept-explainer/
        ├── SKILL.md
        ├── LICENSE.txt
        └── agents/
            └── openai.yaml
```

## 当前包含的技能

### `fable-concept-explainer`

把抽象概念写成寓言故事，再补充概念解析、故事元素映射和两个检验问题。适合解释心理学、哲学、商业、学习方法等不容易直接讲清楚的概念。

## 安装方式

### 1. 在 Codex 中通过技能安装器安装

如果你的环境支持 `$skill-installer`，可以直接安装单个技能目录：

```text
$skill-installer install https://github.com/hf7751/cven-skills/tree/main/skills/fable-concept-explainer
```

安装后重启 Codex，使新技能被重新发现。

### 2. 在 CC Switch 中添加整个仓库

在 CC Switch 的 Skills 仓库管理里添加：

- Owner: `<your-github-name>`
- Owner: `hf7751`
- Name: `cven-skills`
- Branch: `main`
- Subdirectory: `skills`

这样 CC Switch 会扫描 `skills/` 目录下的所有技能，并允许按需安装。

### 3. 手动安装到 Codex

把某个技能目录复制到本地：

```text
~/.codex/skills/
```

例如：

```text
~/.codex/skills/fable-concept-explainer
```

## 使用示例

```text
使用 $fable-concept-explainer 解释“机会成本”
```

```text
请用寓言方式讲清楚“幸存者偏差”
```

## 兼容约定

- 每个技能目录都包含必需的 `SKILL.md`
- 可选 UI 元数据放在 `agents/openai.yaml`
- 技能目录可以独立复制、独立安装
- 仓库根目录使用 `skills/` 作为统一收纳位置，便于工具批量扫描
