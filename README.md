## 🧪 Hypothesis Test Reference Table

### 📘 Terminology & Abbreviations

| Symbol / Term               | Meaning                                                                                                                                               |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| ✅ Use / ❌ Don’t use         | When a test is appropriate or inappropriate                                                                                                           |
| pop.                        | Population                                                                                                                                            |
| **SD**                      | Standard Deviation: measure of spread in data                                                                                                         |
| \$\mu\$, \$\mu\_0\$         | Population mean / hypothesized population mean                                                                                                        |
| \$\bar{x}\$                 | Sample mean                                                                                                                                           |
| \$s\$, \$s\_d\$             | Sample SD \$\div\$ SD of paired differences                                                                                                           |
| \$n\$, \$n\_i\$             | Sample size / size of group \$i\$                                                                                                                     |
| \$\sigma\$, \$\sigma\_i\$   | Population standard deviation (known for Z-tests)                                                                                                     |
| \$\hat{p}\$, \$\hat{p}\_i\$ | Sample proportion                                                                                                                                     |
| \$p\_0\$                    | Hypothesized population proportion                                                                                                                    |
| \$\alpha\$                  | Significance level (e.g., 0.005)                                                                                                                      |
| **CV** (Critical Value)     | Cutoff value from the test distribution for given \$\alpha\$, degrees of freedom (df), and tail type                                                  |
| df                          | Degrees of freedom: number of values free to vary (e.g., one-sample t: n−1; two-sample t: n₁+n₂−2; ANOVA between: k−1; within: N−k; χ²: categories−1) |
| \$x\_i\$, \$y\_i\$          | Individual paired observations                                                                                                                        |
| \$r\$                       | Pearson correlation coefficient                                                                                                                       |
| \$F\$                       | F-statistic: ratio of variances in ANOVA                                                                                                              |
| \$SS\$, \$MS\$              | Sum of Squares \$\div\$ Mean Square (for ANOVA calculations)                                                                                          |
| \$\chi^2\$                  | Chi-square statistic                                                                                                                                  |
| \$O\_i\$, \$E\_i\$          | Observed / Expected frequencies in contingency tables                                                                                                 |
| \$R\_i\$                    | Sum of ranks in group \$i\$                                                                                                                           |
| \$U\$                       | Mann-Whitney U statistic                                                                                                                              |
| \$H\$                       | Kruskal-Wallis H statistic                                                                                                                            |
| \$\bar{d}\$                 | Mean of the paired differences                                                                                                                        |
| One-sided test              | Hypothesis test that checks for a deviation in one direction only (greater than or less than)                                                         |
| Two-sided test              | Hypothesis test that checks for any difference (either greater or less than)                                                                          |

> **Note on Critical Values and Degrees of Freedom**:
>
> * **df** varies by test; see definitions above.
> * For **Z-tests** at \$\alpha = 0.005\$:
>
>   * Two-sided: CV \$\approx \pm2.807\$ (df infinite)
>   * One-sided: CV \$\approx 2.576\$
> * For **t-tests** at \$\alpha = 0.005\$, CV depends on df:
>
>   * One-sample t (df = n−1), e.g. df=29: two-sided CV \$\approx \pm2.756\$; one-sided CV \$\approx 2.462\$
>   * Two-sample t (df ≈ n₁+n₂−2), e.g. df=53: two-sided CV \$\approx \pm2.678\$; one-sided CV \$\approx 2.405\$
> * For **Chi-square** at \$\alpha = 0.005\$, CV depends on df (e.g. df=5: CV \$\approx 15.086\$)
> * For **F-tests** at \$\alpha = 0.005\$, CV depends on (df₁, df₂) via F-table.
> * Non-parametric tests reference appropriate df/tables.
> * Use \$\alpha/2 = 0.0025\$ for two-sided tests.

> ### 🧐 Tail Selection & p‑Value Interpretation
>
> * **Two-sided Tests**: Detect **any** difference; alternative “\$\neq\$”.
> * **One-sided Tests**: Detect **directional** change; alternative “>” or “<”.
> * **p‑value vs \$\alpha\$**:
>
>   * If *p* < \$\alpha\$: **reject \$H\_0\$**—significant.
>   * If *p* ≥ \$\alpha\$: **fail to reject \$H\_0\$**—insufficient evidence.
> * **Test statistic vs CV**:
>
>   * Two-sided: \$|stat| > CV\$.
>   * One-sided: stat > CV (right) or stat < −CV (left).

