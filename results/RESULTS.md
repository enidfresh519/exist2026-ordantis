# Official EXIST 2026 leaderboard results — Ordantis

Source: the official EXIST 2026 result spreadsheets in this folder
(`EXIST2026_TASK2_1_RESULTS.xlsx`, `..._2_...`, `..._3_...`), computed with the
[PyEvALL](https://github.com/EvALLTEAM/PyEvALL) framework. Each subtask is scored **Soft-Soft** and
**Hard-Hard**, over **ALL** instances and per language (**ES**, **EN**). Ranks are global positions
on each leaderboard; three runs (`Ordantis_1/2/3`) were submitted per subtask and setting.

Metrics: **ICM** and **ICM-Norm** are the official ranking metrics (higher is better); **F1** is the
hard secondary metric; **CE** is the soft cross-entropy (lower is better).

## 🏆 Headline

| Subtask · setting | ALL | ES | EN |
|---|---|---|---|
| **2.1 Binary — Soft** | **1 / 144** | **1 / 142** | **1 / 142** |
| **2.2 Intention — Soft** | **1 / 117** | **1 / 115** | **1 / 115** |
| **2.2 Intention — Hard** | **1 / 186** | **1 / 184** | **1 / 184** |
| 2.1 Binary — Hard | 3 / 217 | 2 / 215 | 4 / 215 |
| 2.3 Categories — Soft | 10 / 118 | 10 / 116 | 14 / 116 |
| 2.3 Categories — Hard | 132 / 187 | 134 / 185 | 133 / 185 |

**Three first places** (Task 2.1 soft, Task 2.2 soft and hard), each **#1 across ALL, Spanish and
English** simultaneously.

---

## Task 2.1 — Binary sexism detection (ALL instances)

**Soft-Soft** (144 systems) — columns: Rank · ICM-Soft · ICM-Soft-Norm · CE

| Run | Rank | ICM-Soft | ICM-Soft-Norm | CE |
|---|---|---|---|---|
| **Ordantis_1** (Gemini blend) | **1** | 0.7206 | 0.6158 | 0.8155 |
| Ordantis_3 | 2 | 0.5175 | 0.5832 | 0.8227 |
| Ordantis_2 | 3 | 0.5099 | 0.5820 | 0.8146 |

**Hard-Hard** (217 systems) — columns: Rank · ICM-Hard · ICM-Hard-Norm · F1-YES

| Run | Rank | ICM-Hard | ICM-Hard-Norm | F1-YES |
|---|---|---|---|---|
| Ordantis_2 (Longformer) | 3 | 0.4079 | 0.7074 | 0.8006 |
| Ordantis_1 | 4 | 0.4005 | 0.7037 | 0.8003 |
| Ordantis_3 | 6 | 0.3943 | 0.7005 | 0.7969 |

## Task 2.2 — Source-intention classification (ALL instances)

**Soft-Soft** (117 systems)

| Run | Rank | ICM-Soft | ICM-Soft-Norm | CE |
|---|---|---|---|---|
| **Ordantis_1** (raw blend) | **1** | 0.0114 | 0.5012 | 1.3334 |
| Ordantis_2 | 2 | -0.5650 | 0.4399 | 1.5248 |
| Ordantis_3 | 3 | -0.5685 | 0.4395 | 1.4874 |

**Hard-Hard** (186 systems)

| Run | Rank | ICM-Hard | ICM-Hard-Norm | F1 |
|---|---|---|---|---|
| **Ordantis_3** (model–Gemini blend) | **1** | 0.3709 | 0.6289 | 0.6158 |
| Ordantis_2 | 5 | 0.1790 | 0.5622 | 0.5453 |
| Ordantis_1 | 11 | 0.0659 | 0.5229 | 0.5368 |

## Task 2.3 — Multi-label sexism categorization (ALL instances)

**Soft-Soft** (118 systems)

| Run | Rank | ICM-Soft | ICM-Soft-Norm |
|---|---|---|---|
| Ordantis_1 (Longformer, no sampler) | 10 | -4.6874 | 0.2516 |
| Ordantis_2 | 26 | -5.7804 | 0.1937 |
| Ordantis_3 | 38 | -6.3589 | 0.1630 |

**Hard-Hard** (187 systems)

| Run | Rank | ICM-Hard | ICM-Hard-Norm | F1 |
|---|---|---|---|---|
| Ordantis_1 | 132 | -1.9465 | 0.0962 | 0.3790 |
| Ordantis_2 | 136 | -1.9631 | 0.0927 | 0.3786 |
| Ordantis_3 | 143 | -2.0800 | 0.0685 | 0.3731 |

Task 2.3 shows a sharp hard/soft asymmetry on the *same* probabilistic output: the model ranks
10/118 in soft but drops to 132/187 in hard. This isolates the failure to the category-threshold
binarization (which overfits the validation split) rather than the model itself — see the paper §14.
