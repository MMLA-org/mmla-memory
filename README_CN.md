# MMLA：记忆如何让过去塑造未来

<div align="center">

[English](./README.md) | **简体中文**

</div>

[![arXiv](https://img.shields.io/badge/arXiv-2606.28876-b31b1b.svg)](https://arxiv.org/abs/2606.28876)
[![Technical Report](https://img.shields.io/badge/PDF-Technical_Report-316FF6.svg)](./MMLA_Technical_Report.pdf)

MMLA 研究一个仅靠扩大上下文窗口无法回答的问题：

> 哪些已经完成的观察应当被允许改变模型的有界持久状态？它们应当替换哪一段旧状态？模型又应当在什么时候选择不写入？

公开论文提出了一种事件级记忆架构：模型在已完成的局部片段上进行整合，为目标 row 构造完整候选，并在“完整 row 原子覆写”和 NULL 之间做出选择。真实未来只在训练阶段用于评价写入动作；部署阶段保持因果且不可见未来。完整 Technical Report 保留了推导、实验历史、负面结果、审计边界、比较、协议与附录。

## 阅读论文

- **arXiv 论文：** [arXiv:2606.28876](https://arxiv.org/abs/2606.28876)
- **完整技术报告：** [MMLA_Technical_Report.pdf](./MMLA_Technical_Report.pdf)
- **项目仓库：** [MMLA-org/mmla-memory](https://github.com/MMLA-org/mmla-memory)

## 一分钟理解 MMLA

1. 因果 backbone 只基于已经可用的状态进行预测。
2. 一个有界局部片段完成后，双向 consolidator 只重新解释已经观察到的内容，不改变此前输出。
3. 片段被转换为有界、有序的事件序列。
4. 对每个事件和候选目标 row，神经模块提出语义内容；可信 assembler 管理 tenant、ACL、版本、保护、来源、回滚与删除验证等系统字段。
5. future-blind controller 为该事件提交一个完整 row，或选择 NULL。只有之后的 token 才能读取更新后的状态。
6. 训练阶段可以用共享同一 prefix 的多个真实 continuation 为动作定价；部署阶段不接收任何未来 token。

Resident row 具有固定 bit budget；无界来源记录和 archive 保留在外部并单独计算成本。Canonical view 与 neural view 共享 identity、version 和 validation boundary；二者不一致时 row 会被隔离，而不是静默选择其中一个。多事件 teacher 使用 future-blind branch-prefix cost-to-go，报告同时计算完整候选构造和所有 replay successor state 的成本。真正合并两个 authoritative resident rows 需要有序事件或未来的有界事务，不能隐藏在一次单 row 写入中。

## 当前证据支持什么

- **受控生命周期执行：** 三个固定 seed 均达到 300/300 held-out records。
- **带 archive fallback 的有界选择：** 在报告的 held-out multi-hop QA 设置中，相对弱的、预算匹配的 dense baseline 提升 5.5--16.6 F1，相对 BM25 提升 4.0--6.2 F1。原始 Llama 预算执行保留为失败结果；修正后的 Qwen packer 满足逐记录预算上限。
- **Typed relational transport：** 每个 seed 达到 240/240 held-out records；三个 same-checkpoint matched controls 均没有 whole-record success。

## 当前证据边界

端到端 predictive overwrite 闭环尚未验证。Dense-row、structured-span 与 checkpoint-native reader 虽然通过了已注册的物理映射检查，但 PM-I2 的九个任务都没有通过语义资格门。因此 predictive overwrite 仍然关闭。本报告不声称已经得到 learned future-value policy、重复写入稳定性或完整系统级 quality--cost crossover。

下一项已注册问题是故障定位：接口是在 fitted examples 上就失败，还是只在 fresh composition 上失败，抑或问题来自 routing/content readout？只有通过语义资格门的接口，才允许开启 expected-risk oracle 和后续 controller 实验。

## 与相关系统的关系

报告比较了 MMLA、FlashKDA、MemOps 和 Metis。它们分别处理 recurrent kernel substrate、memory-operation diagnosis、native model memory 与语义上具有权威性的有界状态等不同层面。当前不声称优于这些系统，也不声称已经完成集成。

## 引用

如果你的研究使用或讨论了本工作，请引用 arXiv 论文：

```bibtex
@misc{zou2026mmla,
  title   = {MMLA: How Memory Lets the Past Shape the Future},
  author  = {Zou, Junyi and Donz, Avrova},
  year    = {2026},
  eprint  = {2606.28876},
  archivePrefix = {arXiv},
  primaryClass  = {cs.CL},
  url     = {https://arxiv.org/abs/2606.28876}
}
```

## 作者

Junyi Zou 与 Avrova Donz 为同等贡献作者。

- Junyi Zou — MMLA-org — [ORCID](https://orcid.org/0009-0009-1367-7428)
- Avrova Donz — MMLA-org；Communication University of China (CUC) — [ORCID](https://orcid.org/0009-0009-0100-0719)

本仓库有意只保留英文 README、中文 README 与完整 Technical Report。Checkpoint、数据集和内部审计 artifact 并不因此被视为已经公开下载。
