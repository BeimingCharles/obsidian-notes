---
类型: 文献笔记
作者: Chen et al.
年份: 2026
DOI: 10.18653/v1/2026.eacl-long.274
Zotero键值: L6LK5P5R
阅读状态: 已初读并横向比较
主题: 跨模态情感冲突
出处: EACL 2026
更新日期: 2026-10-01
---

# Do Audio LLMs Really LISTEN, or Just Transcribe? Measuring Lexical vs. Acoustic Emotion Cues Reliance

[Zotero 条目](zotero://select/library/items/L6LK5P5R) · [打开 PDF](zotero://open-pdf/library/items/3VVWEVTF) · [论文来源](https://aclanthology.org/2026.eacl-long.274/)

## 一句话总结

通过控制词义和声学情绪线索的一致、冲突与缺席，诊断音频大模型的词义主导及声学线索利用不足。

## 我的原始总结

> 第三篇论文，语音模型大多是在转写成文本进行分析而不是直接通过语音进行分析，所以提出了 LISTEN 这个评估框架。

## 核对后的修正

实验支持“受测模型更依赖词义”，不能直接推断其内部都采用“先转写、后文本分类”流水线。模型直接接收音频，也可能主要从音频中利用词义。LISTEN 主要贡献是评测与诊断，没有提出一个修复融合模型。

## 研究问题与评测

常规识别分数能否区分词义捷径与真实声学情绪能力？

- Neutral-Text：文字情绪中性，声学情绪变化。
- Emotion-Matched：词义与声学线索一致。
- Emotion-Mismatched：二者冲突。
- Paralinguistic：无词语的情绪声学线索。

比较文本、音频及文本＋音频输入。依据：Introduction 的贡献说明与 §3–5。

## 数据集与实验

作者公布 [数据](https://huggingface.co/datasets/VibeCheck1/LISTEN_full) 和 [代码](https://github.com/DeliJingyiC/LISTEN)。受测模型为文中六个系统，结论限于其版本与设置；下载数据时需核对版本、行数和样本/问题的计数口径。

## 主要结论与边界

受测模型存在词义主导。冲突部分以讽刺为主，主要为单句设置，未覆盖完整多轮对话；不能将结果推广为所有自然情绪冲突。

## 对我的研究有什么用

可作为冻结模型的诊断实验起点。研究对话上下文是否改变线索利用时，需同时检查改善与恶化的样本。

## 我的疑问

- 加入真实上下文是否降低还是强化文字偏好？
- 换成不包含讽刺的自然冲突是否仍出现同一现象？
- 细粒度标签和标注歧义会怎样影响结论？

## 相关概念与论文

- [[跨模态情感冲突]]
- [[Han 2025 - CA-MER与MoSEAR]]
- [[Sun 2026 - EmoMM与CHASE]]

## 待补证据

- [ ] 各条件的样本与标签分布。
- [ ] 文本、音频、联合输入的配对结果。
- [ ] 本机小样本基线与失败类型。
