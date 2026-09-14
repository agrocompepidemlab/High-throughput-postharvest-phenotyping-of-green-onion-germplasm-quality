$\color{#3D8A4F}{\textsf{XGBOOST + SHAP · 350–1400 NM · N = 79 SPECTRA}}$

# Spectral classification of green onion pseudostems

> The metric panels of both figures in one table: accuracy, Cohen's κ and F1 macro for XGBoost and the LogReg L1 baseline, each with the stability of its inner cross-validation. Values are transcribed as reported in the figures.

---

## $\color{#3D8A4F}{\textbf{A}}$ Global analysis

One model per target variable, all four storage times pooled. Bands are selected inside each training fold, so nothing about the test fold reaches the selection step.

| Target | Class labels | $\color{#3D8A4F}{\textbf{Accuracy}}$<br>XGBoost | LogReg L1 | Stability | $\color{#3D8A4F}{\textbf{Cohen's κ}}$<br>XGBoost | LogReg L1 | Stability | $\color{#3D8A4F}{\textbf{F1 macro}}$<br>XGBoost | LogReg L1 | Stability | Confusion<br>matrix |
| :--- | :--- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | :--- |
| **Species**<br><sub>2 classes · n=79</sub> | <sub>A. fistulosum / Hybrid</sub> | **68.4%** | 59.5% | $\color{#7A8275}{\textsf{67.7 }\pm\textsf{ 16.7}}$ | **0.340** | 0.000 | $\color{#7A8275}{\textsf{0.190 }\pm\textsf{ 0.250}}$ | **0.670** | 0.373 | $\color{#7A8275}{\textsf{0.527 }\pm\textsf{ 0.189}}$ | <sub>35 / 12 · 13 / 19</sub> |
| **Genotype**<br><sub>10 classes · n=79</sub> | <sub>10 materials</sub> | **7.6%** | 7.6% | $\color{#7A8275}{\textsf{67.7 }\pm\textsf{ 16.7}}$ | $\color{#8A9285}{\textbf{0.026}}$ | 0.028 | $\color{#7A8275}{\textsf{0.009 }\pm\textsf{ 0.103}}$ | **0.067** | 0.031 | $\color{#7A8275}{\textsf{0.078 }\pm\textsf{ 0.075}}$ | <sub>see panel J</sub> |
| **Storage time**<br><sub>4 classes · n=79</sub> | <sub>DAH 2 / 6 / 10 / 14</sub> | **51.9%** | 24.1% | $\color{#7A8275}{\textsf{67.7 }\pm\textsf{ 16.7}}$ | **0.359** | 0.014 | $\color{#7A8275}{\textsf{0.427 }\pm\textsf{ 0.234}}$ | **0.522** | 0.139 | $\color{#7A8275}{\textsf{0.543 }\pm\textsf{ 0.193}}$ | <sub>11 / 8 / 10 / 12 correct</sub> |

## $\color{#3D8A4F}{\textbf{B}}$ Species classification within each storage time

The 60 bands fixed by the global species analysis, refitted separately at each sampling point, validated with StratifiedGroupKFold by genotype.

| Storage time | $\color{#3D8A4F}{\textbf{Accuracy}}$<br>XGBoost | LogReg L1 | Stability | $\color{#3D8A4F}{\textbf{Cohen's κ}}$<br>XGBoost | LogReg L1 | Stability | $\color{#3D8A4F}{\textbf{F1 macro}}$<br>XGBoost | LogReg L1 | Stability | $\color{#7B61C4}{\textbf{AUC}}$ | Confusion<br>matrix |
| :--- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | :--- |
| **2 DAH**<br><sub>T1 · n=20 · 12 / 8</sub> | **85.0%** | 60.0% | $\color{#7A8275}{\textsf{64.6 }\pm\textsf{ 39.0}}$ | $\color{#3D8A4F}{\textbf{0.694}}$ | 0.091 | $\color{#7A8275}{\textsf{0.188 }\pm\textsf{ 0.310}}$ | **0.847** | 0.524 | $\color{#7A8275}{\textsf{0.594 }\pm\textsf{ 0.398}}$ | $\color{#7B61C4}{\textbf{0.776}}$ | <sub>10 / 2 · 1 / 7</sub> |
| **6 DAH**<br><sub>T2 · n=20 · 12 / 8</sub> | **60.0%** | 60.0% | $\color{#7A8275}{\textsf{54.2 }\pm\textsf{ 38.1}}$ | $\color{#8A9285}{\textbf{0.167}}$ | 0.091 | $\color{#7A8275}{\textsf{0.175 }\pm\textsf{ 0.294}}$ | **0.583** | 0.524 | $\color{#7A8275}{\textsf{0.484 }\pm\textsf{ 0.371}}$ | $\color{#7B61C4}{\textbf{0.729}}$ | <sub>8 / 4 · 4 / 4</sub> |
| **10 DAH**<br><sub>T3 · n=20 · 12 / 8</sub> | **80.0%** | 60.0% | $\color{#7A8275}{\textsf{54.2 }\pm\textsf{ 38.1}}$ | $\color{#3D8A4F}{\textbf{0.600}}$ | 0.091 | $\color{#7A8275}{\textsf{0.158 }\pm\textsf{ 0.291}}$ | **0.798** | 0.524 | $\color{#7A8275}{\textsf{0.482 }\pm\textsf{ 0.389}}$ | $\color{#7B61C4}{\textbf{0.901}}$ | <sub>9 / 3 · 1 / 7</sub> |
| **14 DAH**<br><sub>T4 · n=19 · 11 / 8</sub> | **84.2%** | 36.8% | $\color{#7A8275}{\textsf{70.8 }\pm\textsf{ 26.2}}$ | $\color{#3D8A4F}{\textbf{0.671}}$ | 0.295 | $\color{#7A8275}{\textsf{0.167 }\pm\textsf{ 0.343}}$ | **0.835** | 0.352 | $\color{#7A8275}{\textsf{0.614 }\pm\textsf{ 0.310}}$ | $\color{#7B61C4}{\textbf{0.773}}$ | <sub>10 / 1 · 2 / 6</sub> |

<sub>Stability = inner CV, mean ± SD · Confusion matrix = correct / misclassified per true class · κ $\color{#3D8A4F}{\textsf{> 0.40 moderate–good}}$ · κ $\color{#3D8A4F}{\textbf{> 0.60 excellent}}$ · κ $\color{#8A9285}{\textbf{weak}}$</sub>

---

### Notes

| | |
|:---|:---|
| $\color{#3D8A4F}{\textbf{Source}}$ | Every value is transcribed from the metric panel of the corresponding figure. Percentages are shown to one decimal and κ and F1 to three, so 7.60% and 7.6% in the Genotype panel appear here as the single value they represent. |
| $\color{#3D8A4F}{\textbf{Models}}$ | XGBoost with SHAP-based band selection (main model) and LogReg L1 (baseline). 79 pseudostem spectra, 350–1400 nm, ComBat-corrected, 60 bands selected per fold in the global analysis and fixed for the per-time-point analysis. |
| $\color{#3D8A4F}{\textbf{Stability}}$ | Inner cross-validation run on the training folds only, grouped the same way as the outer CV. Mean ± standard deviation. It is not a confidence interval for the out-of-fold metric next to it. |
| $\color{#3D8A4F}{\textbf{Chance level}}$ | Species 2 classes → 50% · Storage time 4 classes → 25% · Genotype 10 classes → 10%. κ &gt; 0.40 is moderate-to-good agreement; κ &gt; 0.60 is excellent. |
| $\color{#3D8A4F}{\textbf{AUC}}$ | One-vs-rest, computed on the out-of-fold probabilities. Binary here, so both classes share the same value. The global figure does not label AUC on its ROC panels. |

> [!WARNING]
> **Worth checking** — The notebook prints three of these κ as negative: Genotype XGBoost −0.026, Genotype LogReg L1 −0.028, and Storage time LogReg L1 −0.014. The figures show them positive, and the table above follows the figures. A negative κ means performance slightly below chance, so the sign changes how that row reads.

<sub>Source: **Phase 4_Spectral_analysis.ipynb** — metric panels of the two composite figures.</sub>
