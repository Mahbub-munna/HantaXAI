\# HantaXAI: Explainable Spatiotemporal Forecasting of Hantavirus Outbreaks



HantaXAI is a research project that investigates multi-source, explainable machine learning for early forecasting of Hantavirus outbreaks. The project uses an XGBoost-based prediction pipeline to combine epidemiological, environmental, clinical, and historical outbreak information for three-month-ahead outbreak prediction.



\## Research Overview



Hantavirus outbreaks are influenced by interacting epidemiological, ecological, environmental, and clinical factors. HantaXAI investigates whether integrating these heterogeneous sources can support earlier outbreak detection while maintaining model interpretability.



The study covers 25 countries across five WHO regions over the period 1993–2025.



\### Key Components



\- \*\*Multi-source data integration:\*\* Monthly epidemiological trends, environmental and ecological variables, clinical severity indicators, and historical outbreak statistics.

\- \*\*Temporal feature engineering:\*\* Lagged case counts, rolling statistics, seasonal encodings, and other historical features.

\- \*\*Prediction model:\*\* XGBoost for binary outbreak prediction three months ahead.

\- \*\*Temporal evaluation:\*\* Chronological training and testing, with time-series cross-validation.

\- \*\*Explainability:\*\* SHAP analysis to investigate global feature importance and individual feature contributions.



\## Methodology



The pipeline follows these main stages:



1\. Obtain and inspect the source data.

2\. Integrate the epidemiological, environmental, clinical, and historical records.

3\. Preprocess the data and construct temporally valid features.

4\. Define the three-month-ahead outbreak prediction target.

5\. Train and tune the XGBoost model using time-aware validation.

6\. Evaluate predictions on the held-out temporal test set.

7\. Analyze influential features using SHAP.

8\. Generate visualizations and summarize the findings.



The final model described in the paper uses 31 features, including 30 engineered features and an encoded country identifier.



\## Reported Results



The accompanying paper reports the following results:



| Metric | Reported value |

|---|---:|

| Test accuracy | 92.26% |

| Test ROC-AUC | 0.9565 |

| Test outbreak recall | 93.75% |

| Test F1-score | 0.9270 |

| Mean cross-validation ROC-AUC | 0.9855 ± 0.0116 |

| Mean cross-validation F1-score | 0.9455 ± 0.0163 |



These are the results reported in the manuscript. Users should run the notebook to inspect the implementation and verify reproducibility in their own environment.



\## Repository Contents



\- `HantaXAI.ipynb` — Main research notebook containing the implementation and analysis.

\- `requirements.txt` — Python dependencies.

\- `figures/` — Research figures and model visualizations, when included.

\- `results/` — Evaluation summaries and generated outputs, when included.

\- `CITATION.cff` — Citation metadata.



\## Dataset



The study uses a public Hantavirus epidemiology dataset hosted on Kaggle:



\*\*Dataset:\*\* \[Hantavirus (Andes Virus) — Global Epidemiology Dataset](https://www.kaggle.com/datasets/zkskhurram/hantavirus-andes-virus-global-epidemiology)



Review the dataset's license, provenance, and usage conditions before downloading, redistributing, or reusing its contents. Raw data are not included in this repository by default.



The original source records and the exact preprocessing procedure should be checked against the accompanying notebook before reproducing the experiments.



\## Getting Started



\### 1. Clone the repository



```bash

git clone https://github.com/YOUR\_USERNAME/HantaXAI.git

cd HantaXAI

```



Replace `YOUR\_USERNAME` with your GitHub username.



\### 2. Create a virtual environment



```bash

python -m venv .venv

```



Activate it:



\*\*Windows\*\*

```bash

.venv\\Scripts\\activate

```



\*\*Linux/macOS\*\*

```bash

source .venv/bin/activate

```



\### 3. Install dependencies



```bash

pip install -r requirements.txt

```



\### 4. Run the notebook



```bash

jupyter notebook HantaXAI.ipynb

```



Obtain the dataset separately and update the notebook's data path to match your environment. Execute the notebook cells in order.



\## Reproducibility Notes



\- The study uses a chronological train/test split: 1993–2021 for training and 2022–2025 for testing.

\- The forecast horizon is three months.

\- Feature construction must use only information available before the prediction time.

\- Preprocessing parameters should be fitted using training data and then applied to held-out data.

\- Random seeds, package versions, data-source versions, and model configuration should be recorded where applicable.

\- Reported metrics should be treated as reproduced only after the notebook has been executed and the results verified.



\## Limitations



The study uses retrospective, country-level data and may be affected by differences in surveillance coverage, data availability, and reporting practices. Independent geographic and prospective validation are important directions for future research.



\## Citation



If you use this work, please cite the associated paper:



> Rydi, R. A., Risha, R. T., Munna, M. A., Arman, M. S., Ahmed, F., and Ahmed, F. (2026). \*HantaXAI: Multi-Source Explainable Spatiotemporal XGBoost for Early Forecasting of Hantavirus Outbreaks\*. In Proceedings of the 4th International Conference on Computing Advancements (ICCA 2026).



\## Contact



For questions about the implementation or research, please open a GitHub issue or contact the corresponding authors listed in the paper.

