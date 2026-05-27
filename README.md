# Kempe Obstruction Theory
## 平面图着色中的 Kempe 障碍传播研究

### Kempe Obstruction Dynamics in Planar Graph Coloring

**版本**：v0.2 | **状态**：预印本（待同行评议） | **更新**：2026年5月27日

> **声明**：本文给出四色定理的一条完整证明路径。核心论证（定理二中各情形的严格排除以及定理三的对称拼接构造）均已在正文中详细展开。欢迎同行评议、形式化验证及任何形式的审查与反馈。

---

## 概述

本仓库提供四色定理的一个非计算机证明方案，基于 Kempe 障碍结构的分析。

核心思路：通过引入**局部四色困难子图（GLFHO）**概念和**对称拼接消解法**，建立证明框架。

This repository presents a proposed non-computer proof of the Four Color Theorem based on the analysis of Kempe obstruction structures. The key idea is the introduction of **Locally Four-Color-Hard Obstruction (GLFHO)** and a **symmetric splicing resolution method**.

---

## 核心成果 / Main Results

### 三定理路径 / Three-Theorem Path

1. **定理一 / Theorem 1**：无三/四边形平面图中至少有两个不相邻的五边形面
   *Any simple planar graph without triangular or quadrilateral faces contains at least two non-adjacent pentagonal faces.*

2. **定理二 / Theorem 2**：极小5-色平面图的任意5-着色中至多存在唯一的 GLFHO
   *In any 5-coloring of a minimal 5-chromatic planar graph, at most one GLFHO can exist (Static Absolute Non-Coexistence).*

3. **定理三 / Theorem 3**：GLFHO 可通过对称拼接在5-度顶点邻域间转移
   *A GLFHO can be transferred between degree-5 vertex neighborhoods via symmetric splicing, yielding a GLFHO-free 4-coloring of G - {v}.*

### 主定理 / Main Theorem

**四色定理**：任意简单平面图均可正常4-着色
*Four Color Theorem: Every simple planar graph is 4-colorable.*

采用对称拼接消解法，将困难结构消除，得到4-着色。
*The proof applies a symmetric splicing resolution method to eliminate the obstruction structure.*

---

## 论文章节

| 章节 | 文件 | 简介 |
|------|------|------|
| 前言与摘要 | [00-frontmatter.md](paper/zh/00-frontmatter.md) | 中英文摘要、引言 |
| 第一节 | [01-concepts.md](paper/zh/01-concepts.md) | 基本概念与定义（平面图、Kempe链、GLFHO） |
| 第二节 | [02-theorem1.md](paper/zh/02-theorem1.md) | 定理一：五边形的存在性 |
| 第三节 | [03-theorem2.md](paper/zh/03-theorem2.md) | 定理二：GLFHO的唯一性（核心定理） |
| 第四节 | [04-theorem3.md](paper/zh/04-theorem3.md) | 定理三：GLFHO的转移性 |
| 第五节 | [05-main-proof.md](paper/zh/05-main-proof.md) | 四色定理的完整证明 |
| 第六节 | [06-comparison.md](paper/zh/06-comparison.md) | 与经典方法的对比 |

---

## 阅读指南

**快速浏览（15分钟）**：阅读下方"核心思想"部分，再查看 `paper/zh/main.md` 的结构概览。

**深入学习（2-3小时）**：从 `paper/zh/main.md` 开始，按顺序阅读 00-frontmatter → 06-comparison，参考 `examples/具体例子.md` 理解直观例子。

**完整研究**：逐章细读所有论文内容，研究 `counterexamples/反例集.md` 中的历史背景，参考 `notes/技术笔记.md` 中的深入讨论。

---

## 核心思想

### 问题的来源：Kempe 的缺陷

Kempe 在 1879 年尝试证明四色定理，但在处理5-度顶点时做了一个错误假设：

> "两条 Kempe 链总是可以安全地进行交换操作"

1890 年，Heawood 指出这个假设不成立——两条 Kempe 链可能形成拓扑缠绕，使得交换操作受阻。

### 本文的方法 / Our Approach

本文通过三个概念处理这个困境：
*This paper addresses the difficulty through three concepts:*

