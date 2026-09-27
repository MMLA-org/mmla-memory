# MMLA 记忆论文家族

[English README](README.md)

本仓库收录 MMLA 综合技术报告 [arXiv:2606.28876v4](https://arxiv.org/abs/2606.28876v4) 与五篇 R02 配套理论论文。

**记忆介导学习架构（Memory-Mediated Learning Architecture，MMLA）**研究**预测式双状态适应（Predictive Dual-State Adaptation，PDSA）**：缓慢更新的基础参数、有界数值策略状态和有界权威记忆各有独立职责。同一问题内的反馈可以更新策略状态，可信记忆生命周期则提交一条完整的类型化记忆行，或执行精确的 `NULL` 操作。后续推理可以读取两种状态，但它们遵循各自的更新、重置和回滚约束。

仓库提供论文 PDF 与说明文档，暂不包含实现代码、模型检查点或数据集。

## PDF 文件

| 论文 | 版本 | 主题 |
| --- | --- | --- |
| [MMLA: Memory-Mediated Learning Architecture for Predictive Dual-State Adaptation](2606.28876v4.pdf) | arXiv v4，2026 年 9 月 14 日 | 综合架构、条件性理论与汇总证据 |
| [Reasoning-Time Training: Learning Before a Single Problem Ends](RTT_Foundations.pdf) | R02 | 同一问题内的策略更新与因果验证 |
| [Atomic Memory Rows: A Bounded, Verifiable Substrate for Editable Reasoning](Atomic_Memory_Rows.pdf) | R02 | 有界权威记忆行、原子提交与生命周期不变量 |
| [Learning What to Remember: Predictive Admission for Bounded Reasoning-Time Memory](Predictive_Memory_Admission.pdf) | R02 | 基于未来风险的准入、精确 `NULL` 与训练和部署的信息隔离 |
| [MMLA-RTT: Dual-State Learning at Reasoning Time](MMLA_RTT_Dual_State.pdf) | R02 | 策略与记忆的独立状态、干预与效果归因 |
| [Causal Generation, Retrospective Consolidation: Completed-Segment Bidirectional Memory Without Temporal Leakage](Completed_Segment_Consolidation.pdf) | R02 | 因果生成与片段结束后的回顾式记忆更新 |

建议先阅读 v4 综合报告，了解整体架构与汇总证据。五篇独立 R02 论文仍沿用较早的公共 V3 和技术报告作为证据背景，均为等待独立评审的重大修订候选稿。

## 证据边界

v4 报告日期为 **2026 年 9 月 14 日**，科学证据截止日期为 **2026 年 9 月 13 日**。

**已验证组件。** 报告记录了三个随机种子下各 300/300 条留出记录的精确生命周期执行、相对于冻结隐藏表示的稠密检索和 BM25 基线的校准检索增益，以及每个种子下各 240/240 条留出记录的精确类型化 anchor-filler 传输。这些结果验证了受限组件，尚不能证明自然语言记忆管理或完整 PDSA 系统有效。

**未决问题与已登记负结果。** 受限潜在状态读出已有进展，但在九条训练轨迹的比较中，没有潜在状态实验组同时通过两个任务族的连续事件任务验证。截至证据截止日期，严格的纯策略 RTT 效果、预测准入 oracle 优势、学习得到的未来不可见准入策略，以及策略与记忆的因子交互优势均未确立。空结果、负对照与未决比较保持其报告中的状态。

**理论论文。** 五篇 R02 提供显式假设、类型化模型、证明、反例与可证伪义务。它们未报告新实验，也未确立合格的语义接口、学习得到的准入机制、双状态经验成功或完成段整合的经验成功。论文之间的形式化依赖不代表经验验证可以相互转移。

## BibTeX

```bibtex
@article{zou2026mmla,
  title   = {{MMLA}: Memory-Mediated Learning Architecture for Predictive Dual-State Adaptation},
  author  = {Zou, Junyi and Donz, Avrova},
  year    = {2026},
  eprint  = {2606.28876},
  archivePrefix = {arXiv},
  primaryClass  = {cs.cl},
  note    = {Version 4},
  url     = {https://arxiv.org/abs/2606.28876v4}
}

@article{zou2026rtt,
  title  = {Reasoning-Time Training: Learning Before a Single Problem Ends},
  author = {Zou, Junyi and Donz, Avrova},
  year   = {2026},
  note   = {R02 major-revision candidate; pending independent Reviewer adjudication}
}

@article{zou2026amr,
  title  = {Atomic Memory Rows: A Bounded, Verifiable Substrate for Editable Reasoning},
  author = {Zou, Junyi and Donz, Avrova},
  year   = {2026},
  note   = {R02 major-revision candidate; pending independent Reviewer adjudication}
}

@article{zou2026pma,
  title  = {Learning What to Remember: Predictive Admission for Bounded Reasoning-Time Memory},
  author = {Zou, Junyi and Donz, Avrova},
  year   = {2026},
  note   = {R02 major-revision candidate; pending independent Reviewer adjudication}
}

@article{zou2026dual,
  title  = {MMLA--RTT: Dual-State Learning at Reasoning Time},
  author = {Zou, Junyi and Donz, Avrova},
  year   = {2026},
  note   = {R02 major-revision candidate; pending independent Reviewer adjudication}
}

@article{zou2026csbc,
  title  = {Causal Generation, Retrospective Consolidation: Completed-Segment Bidirectional Memory Without Temporal Leakage},
  author = {Zou, Junyi and Donz, Avrova},
  year   = {2026},
  note   = {R02 major-revision candidate; pending independent Reviewer adjudication}
}
```

## 许可证

本仓库采用 [知识共享署名-非商业性使用 4.0 国际许可协议（CC BY-NC 4.0）](LICENSE)。