## Statistical Tests Table (\$\alpha = 0.005\$)

| Test Name                 | Type           | When to Use / Not Use                                                  | Formula                                                                                                                             | Variables                      | Example                                         | Data Type            | Required Data                 | Hypotheses                                                            | Tail Options   |
| ------------------------- | -------------- | ---------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ | ----------------------------------------------- | -------------------- | ----------------------------- | --------------------------------------------------------------------- | -------------- |
| One-sample t-test         | Parametric     | ✅ mean vs known pop. mean<br>❌ non-normal small \$n\$                  | \$t = \dfrac{\bar x - \mu\_0}{s \div \sqrt{n}}\$                                                                                    | \$\bar x, \mu\_0, s, n\$       | “30 students: mean=75, s=10 vs 70”              | Continuous           | raw sample, known \$\mu\_0\$  | \$H\_0: \bar x = \mu\_0\$<br>\$H\_a: \bar x \neq \mu\_0\$             | two-/one-sided |
| Two-sample t-test         | Parametric     | ✅ two independent means<br>❌ non-normal or unequal var.                | \$t = \dfrac{\bar x\_1 - \bar x\_2}{\sqrt{\dfrac{s\_1^2}{n\_1} + \dfrac{s\_2^2}{n\_2}}}\$                                           | \$\bar x\_i, s\_i, n\_i\$      | “BP: A (n=25, mean=120) vs B (n=30, mean=125)”  | Continuous           | two samples                   | \$H\_0: \bar x\_1 = \bar x\_2\$<br>\$H\_a: \bar x\_1 \neq \bar x\_2\$ | two-/one-sided |
| Paired t-test             | Parametric     | ✅ before/after same group<br>❌ independent groups                      | \$t = \dfrac{\bar d}{s\_d \div \sqrt{n}}\$                                                                                          | \$\bar d, s\_d, n\$            | “20 patients: mean change=−5 kg, SD=2”          | Continuous, paired   | paired differences            | \$H\_0: \bar d = 0\$<br>\$H\_a: \bar d \neq 0\$                       | two-/one-sided |
| One-sample Z-test         | Parametric     | ✅ large \$n\$, known \$\sigma\$<br>❌ small \$n\$ or unknown \$\sigma\$ | \$Z = \dfrac{\bar x - \mu}{\sigma \div \sqrt{n}}\$                                                                                  | \$\bar x, \mu, \sigma, n\$     | “Widget weight (n=100, mean=50.2, σ=0.5) vs 50” | Continuous           | raw sample, known \$\sigma\$  | \$H\_0: \bar x = \mu\$<br>\$H\_a: \bar x \neq \mu\$                   | two-/one-sided |
| Two-sample Z-test         | Parametric     | ✅ large \$n\$, known \$\sigma\_i\$<br>❌ unknown pop. SD                | \$Z = \dfrac{\bar x\_1 - \bar x\_2}{\sqrt{\dfrac{\sigma\_1^2}{n\_1} + \dfrac{\sigma\_2^2}{n\_2}}}\$                                 | \$\bar x\_i, \sigma\_i, n\_i\$ | “Yield: A (150,200,σ=15) vs B (180,190,σ=20)”   | Continuous           | two samples, known \$\sigma\$ | \$H\_0: \bar x\_1 = \bar x\_2\$<br>\$H\_a: \bar x\_1 \neq \bar x\_2\$ | two-/one-sided |
| Z-test prop. (1)          | Parametric     | ✅ prop. vs known \$p\_0\$<br>❌ very small \$n\$                        | \$Z = \dfrac{\hat p - p\_0}{\sqrt{\dfrac{p\_0(1-p\_0)}{n}}}\$                                                                       | \$\hat p, p\_0, n\$            | “65/100 click vs 60%”                           | Proportion / binary  | successes & \$n\$             | \$H\_0: p = p\_0\$<br>\$H\_a: p \neq p\_0\$                           | two-/one-sided |
| Z-test prop. (2)          | Parametric     | ✅ compare two prop., large \$n\$<br>❌ small \$n\$                      | \$Z = \dfrac{\hat p\_1 - \hat p\_2}{\sqrt{p(1-p)\bigl(\tfrac{1}{n\_1}+\tfrac{1}{n\_2}\bigr)}}\$, \$p=\tfrac{x\_1+x\_2}{n\_1+n\_2}\$ | \$\hat p\_i, x\_i, n\_i, p\$   | “A:40/200=20% vs B:30/180≈16.7%”                | Proportion / binary  | two successes & sample sizes  | \$H\_0: p\_1 = p\_2\$<br>\$H\_a: p\_1 \neq p\_2\$                     | two-/one-sided |
| Chi-square (gof)          | Non-Parametric | ✅ observed vs expected counts<br>❌ expected < 5                        | \$\chi^2 = \sum\_i \dfrac{(O\_i - E\_i)^2}{E\_i}\$                                                                                  | \$O\_i, E\_i\$                 | “Die rolls vs expected”                         | Categorical          | obs & exp counts              | \$H\_0:\$ observed = expected<br>\$H\_a:\$ observed \neq expected     | two-sided only |
| Chi-square (independ.)    | Non-Parametric | ✅ association between cats<br>❌ sparse tables                          | \$\chi^2 = \sum\_{i,j} \dfrac{(O\_{ij} - E\_{ij})^2}{E\_{ij}}\$                                                                     | \$O\_{ij}, E\_{ij}\$           | “Gender vs Yes/No”                              | Categorical          | contingency table             | \$H\_0:\$ independent<br>\$H\_a:\$ associated                         | two-sided only |
| Pearson correlation       | Parametric     | ✅ linear rel’n<br>❌ non-linear or heavy outliers                       | \$r = \dfrac{\sum\_i (x\_i - \bar x)(y\_i - \bar y)}{\sqrt{\sum\_i (x\_i - \bar x)^2 \sum\_i (y\_i - \bar y)^2}}\$                  | \$x\_i,y\_i,\bar x,\bar y\$    | “Height vs weight in 50 people”                 | Paired continuous    | paired x,y values             | \$H\_0: r = 0\$<br>\$H\_a: r \neq 0\$                                 | two-/one-sided |
| ANOVA                     | Parametric     | ✅ compare 3+ means<br>❌ non-normal or unequal var.                     | \$F = \dfrac{MS\_b}{MS\_w}, MS\_b=\dfrac{SS\_b}{k-1}, MS\_w=\dfrac{SS\_w}{N-k}\$                                                    | \$SS\_b, SS\_w, k, N\$         | “Classes A/B/C scores”                          | Continuous, grouped  | raw values + groups           | \$H\_0:\$ all means equal<br>\$H\_a:\$ at least one differs           | two-sided only |
| Mann-Whitney U test       | Non-Parametric | ✅ two independent groups, non-normal<br>❌ parametric ok                | \$U = n\_1 n\_2 + \dfrac{n\_1(n\_1+1)}{2} - R\_1\$                                                                                  | \$n\_i, R\_1\$                 | “Stress Day vs Night”                           | Ordinal / continuous | two samples, ranks/raw        | \$H\_0:\$ distributions equal<br>\$H\_a:\$ distributions differ       | two-/one-sided |
| Wilcoxon signed-rank test | Non-Parametric | ✅ paired non-normal<br>❌ parametric ok                                 | \$W = \min(W^+, W^-), W^+ = \sum\_{d\_i>0}R\_i, W^- = \sum\_{d\_i<0}R\_i\$                                                          | \$d\_i, R\_i, W^+, W^-\$       | “Mood 1–10 before/after”                        | Paired ordinal       | paired before/after scores    | \$H\_0:\$ median diff = 0<br>\$H\_a:\$ median diff \neq 0             | two-/one-sided |
| Kruskal-Wallis test       | Non-Parametric | ✅ 3+ groups non-normal<br>❌ ANOVA conditions met                       | \$H = \dfrac{12}{N(N+1)}\sum\_i \dfrac{R\_i^2}{n\_i} - 3(N+1)\$                                                                     | \$R\_i, n\_i, N\$              | “Satisfaction N/S/E”                            | Ordinal, grouped     | raw values + groups           | \$H\_0:\$ distributions equal<br>\$H\_a:\$ at least one differs       | two-sided only |
