# VulRIS paper data

This repository contains the final evidence used by the VulRIS paper. The
evaluation uses one fixed 140-case Vul4J+ cohort under a source-only baseline
(B0) and a VulRIS-assisted condition (P1).

## Final results

| Method/model | B0 | P1 | P1−B0 |
| --- | ---: | ---: | ---: |
| DeepSeek 4.1 Flash (Max) | 39/140 (27.86%) | 48/140 (34.29%) | +9 (+6.43 pp) |
| Gemini 3.8 Flash (High) | 52/140 (37.14%) | 49/140 (35.00%) | -3 (-2.14 pp) |
| GPT-6 Luna (High) | 15/140 (10.71%) | 18/140 (12.86%) | +3 (+2.14 pp) |
| GPT-6 Luna (Max) | 20/140 (14.29%) | 23/140 (16.43%) | +3 (+2.14 pp) |

The CodeQL CLI 2.23.2 baseline reports 19/140 (13.57%). GPT-5.6 Luna is
excluded from the final paper and comparative experiment.

## Total token usage

The values below are aggregate input-plus-output tokens over the same 140
cases. A negative change means that P1 used fewer tokens than B0.

| Model profile | B0 total tokens | P1 total tokens | P1−B0 | Change |
| --- | ---: | ---: | ---: | ---: |
| DeepSeek 4.1 Flash (Max) | 11,557,700 | 11,164,300 | -393,400 | -3.40% |
| Gemini 3.8 Flash (High) | 11,555,500 | 9,053,900 | -2,501,600 | -21.65% |
| GPT-6 Luna (High) | 876,200 | 1,031,200 | +155,000 | +17.69% |
| GPT-6 Luna (Max) | 3,831,600 | 3,639,800 | -191,800 | -5.01% |

The machine-readable source is
[`model-condition-metrics.csv`](results/vul4jplus-final-20261110/model-condition-metrics.csv).

## Contents

- [`results/vul4jplus-final-20261110`](results/vul4jplus-final-20261110/):
  1,260 case-level binary decisions, machine-readable paper tables, data
  dictionary, provenance hashes, and the raw-ledger manifest.
- [Raw experiment ledgers and criteria artifacts](https://github.com/VulRIS-data/Data/releases/tag/vul4jplus-paper-evidence-20261110):
  13 SQLite ledgers and four mapping/criteria artifacts distributed as one
  GitHub Release asset.
- [`DATA_SOURCES.md`](DATA_SOURCES.md): benchmark source and redistribution
  scope.
- [`LICENSES.md`](LICENSES.md): licensing boundaries for original metadata and
  third-party benchmark material.

The old VJBench, CWE-Bench-Java, and superseded Vul4J+ aggregate files were
removed from the final branch because they are not used by the final
Vul4J+-only manuscript.
