# xingshi-zhengce-paper

一个面向 AI 代理的《形势与政策》课程论文写作 skill。技能正文是一份按成文顺序排列的中文语料，共 215 条，约 32 KB，不切分、不分类、无二级文件。

## 结构

```
xingshi-zhengce-paper/
├── SKILL.md            # 技能入口：frontmatter（name + description）+ 一句使用说明 + 215 条语料
└── agents/
    └── openai.yaml     # Codex 桌面端界面元数据：显示名、短描述、默认提示词
```

## 安装

### Codex

把本仓库目录放到本地技能根目录，目录名与技能名一致：

```
~/.codex/skills/xingshi-zhengce-paper/SKILL.md
```

Windows 下即 `C:\Users\<用户名>\.codex\skills\xingshi-zhengce-paper\SKILL.md`。放置后新开一个会话即可被识别；想显式调用就写 `$xingshi-zhengce-paper`。

### DSH（DeepSeek Harness）

DSH 扫描的是自己的技能根：`$DSH_HOME`（默认 `~/.dsh`）下的 `skills` 子目录。

```
~/.dsh/skills/xingshi-zhengce-paper/SKILL.md
```

DSH 的 frontmatter 必填项同样是 `name` 与 `description`（本技能已满足），另支持可选字段 `whenToUse`。如果希望隐式触发更稳，可在 frontmatter 里补一行：

```yaml
whenToUse: "写《形势与政策》等思政类课程论文时"
```

该字段不影响 Codex 使用（Codex 侧保持只有 `name` 与 `description` 即可）。

## 使用

触发条件就是 frontmatter 里的那两行：

```yaml
name: xingshi-zhengce-paper
description: "写《形势与政策》课程论文时使用。"
```

写这类课程论文时，技能正文会被整份载入上下文，按需取句、化用或仿写。文中的名句、句式与论述材料均可直接引用或改写。

## 说明

- 语料为公开文章、报刊评论、演讲与典籍中的句子摘录汇编，按成文顺序排列，正文中不带分类标签。
- 摘录句子的著作权归原作者与出版方所有，此处仅作课程写作学习参考，不构成对原文的再授权。
- 技能结构、`agents/openai.yaml` 与文档以 MIT 许可发布（见 `LICENSE`）。
- 仓库内不含任何个人信息或私有数据。
