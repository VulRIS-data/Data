# VulRIS evaluation results

This repository contains the final case-level results reported for the four Java vulnerability datasets in the VulRIS paper. The unit of evaluation is a dataset case: `hit` means the method identified the vulnerability recorded for that case and its relevant cause; `miss` means it did not.

| Dataset | Cases | CodeQL hits | VulRIS with LLM hits | Difference |
| --- | ---: | ---: | ---: | ---: |
| Vul4J | 79 | 11 (13.92%) | 29 (36.71%) | 18 (22.78 percentage points) |
| VJBench | 42 | 4 (9.52%) | 20 (47.62%) | 16 (38.10 percentage points) |
| Vul4J+ | 140 | 17 (12.14%) | 59 (42.14%) | 42 (30.00 percentage points) |
| CWE-Bench-Java | 210 | 40 (19.05%) | 91 (43.33%) | 51 (24.29 percentage points) |

The LLM condition used the pre-fix source plus a VulRIS relation index, with DeepSeek V4.1 Flash Max and at most one submitted vulnerability candidate per case. CodeQL ran on the pre-fix source with CLI 2.23.2, Java query pack 1.8.1, `java-security-extended.qls`, and `build-mode=none`. Results were judged against the vulnerability specified by the respective dataset, not against the presence of any security warning.

The evaluated cohort contains all 79 Vul4J cases and 42 VJBench cases. The 140 Vul4J+ cases are the cases with a suitable vulnerability reference among 191 prepared records. The 210 CWE-Bench-Java cases are the cases with a determinable reference and completed results for both methods among 213 prepared records. The four rows are reported separately because Vul4J and Vul4J+ have overlapping cases.

## Files

- [summary.csv](results/summary.csv): counts, rates, differences, and four-way overlap.
- [vul4j.csv](results/vul4j.csv): final results for Vul4J.
- [vjbench.csv](results/vjbench.csv): final results for VJBench.
- [vul4j-plus.csv](results/vul4j-plus.csv): final results for Vul4J+.
- [cwe-bench-java.csv](results/cwe-bench-java.csv): final results for CWE-Bench-Java.

Each case file contains `dataset`, `case_id` (the paper's case key), `original_id` (upstream identifier), `cve`, `source_repository`, `codeql`, and `vulris_llm`. The `summary.csv` percentages are calculated from the integer case counts, with `rate_difference_pp` calculated before rounding.

The original vulnerable source trees are not redistributed here. The case identifiers link these results to the source datasets: [Vul4J](https://github.com/tuhh-softsec/Vul4J), [VJBench's source collection](https://github.com/lin-tan/llm-vul), [Vul4J+](https://zenodo.org/records/13752193), and [CWE-Bench-Java](https://github.com/iris-sast/iris). The index-building software is in [VulRIS-data/VulRIS](https://github.com/VulRIS-data/VulRIS).
