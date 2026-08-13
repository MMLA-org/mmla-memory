# MMLA: How Memory Lets the Past Shape the Future

<div align="center">

**English** | [简体中文](./README_CN.md)

</div>

[![arXiv](https://img.shields.io/badge/arXiv-2606.28876-b31b1b.svg)](https://arxiv.org/abs/2606.28876)
[![Technical Report](https://img.shields.io/badge/PDF-Technical_Report-316FF6.svg)](./MMLA_Technical_Report.pdf)

MMLA studies a question that longer context alone does not answer:

> Which completed observations should be allowed to change a model's bounded,
> persistent state, which old state should they replace, and when should the
> model write nothing?

The public paper introduces an event-level memory architecture with
completed-segment consolidation, target-conditioned row construction, a hard
complete-row overwrite or NULL, and training-only future supervision. The
companion Technical Report preserves the full derivations, experiment history,
negative results, audit trail, comparisons, protocols, and appendices.

## Read the work

- **Public paper:** [arXiv:2606.28876](https://arxiv.org/abs/2606.28876)
- **Complete Technical Report:** [MMLA_Technical_Report.pdf](./MMLA_Technical_Report.pdf)
- **Repository:** [MMLA-org/mmla-memory](https://github.com/MMLA-org/mmla-memory)

## Architecture in one minute

1. A causal backbone predicts from previously available state.
2. After a bounded local segment is complete, a bidirectional consolidator may
   reinterpret only that already observed segment.
3. The segment is converted into a bounded ordered list of events.
4. For each event and target row, a neural module proposes semantic content;
   a trusted assembler owns tenant, ACL, version, protection, provenance,
   rollback, and deletion-verification fields.
5. A future-blind controller commits one complete row or chooses NULL for that
   event. Only later tokens can read the resulting segment state.
6. During training only, same-prefix realized futures may price all registered
   actions from one frozen snapshot. Deployment receives no future tokens.

Resident rows have fixed bit budgets; unbounded provenance and archives remain
external and separately charged. Canonical and neural bytes share one identity,
version, and validation boundary, with mismatch quarantined rather than silently
resolved. Multi-event training uses future-blind branch-prefix cost-to-go, and
the report charges complete candidate construction and every replayed successor
state. A true merge of two authoritative resident rows requires ordered events
or a future bounded transaction; it is not hidden inside one row write.

## What the evidence currently supports

- **Controlled lifecycle execution:** 300/300 held-out records for each of
  three fixed seeds.
- **Bounded selection with archive fallback:** +5.5--16.6 F1 over a weak
  budget-matched dense baseline and +4.0--6.2 F1 over BM25 on the reported
  held-out multi-hop QA settings. The original Llama budget execution is
  retained as failed; the corrected Qwen packer satisfies the stated
  per-record caps.
- **Typed relational transport:** 240/240 held-out records per seed, while
  three same-checkpoint matched controls obtain no whole-record successes.

## Current boundary

The end-to-end predictive overwrite loop has not yet been validated.
Dense-row, structured-span, and checkpoint-native readers preserve the
registered physical mapping checks but none of the nine PM-I2 jobs qualifies
semantically. Predictive overwrite therefore remains closed by gate. The
report does not claim a learned future-value policy, repeated-write stability,
or a full-system quality--cost crossover.

The next registered question is fault localization: does the interface fail
on fitted examples, only on fresh composition, or because of routing/content
readout? Only a semantically qualified interface may open the expected-risk
oracle and later controller experiments.

## Related systems

The report compares MMLA with FlashKDA, MemOps, and Metis. They address
different layers of the problem: recurrent kernel substrate, memory-operation
diagnosis, native model memory, and semantically authoritative bounded state.
No superiority or implemented integration is claimed.

## Citation

If you use or discuss this work, please cite the arXiv paper:

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

## Authors

Junyi Zou and Avrova Donz contributed equally.

- Junyi Zou — MMLA-org — [ORCID](https://orcid.org/0009-0009-1367-7428)
- Avrova Donz — MMLA-org; Communication University of China (CUC) —
  [ORCID](https://orcid.org/0009-0009-0100-0719)

This repository intentionally contains only the English and Chinese
reader-facing READMEs and the complete Technical Report. It does not imply
that checkpoints, datasets, or internal audit artifacts are already publicly
downloadable.
