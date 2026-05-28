---
title: 平面图着色中的 Kempe 障碍传播研究
subtitle: 两定理路径的四色定理完整证明
title_en: Kempe Obstruction Dynamics in Planar Graph Coloring
subtitle_en: A Complete Proof of the Four Color Theorem via Two-Theorem Path
author: 方寸山
version: v0.3
date: 2026-05-28
---

## 摘要 / Abstract

### 【中文摘要】

本文沿"两定理路径"给出四色定理的完整证明。以 Kempe 链与局部四色困难子图（GLFHO）为核心工具，依次建立两条支柱性定理：

- **定理一**（唯一性定理）利用 Jordan 曲线与颜色分隔引理，证明极小5-色平面图的任意5-着色中至多存在唯一的 GLFHO；
- **定理二** 证明 GLFHO 可通过对称拼接操作在5-度顶点邻域间转移。

在此基础上，主证明对极小5-色平面图施行**对称拼接消解法**：

将含唯一 GLFHO 的图 G(n) 与其副本对称拼接，由4-着色论证保证原侧 u 邻域无 GLFHO，从而得到 G - {v} 的纯4-着色。对称拼接的关键设计在于将问题从5-着色框架（Kempe 链可能受 GLFHO 缠绕阻塞）转入纯4-着色框架；在4-着色环境中，构成 GLFHO Jordan 屏障所必需的第5种颜色不存在，Kempe 链交换必然可行，故 G - {v} 的4-着色可标准地扩展至整个 G，导出与 χ(G)=5 的矛盾，完成证明。

**关键词：** 四色定理；平面图着色；Kempe 链；局部四色困难子图（GLFHO）；极小5-色图；图论

---

### 【Abstract】

This paper presents a complete proof of the Four Color Theorem via a "two-theorem path." Using Kempe chains and Locally Four-Color-Hard Obstructions (GLFHO) as core tools, two pillar theorems are established: 

- **Theorem 1** (Uniqueness Theorem) uses the Jordan Curve Theorem and a color-separation lemma to prove that at most one GLFHO can exist in any 5-coloring of a minimal 5-chromatic planar graph;

- **Theorem 2** proves that a GLFHO can be transferred between 5-degree vertex neighborhoods via a symmetric splicing operation.

The main proof applies a **symmetric splicing resolution method** to a minimal 5-chromatic planar graph: the graph G(n) containing a unique GLFHO at vertex u is symmetrically spliced with its copy; the 4-coloring argument then guarantees that the original side's u-neighborhood becomes GLFHO-free, yielding a pure 4-coloring of G - {v}. The key design of symmetric splicing is to shift the problem from a 5-coloring framework — where Kempe chains may be blocked by GLFHO entanglement — into a pure 4-coloring framework; in the 4-coloring environment, the fifth color essential for forming a GLFHO Jordan barrier is absent, so Kempe chain exchanges are guaranteed to succeed, and the 4-coloring of G - {v} extends to all of G by standard methods, contradicting χ(G) = 5 and completing the proof.

**Keywords:** Four Color Theorem; planar graph coloring; Kempe chains; locally four-color-hard obstruction (GLFHO); minimal 5-chromatic graph; graph theory

---

## 引　言

四色定理是图论中最著名的定理之一：对任意地图（等价于封闭球面上的区域划分），仅用四种颜色就可以完成着色，使得相邻区域颜色不同。这个看似简单的命题自1852年被提出后，历经百余年才于1976年由Appel与Haken借助计算机穷举得证——这一结论令许多数学家感到遗憾，因为他们希望有一个不依赖计算机的优雅证明。

本文沿"两定理"路径建立四色定理的完整证明。核心思路是：若平面图中存在一个"局部四色困难子图"（即某区域使得染色困难的局部结构），则通过合理的变换操作，这个困难结构可以被"消除"，从而四色着色总是可以实现的。

### 证明路径的两大支柱

证明路径以两条定理为支柱：

1. **定理一** 极小5-色平面图中，至多只能存在一处局部四色困难子图，不可能同时存在两处或更多。

2. **定理二** 若某5-度顶点邻域为局部四色困难子图，则该困难结构可以通过对称拼接操作"转移"到图中另一个5-度顶点邻域，使原位置不再困难。

### 核心消解机制

以上两条定理共同支撑了四色定理的证明路径。其核心机制为**对称拼接消解法**：

1. **消解**：对极小5-色图 G 中唯一的 GLFHO（中心为5-度顶点 u），选取另一个与 u 不相邻的5-度顶点 v，通过定理二的对称拼接构造，获得 G - {v} 的正常4-着色，且该着色下 u 处无 GLFHO。

2. **扩展**：从 G - {v} 的4-着色扩展到 G 的4-着色。由于 v 是5-度顶点（5个邻居使用至多4种颜色），需对 v 的邻域进行 Kempe 链分析以完成扩展。

### 关于本文的状态

本文给出四色定理的一条完整证明路径。核心论证——定理一中 C2b、C3 情形的严格排除以及定理二的对称拼接构造——均已在正文中详细展开。作者欢迎同行评议与形式化验证，也欢迎对证明中任何步骤的质疑与改进建议。

