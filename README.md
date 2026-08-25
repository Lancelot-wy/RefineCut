# RefineCut

> 🚧 **Under construction** — this repository accompanies our EMNLP 2026 paper and is being prepared for the camera-ready release. The code and benchmark are being cleaned for publication and will appear here; the layout below shows what is coming.（维护中：代码与基准整理发布中，以下为规划的仓库结构。）

**Plans You Can Check: Verifier-Grounded Learning of an Open-Weight Planner for Executable Video-Editing** (EMNLP 2026)

RefineCut treats video editing as *executable video-editing planning*: a planner edits a typed timeline through structured `RefinePatch` operations, and a deterministic verifier applies each patch and re-checks an explicit constraint ledger. The planner is trained in two stages — verifier-replayed distillation of multi-teacher trajectories, then verifier-centered self-improvement (RefineCut-Evo) — and runs in a closed verifier loop with no teacher calls at inference.

## Planned repository layout

```
refinecut/        typed timeline state, constraint ledger, RefinePatch apply, caption schema
refinecut_eval/   deterministic verifier, RefinePatch canonicalization,
                  closed-loop evaluation harness, VES metric aggregation
prompts/          the PatchPlanner evaluation prompt
schemas/          JSON schemas: constraint ledger, edit plan, RefinePatch,
                  timeline IR, verifier output
docs/             metric definitions, VES formula, verifier implementation notes
examples/         a worked task with its verifier replay
```

**RefineCut-Bench** — the benchmark (3,578 tasks with briefs and constraint ledgers, clip and music metadata for 7,971 captioned clips and 499 tracks, all splits, and the canonicalized multi-teacher trajectories with per-branch verifier replay scores) — will be released on Hugging Face alongside the code.

## Citation

```bibtex
@inproceedings{refinecut2026,
  title     = {Plans You Can Check: Verifier-Grounded Learning of an Open-Weight Planner for Executable Video-Editing},
  author    = {Wang, Haoyu and Feng, Cheng and Bian, Liuyang and Huang, Ruiyang and Wei, Lei and Wen, Yafei and Chen, Xiaoxin and Tang, Xiaoying},
  booktitle = {Proceedings of the 2026 Conference on Empirical Methods in Natural Language Processing},
  year      = {2026}
}
```

## License

Code: Apache-2.0. RefineCut-Bench will be released separately under CC BY-NC 4.0; raw video clips and music are referenced by their public source identifiers and are not redistributed.
