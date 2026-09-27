# MMLA memory paper family

[中文说明](README_CN.md)

This repository contains the MMLA integrated technical report, [arXiv:2606.28876v4](https://arxiv.org/abs/2606.28876v4), and five R02 companion theory papers.

**Memory-Mediated Learning Architecture (MMLA)** studies **Predictive Dual-State Adaptation (PDSA)**: slow base parameters, a bounded numerical policy state, and a bounded authoritative memory have distinct roles. Within-problem feedback may update the policy state, while a trusted memory lifecycle commits a complete typed row or performs exact `NULL`. Later reasoning may read both states under separate update, reset, and rollback contracts.

The repository distributes paper PDFs and documentation. Implementation code, model checkpoints, and datasets are not included.

## PDFs

| Paper | Version | Focus |
| --- | --- | --- |
| [MMLA: Memory-Mediated Learning Architecture for Predictive Dual-State Adaptation](2606.28876v4.pdf) | arXiv v4, 14 September 2026 | Integrated architecture, conditional theory, and consolidated evidence |
| [Reasoning-Time Training: Learning Before a Single Problem Ends](RTT_Foundations.pdf) | R02 | Within-problem policy updates and causal qualification |
| [Atomic Memory Rows: A Bounded, Verifiable Substrate for Editable Reasoning](Atomic_Memory_Rows.pdf) | R02 | Bounded authoritative rows, atomic commits, and lifecycle invariants |
| [Learning What to Remember: Predictive Admission for Bounded Reasoning-Time Memory](Predictive_Memory_Admission.pdf) | R02 | Future-risk admission, exact `NULL`, and training/deployment separation |
| [MMLA-RTT: Dual-State Learning at Reasoning Time](MMLA_RTT_Dual_State.pdf) | R02 | Separate policy and memory states, interventions, and attribution |
| [Causal Generation, Retrospective Consolidation: Completed-Segment Bidirectional Memory Without Temporal Leakage](Completed_Segment_Consolidation.pdf) | R02 | Causal generation and retrospective memory updates after segment closure |

Start with the integrated v4 report for the architecture and consolidated evidence. The standalone R02 papers retain their earlier public V3 and technical-report context and remain major-revision candidates pending independent review.

## Evidence boundary

The v4 report is dated **14 September 2026**, with a scientific evidence cutoff of **13 September 2026**.

**Validated components.** The report records exact lifecycle execution on 300/300 held-out records for each of three seeds, calibrated retrieval gains over frozen-hidden dense and BM25 baselines, and exact typed anchor-filler transport on 240/240 held-out records per seed. These results validate restricted components; they do not establish natural-language memory management or complete PDSA.

**Open results and registered negatives.** Restricted latent readout progress coexists with a nine-trajectory comparison in which no latent arm qualifies the continuous-event task across both task families. No strict policy-only RTT effect, predictive-admission oracle margin, learned future-blind admission policy, or policy-by-memory factorial advantage is established at the evidence cutoff. Null findings, negative controls, and unresolved comparisons retain their reported status.

**Theory papers.** The five R02 papers provide assumption-explicit definitions, typed models, proofs, counterexamples, and falsification obligations. They report no new experiments and do not establish a qualified semantic interface, learned admission, empirical dual-state success, or empirical completed-segment consolidation. Formal dependencies between papers do not transfer empirical validation.

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

## License

Licensed under [Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](LICENSE).
