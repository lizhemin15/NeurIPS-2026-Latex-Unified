# NeurIPS 2026 LaTeX — Unified Author-Friendly Template

Easier-to-use NeurIPS 2026 LaTeX layout — hope your paper gets **ACCEPT** ✨

**Repository:** [https://github.com/lizhemin15/NeurIPS-2026-Latex-Unified](https://github.com/lizhemin15/NeurIPS-2026-Latex-Unified) · [Issues](https://github.com/lizhemin15/NeurIPS-2026-Latex-Unified/issues)

```bash
git clone https://github.com/lizhemin15/NeurIPS-2026-Latex-Unified.git
```

[English](#english) · [中文](#中文) · [日本語](#日本語)

> **Disclaimer.** This repository is **not** affiliated with NeurIPS. The authoritative source remains [neurips.cc](https://neurips.cc) and the official ZIP ([Formatting Instructions for NeurIPS 2026](https://media.neurips.cc/Conferences/NeurIPS2026/Formatting_Instructions_For_NeurIPS_2026.zip)). Deadlines, policies, and style rules can change—always verify against the official call for papers and handbook before submission.

---

## English

### What this is

A **NeurIPS 2026–compatible** LaTeX layout based on the official `neurips_2026.sty`, reorganized so authors spend less time navigating a single giant instruction file and more time writing. **Visual output and geometry are intended to match the official template** when you do not violate the rules (no extra geometry/font hacks).

### Quick start

| File | Role |
|------|------|
| **`main.tex`** | **Your paper** — title, authors, body, references, checklist. |
| **`references.bib`** | Bibliography (works with `natbib` + BibTeX). |
| **`checklist.tex`** | Required NeurIPS checklist (do not remove). |
| **`neurips2026_formatting_instructions.tex`** | Long formatting guide (compile for the official-style instruction PDF). |
| **`neurips_2026.sty`** | Official class/style implementation — **do not edit** for submission. |

Compile `main.tex` with `pdflatex` + `bibtex` + `pdflatex` ×2 (or `latexmk`). CI builds `main.tex` and the formatting guide on push/PR.

### Improvements over the stock official ZIP (this repo)

- **Clear manuscript entry point:** `main.tex` is obviously “the paper”; the official bundle often mixes the full instruction document with your draft in one long `neurips_2026.tex`.
- **Renamed instruction source:** `neurips2026_formatting_instructions.tex` avoids confusion with `neurips_2026.sty` / `\usepackage{neurips_2026}`.
- **Bilingual (Chinese + English) comments** placed **next to the relevant code** (preamble, options, references, checklist, etc.), summarizing CfP / handbook points—not one huge block at the top.
- **Explicit “AUTHOR PACKAGE ZONE”** in `main.tex`: where to add extra `\usepackage{...}`, plus **forbidden / discouraged** packages and commands that risk desk rejection or PDF font issues (geometry, fullpage, raw `$$`, etc.).
- **Modern bibliography path:** sample `references.bib` + `plainnat` instead of hand-typed reference lists only.
- **Small correctness fixes:** e.g. funding disclosure URL aligned with the current NeurIPS guide path; checklist macro consistency.
- **`.sty` quality-of-life:** warning if a workshop track is selected without `\workshoptitle{...}`.
- **GitHub Actions:** LaTeX build smoke test on push/PR; pushing tag `v*` creates a Release with both PDFs and a tracked-source ZIP (`git archive`).

### Tooling note

Repository structure, comments, and several fixes were iterated with **[Cursor](https://cursor.com)** (AI-assisted editing). Human maintainers remain responsible for correctness; **if something disagrees with the official NeurIPS materials, trust NeurIPS.**

### Contributing & bugs

**Issues are welcome.** Open an [issue](https://github.com/lizhemin15/NeurIPS-2026-Latex-Unified/issues) for bugs, outdated policy links, or compatibility problems (TeX distribution, package versions). PRs are welcome if they preserve official formatting compliance.

---

## 中文

**仓库：** [https://github.com/lizhemin15/NeurIPS-2026-Latex-Unified](https://github.com/lizhemin15/NeurIPS-2026-Latex-Unified) · [提 Issue](https://github.com/lizhemin15/NeurIPS-2026-Latex-Unified/issues)

### 这是什么

在 **官方 `neurips_2026.sty`** 基础上整理的 NeurIPS 2026 论文稿结构：**版式与官方模板一致**（在遵守规则、不乱改版心字号的前提下）。目标是把「写稿」和「读长篇说明」分开，减少新手在单文件里翻几百行说明的困扰。

### 快速对照

| 文件 | 作用 |
|------|------|
| **`main.tex`** | **正文入口**：题目、作者、章节、文献、清单。 |
| **`references.bib`** | 参考文献数据库（配合 natbib + BibTeX）。 |
| **`checklist.tex`** | 官方强制清单，勿删。 |
| **`neurips2026_formatting_instructions.tex`** | 完整排版说明（编译后相当于官方那种说明 PDF）。 |
| **`neurips_2026.sty`** | 官方样式实现，**不要改**。 |

### 相对官方 ZIP 的改进与优化

- **主文件一眼可辨：** 用 `main.tex` 专门写论文；官方压缩包常把说明与示例正文塞在同一个很长的 `neurips_2026.tex` 里。
- **说明文件命名更清晰：** `neurips2026_formatting_instructions.tex` 与 `neurips_2026.sty`、`\usepackage{neurips_2026}` 不易混淆。
- **中英对照注释分散在对应位置**（导言区、选项、参考文献、清单等），概括官网 CfP / Handbook 要点，而不是全部堆在文件最前面。
- **`main.tex` 内划定「作者加包区」**：只在那里加额外宏包，并列出**禁止 / 不推荐**的包与命令（如 geometry、fullpage、裸 `$$` 等），降低误触版式被 desk reject 的概率。
- **Bibliography 工作流：** 提供 `references.bib` 与 `plainnat` 示例，减少手写文献列表。
- **细节修正：** 如资金披露链接与当前官网路径一致；checklist 中宏使用统一等。
- **`.sty` 体验：** Workshop 轨道若未设置 `\workshoptitle` 会给出警告。
- **GitHub Actions：** push/PR 上编译冒烟；推送 `v*` 标签会发布 Release，附带两份 PDF 与 `git archive` 源码压缩包。

### 关于 Cursor

本仓库的目录组织、注释体系与部分修补是在 **[Cursor](https://cursor.com)** 辅助下迭代完成的。若与 NeurIPS 官网或官方 ZIP **有任何冲突，以官方为准**。

### 反馈与抓虫

**欢迎在 [Issues](https://github.com/lizhemin15/NeurIPS-2026-Latex-Unified/issues) 反馈**：错链、与新版政策不一致、某 TeX 发行版编译失败等。也欢迎 PR，前提是**不改变官方规定的版式与合规要求**。

**小龙虾在线随时准备改 bug** —— 开个 issue，我们尽量尽快修。

---

## 日本語

**リポジトリ:** [https://github.com/lizhemin15/NeurIPS-2026-Latex-Unified](https://github.com/lizhemin15/NeurIPS-2026-Latex-Unified) · [Issues](https://github.com/lizhemin15/NeurIPS-2026-Latex-Unified/issues)

このリポジトリは NeurIPS 2026 公式の `neurips_2026.sty` に準拠した LaTeX テンプレートを、**執筆用 `main.tex` と説明用ソースを分離**し、**日中英の注意コメント**や**追加パッケージ用ゾーン**を設けるなど、作者向けに整理したものです。**最終的な規則・締切は必ず [neurips.cc](https://neurips.cc) で確認してください。** 構成の一部は [Cursor](https://cursor.com) を用いた編集で整備されています。不具合やリンク切れは上記 Issues からお知らせください。

---

## License

The NeurIPS style files follow the license terms distributed by NeurIPS. Other additions in this repository (comments, `main.tex` layout, CI, README) are provided as-is for the community; add a `LICENSE` file if you need a specific open-source license for your fork.
