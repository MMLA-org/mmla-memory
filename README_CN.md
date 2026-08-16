# MMLA Memory

[English README](README.md)

MMLA 研究一个有界记忆系统如何让较早的推理影响较后的推理，同时不混淆
因果顺序、权威状态与证据边界。技术树将已经验证的组件证据、已登记的负面
结果，以及五条形式化后续分支明确分开：推理时训练、原子记忆行、预测式
准入、策略/记忆双状态和已完成片段整合。

- 公开论文：[arXiv:2606.28876](https://arxiv.org/abs/2606.28876)
- 项目仓库：[MMLA-org/mmla-memory](https://github.com/MMLA-org/mmla-memory)
- 作者：Junyi Zou、Avrova Donz（共同贡献）

## 文档

- [完整技术报告](MMLA_Technical_Report.pdf) — V3-R24 候选稿完整保留 R22
  的证据记录，并整合五条形式化分支及其证明、反例、成本和停止规则。
- [推理时训练](RTT_Foundations.pdf) — 定义有类型的题内过程，以及区分策略
  状态学习与搜索、上下文、记忆或工作区影响所需的证据。
- [原子记忆行](Atomic_Memory_Rows.pdf) — 建立有界类型化行、可信组装、精确
  提交/NULL、生命周期语义、恢复机制和显式资源核算。
- [预测式记忆准入](Predictive_Memory_Admission.pdf) — 形式化事件索引的分组
  未来、期望风险比较器、精确 NULL、不确定性感知准入、可识别性限制和证伪门。
- [MMLA-RTT 双状态](MMLA_RTT_Dual_State.pdf) — 让策略状态与权威记忆在类型、
  权限、生命周期、重置、回滚和账本上保持分离，并给出条件式组合与识别协议。
- [已完成片段整合](Completed_Segment_Consolidation.pdf) — 给出闭合后因果契约：
  五种时钟、不可变已输出历史、唯一事件归属、教师信息隔离、暴露规则和有界工作量。

## 证据状态

### 已验证的组件证据

公开 V3/R22 记录包含已准入的组件级证据：在各自声明的范围内，受控生命周期
行为、稀疏且校准过的检索/回退行为，以及类型化传输和驻留状态组件。

### 已登记的负面结果

同一记录保留了已经关闭的科学门：PM-I2 语义接口未通过（0/9）；PM-I3 对学习式
潜在行路线发现拟合支持失败；学习式预测覆盖仍未获得验证。

### 理论与协议后续稿

五篇焦点论文和 V3-R24 都是本地候选稿，仍待 Reviewer 独立裁定。它们新增的是
条件数学、系统契约、反例和尚未运行的协议，不包含新的实验结果，也不证明预言机
差距、学习式准入策略、严格 RTT 或 CSBC 成功、安全性，或端到端效率优势。

## 引用

请将公开 arXiv 论文作为主要公开记录引用：

```bibtex
@article{zou2026mmla,
  title         = {MMLA: How Memory Lets the Past Shape the Future},
  author        = {Zou, Junyi and Donz, Avrova},
  year          = {2026},
  eprint        = {2606.28876},
  archivePrefix = {arXiv},
  primaryClass  = {cs.AI}
}
```

以下本地候选稿记录与公开 arXiv 论文分开：

```bibtex
@techreport{zou2026mmlar24,
  title  = {MMLA: How Memory Lets the Past Shape the Future},
  author = {Zou, Junyi and Donz, Avrova},
  year   = {2026},
  note   = {V3-R24 complete technical report candidate; pending independent review}
}

@techreport{zou2026rtt,
  title  = {Reasoning-Time Training: Learning Before a Single Problem Ends},
  author = {Zou, Junyi and Donz, Avrova},
  year   = {2026},
  note   = {MMLA focus-paper candidate; pending independent review}
}

@techreport{zou2026amr,
  title  = {Atomic Memory Rows: A Bounded, Verifiable Substrate for Editable Reasoning},
  author = {Zou, Junyi and Donz, Avrova},
  year   = {2026},
  note   = {MMLA focus-paper candidate; pending independent review}
}

@techreport{zou2026pma,
  title  = {Learning What to Remember: Predictive Admission for Bounded Reasoning-Time Memory},
  author = {Zou, Junyi and Donz, Avrova},
  year   = {2026},
  note   = {MMLA focus-paper candidate; pending independent review}
}

@techreport{zou2026dualstate,
  title  = {MMLA-RTT: Dual-State Learning at Reasoning Time},
  author = {Zou, Junyi and Donz, Avrova},
  year   = {2026},
  note   = {MMLA focus-paper candidate; pending independent review}
}

@techreport{zou2026csbc,
  title  = {Causal Generation, Retrospective Consolidation: Completed-Segment Bidirectional Memory Without Temporal Leakage},
  author = {Zou, Junyi and Donz, Avrova},
  year   = {2026},
  note   = {MMLA focus-paper candidate; pending independent review}
}
```
