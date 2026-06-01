# Meta-Decoding for Quantum Error Correction

This repository contains experiments on learned rescue routing for decoder portfolios in a structured quantum error-correction-inspired benchmark.

## Project idea

Different QEC decoders have different inductive biases. A single decoder may not be optimal across all syndrome regimes. This project studies whether a learned router can exploit decoder complementarity by selecting or overriding decoders on a per-sample basis.

## Final result

On the final structured benchmark:

| Method | Accuracy | Gain over CNN baseline |
|---|---:|---:|
| CNN baseline | 0.762687 | 0.000000 |
| Full accuracy-rescue router | 0.765312 | +0.002625 |
| MLP-only rescue router | 0.765875 | +0.003188 |
| Oracle accuracy router | 0.995875 | +0.233187 |

Bootstrap over 16,000 test samples for the full rescue router:

- Observed gain: +0.002625
- 95% CI: [+0.000375, +0.004938]
- P(gain > 0): 0.9864

The full rescue router switched on 2.1% of samples, with 189 helpful switches and 147 harmful switches, giving a net gain of 42 correct samples.

## Repository structure

```text
notebooks/   Colab notebooks and final experimental notebook
report/      LaTeX report and compiled PDF
figures/     Plots used in the report
results/     Saved result tables
