# MMLA Memory

[中文 README](README_CN.md)

MMLA studies how a bounded memory system can let earlier reasoning influence
later reasoning without blurring causal order, authority, or evidence. The
technology tree separates a validated component record from registered
negative results and from five formal successor branches: reasoning-time
training, atomic memory rows, predictive admission, dual policy/memory state,
and completed-segment consolidation.

- Public paper: [arXiv:2606.28876](https://arxiv.org/abs/2606.28876)
- Project repository: [MMLA-org/mmla-memory](https://github.com/MMLA-org/mmla-memory)
- Authors: Junyi Zou and Avrova Donz (equal contribution)

## Documents

- [Complete Technical Report](MMLA_Technical_Report.pdf) — the additive V3-R24
  candidate preserves the complete R22 evidence record and integrates all five
  formal branches, their proofs, counterexamples, costs, and stop rules.
- [Reasoning-Time Training](RTT_Foundations.pdf) — defines a typed within-problem
  process and the evidence needed to distinguish policy-state learning from
  search, context, memory, or workspace effects.
- [Atomic Memory Rows](Atomic_Memory_Rows.pdf) — develops a bounded typed row,
  trusted assembly, exact commit/NULL behavior, lifecycle semantics, recovery,
  and explicit resource accounting.
- [Predictive Memory Admission](Predictive_Memory_Admission.pdf) — formalizes
  event-indexed grouped futures, expected-risk comparators, exact NULL,
  uncertainty-aware admission, identification limits, and falsification gates.
- [MMLA-RTT Dual State](MMLA_RTT_Dual_State.pdf) — keeps policy state and
  authoritative memory distinct in type, privilege, lifetime, reset, rollback,
  and ledger while specifying conditional composition and identification.
- [Completed-Segment Consolidation](Completed_Segment_Consolidation.pdf) — gives
  a causal post-closure contract with five clocks, immutable emitted history,
  unique event ownership, teacher separation, exposure rules, and bounded work.

## Evidence status

### Validated component evidence

The public V3/R22 record contains the admitted component evidence: controlled
lifecycle behavior, sparse calibrated retrieval/fallback behavior, and typed
transport and resident-state components under their stated scopes.

### Registered negative results

The same record retains the closed scientific gates: the PM-I2 semantic
interface did not qualify (0/9), PM-I3 found fitted-support failure for the
learned latent-row route, and learned predictive overwrite remains unvalidated.

### Theory and protocol successors

The five focus papers and V3-R24 are local candidates pending independent
Reviewer adjudication. They add conditional mathematics, systems contracts,
counterexamples, and unrun protocols; they contain no new experimental result
and do not establish an oracle gap, learned admission policy, strict-RTT or
CSBC success, safety, or end-to-end efficiency superiority.

## Citation

Please cite the public arXiv paper as the primary public record:

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

The following local candidate records are separate from the public arXiv
publication:

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
