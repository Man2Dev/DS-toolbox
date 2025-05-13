**Statistical Toolbox: Notebooks Directory**

Welcome to the **notebooks/** folder of the Statistical Toolbox repository. This directory contains self-contained Jupyter Notebooks—each focused on a specific statistical method or test. Together, they form a practical, hands‑on reference for performing common analyses in Python.

---

## 📋 Prerequisites

Before running any notebook, ensure you have:

* **Python 3.7+**
* Installed packages:

  * `pandas`
  * `numpy`
  * `scipy`
  * `matplotlib`
  * `seaborn`
  * `scikit-learn` (for example datasets)
  * `ipywidgets` and `plotly` *(optional, for interactive sections)*

You can install all dependencies with:

```bash
pip install pandas numpy scipy matplotlib seaborn scikit-learn ipywidgets plotly
```

---

## 🚀 How to Use

1. **Launch Jupyter**: From the repository root,

   ```bash
   jupyter notebook
   ```
2. **Navigate** to the **notebooks/** folder in the file browser.
3. **Open** the notebook of interest (e.g., `01_correlation_analysis.ipynb`).
4. **Run Cells** sequentially (Shift + Enter) to see explanations, code outputs, and visualizations.
5. **Modify** parameters or datasets in code to experiment with different data or settings.

---

## 📚 Notebook Index & Use Cases

| Filename                              | Purpose & Use Case                                                                                                                                                                                                                 |
| ------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **01\_correlation\_analysis.ipynb**   | **Correlation analysis (Pearson, Spearman, Kendall)**<br>Measure linear or monotonic associations between continuous or ordinal variables. Useful when exploring relationships (e.g., height vs. weight, test scores correlation). |
| **02\_binomial\_distribution.ipynb**  | **Binomial Distribution**<br>Compute probabilities of a given number of successes in fixed, independent trials (e.g., coin flips, pass/fail outcomes in quality control).                                                          |
| **03\_poisson\_distribution.ipynb**   | **Poisson Distribution**<br>Model count of rare events in a fixed interval (e.g., calls per minute at a call center, traffic accidents per day).                                                                                   |
| **04\_qq\_plot.ipynb**                | **Q–Q Plot**<br>Graphically compare a sample to a theoretical distribution or compare two samples. Ideal for checking normality or distributional shape.                                                                           |
| **05\_t\_tests.ipynb**                | **t-Tests (One-sample, Two-sample, Paired)**<br>Test mean differences against a known value, between two independent groups, or within paired samples (e.g., before/after studies).                                                |
| **06\_z\_tests\_and\_z\_score.ipynb** | **Z-Tests & Z-Scores**<br>Perform hypothesis tests when population variance is known or for large samples, and compute standard scores for data normalization.                                                                     |
| **07\_chi\_square\_tests.ipynb**      | **Chi-Square Tests**<br>Assess categorical data: goodness‑of‑fit (observed vs. expected frequencies) and independence (contingency tables, e.g., survey responses vs. demographic factors).                                        |
| **08\_anova.ipynb**                   | **ANOVA (Analysis of Variance)**<br>Compare means across three or more groups to detect any significant differences (e.g., multiple teaching methods evaluation).                                                                  |
| **09\_mann\_whitney\_u\_test.ipynb**  | **Mann–Whitney U Test**<br>Nonparametric alternative to the two-sample t-test for independent samples when normality is questionable.                                                                                              |
| **10\_wilcoxon\_signed\_rank.ipynb**  | **Wilcoxon Signed-Rank Test**<br>Nonparametric alternative to the paired t-test, for matched or repeated measures data.                                                                                                            |
| **11\_kruskal\_wallis.ipynb**         | **Kruskal–Wallis Test**<br>Nonparametric counterpart to one-way ANOVA, for comparing three or more independent groups without assuming normality.                                                                                  |

---

## 🔗 Further Reading & Resources

* **SciPy Documentation**: Functions and usage examples for each statistical test.
* **Seaborn Gallery**: Examples of advanced visualizations (heatmaps, regression plots).
* **Online Tutorials** (e.g., DataCamp, Real Python) for deeper dives into statistical modeling and interpretation.

---

*Happy analyzing!*

*— The Statistical Toolbox Team*

