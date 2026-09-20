# 一元实值函数

## 主要内容

Bourbaki《数学原本》(Éléments de mathématique) 中《一元实值函数》一卷的自学笔记。

## 说明

本笔记按 Bourbaki 原书的章节层级组织，对应关系如下：

| Bourbaki 原书 | 本笔记 | 本仓库中的示例 |
|---|---|---|
| 章（Chapitre） | `Content/` 下的**章目录** | `1_Derivatives/` |
| 节（§） | 章目录下的**节目录** | `1_First_Derivative/` |
| 小节（1、2、…） | 节目录下的 **`.tex` 文件** | `1_Derivative_of_a_vector_function.tex` |

- 目录与文件名取该层级标题的**英译**，并加编号前缀（`1_`、`2_`…，不加前导零）。
- 中文标题写在 `\chapter{...}` 与 `\section{...}` 中：`\chapter{}` 用该**节目录**名的中译，`\section{}` 用该**文件**名的中译。
- 每层目录各有一个 `index.tex`，按顺序汇总对下一层的 `\input`。

正文的写作规定详见模板《笔记写作》中的《正文写作规范》；tex 层面（定理环境用法、符号库维护等）的规定另见该模板的 README。

## 内容结构

```
Content/
├─ 1_Derivatives/
│  ├─ 1_First_Derivative/
│  ├─ 2_The_Mean_Value_Theorem/
│  ├─ 3_Derivatives_of_Higher_Order/
│  └─ 4_Convex_Functions_of_a_Real_Variable/
├─ 2_Primitives_and_Integrals/
│  ├─ 1_Primitives_and_Integrals/
│  ├─ 2_Integrals_over_Non-Compact_Intervals/
│  └─ 3_Derivatives_and_Integrals_of_Functions_Depending_on_a_Parameter/
├─ 3_Elementary_Functions/
│  ├─ 1_Derivatives_of_The_Exponential_and_Circular_Functions/
│  └─ 2_Expansions_of_The_Exponential_and_Circular_Functions_and_of_The_Functions_associated_with_them/
├─ 4_Differential_Equations/
│  ├─ 1_Existence_Theorems/
│  └─ 2_Linear_Differential_Equations/
├─ 5_Local_Study_of_Functions/
│  ├─ 1_Comparison_of_Functions_on_a_Directed_Set/
│  ├─ 2_Astmptotic_Expansions/
│  ├─ 3_Asymptotic_Expansions_of_Functions_of_a_Real_Variable/
│  ├─ 4_Application_to_Series_with_Positive_Terms/
│  └─ Appendix/
├─ 6_Generalized_Taylor_Expansions_Euler-Maclaurin_Summation_Formula/
│  ├─ 1_Generalized_Taylor_Expansions/
│  ├─ 2_Eulerian_Expansions_of_The_Trigonometric_Functions_and_Bernoulli_Numbers/
│  └─ 3_Bounds_for_the_Remainder_in_the_Euler-Maclaurin_Summation_Formula/
└─ 7_The_Gamma_Functions/
   ├─ 1_The_Gamma_Function_in_The_Real_Domain/
   └─ 2_The_Gamma_Function_in_The_Comples_Domain/
```

## 文件结构

```
main.tex          编译入口
structure.sty     样式包：页面设置、定理环境、引用、数学符号库
quiver.sty        交换图支持
Content/          分章正文，每章一个目录，由 index.tex 汇总 \input
commit.py         一键提交并推送（说明见 commit.md）
setup_mode.py     习题编排模式切换（说明见 setup_mode.md）
README.md         本文件：项目说明
CHANGELOG.md      更新日志：tex 配置调整与正文内容调整
```

各脚本的选项与功能分别见 [commit.md](commit.md) 与 [setup_mode.md](setup_mode.md)；符号库由上层目录的 `symbols.py` 统一管理。

## 编译

本笔记使用自建的【笔记写作】模板（样式包 `structure.sty`），须用 **XeLaTeX** 编译：

```bash
xelatex main.tex
```

- **编译环境**：XeLaTeX。模板依赖 ctexbook 与 XeLaTeX 特性，**不支持 pdfLaTeX**。
- **TeXStudio**：建议 4.0 或更高版本。
- `main.pdf` 未纳入版本控制，需本地编译生成。