1. **GLFHO（局部四色困难子图）**：精确定义了"Kempe 链缠绕"现象——当两条 Kempe 链被 Jordan 曲线分隔时，它们无法通过简单交换来处理。
   *GLFHO (Locally Four-Color-Hard Obstruction): Precisely defines the "Kempe chain entanglement" phenomenon — when two Kempe chains are separated by a Jordan curve, simple exchange cannot resolve the coloring.*

2. **定理二（GLFHO 的唯一性）**：论证任何极小5-色平面图中最多只有一个 GLFHO。这意味着只需消除这一个困难，整体问题就解决了。
   *Theorem 2 (Uniqueness): At most one GLFHO exists in any 5-coloring of a minimal 5-chromatic planar graph. Eliminating this single obstruction resolves the entire problem.*

3. **定理三（GLFHO 的可转移性）**：通过对称拼接，将 GLFHO 从一个位置消解，不依赖于 Kempe 链交换。
   *Theorem 3 (Transferability): Via symmetric splicing, the GLFHO at one location is resolved without relying on Kempe chain exchanges.*

### 对称拼接消解法 / Symmetric Splicing Resolution

```
第一步：对称拼接  → 将 G 与其副本 G' 沿 v 的边界粘合为 H
Step 1: Splice    → Glue G and its copy G' along v's boundary to form H
        ↓
第二步：着色消解  → G'-侧仅用4色（无GLFHO），对称映射使 G-侧获得无GLFHO的4-着色
Step 2: Resolve   → G'-side uses only 4 colors (no GLFHO); symmetry gives G-side a GLFHO-free 4-coloring
        ↓
第三步：扩展      → 将 G-{v} 的4-着色扩展到整个 G
Step 3: Extend    → Extend the 4-coloring of G-{v} to all of G
```

---

## 与经典方法的对比

| 方面 | Kempe 1879 | Appel-Haken 1976 | 本文 |
|------|-----------|----------------|------|
| 核心工具 | Kempe链 | 不可避免构型 | GLFHO + 对称拼接 |
| 计算机依赖 | 否 | 是 | 否 |
| 穷举规模 | 无 | ~1200个构型 | 无需穷举 |
| 证明长度 | 短（有缺陷） | 极长 | 适中 |
| 主要局限 | 忽视链缠绕 | 依赖计算机 | 定理二严格性待评议 |

---

## 仓库结构

```
kempe-obstruction-theory/
├── paper/
│   ├── zh/                          # 中文论文（完整）
│   │   ├── main.md                  # 论文总索引
│   │   ├── 00-frontmatter.md        # 前言与摘要
│   │   ├── 01-concepts.md           # 基本概念与定义
│   │   ├── 02-theorem1.md           # 定理一
│   │   ├── 03-theorem2.md           # 定理二（核心）
│   │   ├── 04-theorem3.md           # 定理三
│   │   ├── 05-main-proof.md         # 主定理证明
│   │   └── 06-comparison.md         # 经典方法对比
│   └── figures/                     # 图表资源
│
├── examples/
│   └── 具体例子.md                  # Kempe链、GLFHO、拼接等具体例子
│
├── counterexamples/
│   └── 反例集.md                    # Heawood反例、9-17-25节点反例
│
├── notes/
│   └── 技术笔记.md                  # 关键概念速查、常见问题解答
│
├── CITATION.cff                     # 引用信息
├── LICENSE                          # MIT 许可证
└── README.md                        # 本文件
```

---

## 当前状态

- 论文主体完成（中文版）
- 定理一、二、三论证完成
- 主定理（四色定理）证明完成
- 具体例子与反例文档完成
- 英文翻译（待完成）
- 形式化验证（规划中）
- **同行评议（征求中）**

---

## 引用

```bibtex
@unpublished{fangcunshan_kempe_2026,
  title={平面图着色中的 Kempe 障碍传播研究},
  author={方寸山},
  year={2026},
  month={May},
  note={Preprint, under peer review}
}
```

---

## 许可证

本项目采用 MIT 许可证。详见 [LICENSE](LICENSE) 文件。

---

## 联系方式

- **作者**：方寸山(agepeace@163.com)

本证明等待同行评议。如有意见建议，欢迎提出 Issue 或提交 PR。

---

**开始阅读**：[paper/zh/main.md](paper/zh/main.md)
