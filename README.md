# 📊 Hypothesis Testing Cheat Sheet

This guide helps you choose the right statistical test, set up hypotheses, and interpret results. Whether you're comparing means, proportions, or checking associations, this cheat sheet has you covered!

## 🎯 How to Use This Guide
1. **Identify your data**: Are you working with means, proportions, or categories?
2. **Check assumptions**: Ensure your data meets the test’s requirements (e.g., normality, sample size).
3. **Pick a test**: Use the table to find the test that matches your needs.
4. **Interpret results**: Use the decision rules to decide if your results are significant.

## 📚 Key Terms
| Term | Meaning |
|------|---------|
| **✅ Use / ❌ Don’t use** | When a test is appropriate or inappropriate. |
| **H₀ (Null Hypothesis)** | The default assumption (e.g., "no difference" or "no effect"). |
| **Hₐ (Alternative Hypothesis)** | What you're testing for (e.g., "there is a difference"). |
| **p-value** | Probability of observing your data if H₀ is true. Smaller p-values suggest stronger evidence against H₀. |
| **α (Significance Level)** | Threshold for significance (usually 0.05). If p < α, reject H₀. |
| **Critical Value (CV)** | Cutoff for test statistic to reject H₀ (depends on α and test). |
| **One-sided Test** | Tests for a difference in one direction (e.g., "greater than"). |
| **Two-sided Test** | Tests for any difference (e.g., "not equal"). |
| **df** | Degrees of freedom, used to find critical values. |
| **SD** | Standard deviation, measures data spread. |
| **CV (Critical Value)** | Cutoff value from the test distribution for given $\alpha$, df, and alternative type. |
| **pop.** | Population|
| **gof** | Goodness-of-Fit |

## 📚 Key Symbols
| Symbol               | Meaning                                                                                       |
| --------------------------- | --------------------------------------------------------------------------------------------- |
| $\mu$, $\mu_0$              | Population mean / hypothesized population mean                                                |
| $\bar{x}$                   | Sample mean                                                                                   |
| $s$, $s_d$                  | Sample standard deviation / standard deviation of paired differences                          |
| $n$, $n_i$                  | Sample size / size of group $i$                                                               |
| $\sigma$, $\sigma_i$        | Population standard deviation (known for Z-tests)                                             |
| $\hat{p}$, $\hat{p}_i$      | Sample proportion                                                                             |
| $p_0$                       | Hypothesized population proportion                                                            |
| $\alpha$                    | Significance level (e.g., $0.05$)                                                             |
| $x_i$, $y_i$                | Individual paired observations                                                                |
| $r$                         | Pearson correlation coefficient                                                               |
| $F$                         | F-statistic: ratio of variances in ANOVA                                                      |
| $SS$, $MS$                  | Sum of Squares / Mean Square (for ANOVA calculations)                                         |
| $\chi^2$                    | Chi-square statistic                                                                          |
| $O_i$, $E_i$                | Observed / Expected frequencies in contingency tables                                         |
| $R_i$                       | Sum of ranks in group $i$                                                                     |
| $U$                         | Mann-Whitney U statistic                                                                      |
| $H$                         | Kruskal-Wallis H statistic                                                                    |
| $\bar{d}$                   | Mean of the paired differences                                                                |

> **Note on Critical Values and Degrees of Freedom**:
>
> * **df** varies by test; see formulas in the main table.
> * Use $\alpha/2 = 0.025$ for two-sided tests.

> ### 🧐 Tail Selection & p‑Value Interpretation
>
> * **Two-sided Tests**: Detect **any** difference; alternative $\neq$.
> * **One-sided Tests**: Detect **directional** change; alternative ">" or "<".
> * **p‑value vs $\alpha$**:
>
>   * If *p* < $\alpha$: **reject $H_0$**—significant.
>   * If *p* ≥ $\alpha$: **fail to reject $H_0$**—insufficient evidence.
> * **Test statistic vs CV**:
>
>   * Two-sided: $|\text{stat}| > \text{CV}$.
>   * One-sided: stat > CV (right) or stat < −CV (left).

## 🧠 Tips for Interpretation
- For parametric tests (e.g., t-tests, Z-tests), compare the test statistic to a critical value (e.g., $t_{\alpha/2, df}$, $Z_{\alpha/2}$) or use the p-value against $\alpha$.
- For non-parametric tests (e.g., Chi-square, Mann-Whitney U), decision rules use critical values from respective distributions or p-values.
- **The p-value approach is consistent**: reject $H_0$ if p < $\alpha$; otherwise, fail to reject $H_0$.
- **Critical Values**: If the test statistic exceeds the critical value (or falls in the rejection region), reject H₀. Critical values depend on α, df, and the test distribution.

## 📋 Hypothesis Tests Table
Each test includes when to use it, the formula, key variables, example, hypotheses, tail options, and how to decide whether to reject H₀.

## Statistical Tests Table ($\alpha = 0.05$)

| Test Name                 | Type           | When to Use / Not Use                                                  | Formula                                                                                                                             | Variables                    | df Formula                          | Example                                       | Hypotheses                                                            | Tail Options   | Decision Rule                                                                                       |
| ------------------------- | -------------- | ---------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- | ----------------------------------- | --------------------------------------------- | --------------------------------------------------------------------- | -------------- | --------------------------------------------------------------------------------------------------- |
| One-sample t-test         | Parametric     | ✅ mean vs known pop. mean<br>❌ non-normal small $n$                    | $t = \dfrac{\bar x - \mu_0}{\dfrac{s}{\sqrt{n}}}$                                                                                   | $\bar x,\mu_0,s,n$           | $n - 1$                             | 30 students: mean=75, s=10 vs 70              | $H_0: \mu = \mu_0$<br>$H_a: \mu \neq \mu_0$                           | Two-/One-sided | Two-sided: Reject $H_0$ if $\|t\| > t_{\alpha/2, n-1}$ or p < $\alpha$<br>One-sided: Reject if $t > t_{\alpha, n-1}$ (right) or $t < -t_{\alpha, n-1}$ (left) |
| Two-sample t-test         | Parametric     | ✅ two independent means<br>❌ non-normal or unequal variances           | $t = \dfrac{\bar x_1 - \bar x_2}{\sqrt{\dfrac{s_1^2}{n_1} + \dfrac{s_2^2}{n_2}}}$                                                  | $\bar x_i,s_i,n_i$           | $n_1 + n_2 - 2$                     | BP: A (n=25, mean=120) vs B (n=30, mean=125)  | $H_0: \mu_1 = \mu_2$<br>$H_a: \mu_1 \neq \mu_2$                       | Two-/One-sided | Two-sided: Reject $H_0$ if $\|t\| > t_{\alpha/2, df}$ or p < $\alpha$<br>One-sided: Reject if $t > t_{\alpha, df}$ (right) or $t < -t_{\alpha, df}$ (left) |
| Paired t-test             | Parametric     | ✅ before/after same group<br>❌ independent groups                      | $t = \dfrac{\bar d}{\dfrac{s_d}{\sqrt{n}}}$                                                                                         | $\bar d,s_d,n$               | $n - 1$                             | 20 patients: mean change=−5 kg, SD=2          | $H_0: \mu_d = 0$<br>$H_a: \mu_d \neq 0$                               | Two-/One-sided | Two-sided: Reject $H_0$ if $\|t\| > t_{\alpha/2, n-1}$ or p < $\alpha$<br>One-sided: Reject if $t > t_{\alpha, n-1}$ (right) or $t < -t_{\alpha, n-1}$ (left) |
| One-sample Z-test         | Parametric     | ✅ large $n$, known $\sigma$<br>❌ small $n$ or unknown $\sigma$         | $Z = \dfrac{\bar x - \mu}{\dfrac{\sigma}{\sqrt{n}}}$                                                                                | $\bar x,\mu,\sigma,n$        | ∞ (known pop)                       | Widget weight (n=100, mean=50.2, σ=0.5) vs 50 | $H_0: \mu = \mu_0$<br>$H_a: \mu \neq \mu_0$                           | Two-/One-sided | Two-sided: Reject $H_0$ if $\|Z\| > Z_{\alpha/2}$ or p < $\alpha$<br>One-sided: Reject if $Z > Z_{\alpha}$ (right) or $Z < -Z_{\alpha}$ (left) |
| Two-sample Z-test         | Parametric     | ✅ large $n$, known $\sigma_i$<br>❌ unknown pop. SD                     | $Z = \dfrac{\bar x_1 - \bar x_2}{\sqrt{\dfrac{\sigma_1^2}{n_1} + \dfrac{\sigma_2^2}{n_2}}}$                                        | $\bar x_i,\sigma_i,n_i$      | ∞ (known pop)                       | Yield: A (150,200,σ=15) vs B (180,190,σ=20)   | $H_0: \mu_1 = \mu_2$<br>$H_a: \mu_1 \neq \mu_2$                       | Two-/One-sided | Two-sided: Reject $H_0$ if $\|Z\| > Z_{\alpha/2}$ or p < $\alpha$<br>One-sided: Reject if $Z > Z_{\alpha}$ (right) or $Z < -Z_{\alpha}$ (left) |
| Z-test prop. (1)          | Parametric     | ✅ prop. vs known $p_0$<br>❌ very small $n$                             | $Z = \dfrac{\hat p - p_0}{\sqrt{\dfrac{p_0(1-p_0)}{n}}}$                                                                            | $\hat p,p_0,n$               | ∞ (approx.)                         | 65/100 click vs 60%                           | $H_0: p = p_0$<br>$H_a: p \neq p_0$                                   | Two-/One-sided | Two-sided: Reject $H_0$ if $\|Z\| > Z_{\alpha/2}$ or p < $\alpha$<br>One-sided: Reject if $Z > Z_{\alpha}$ (right) or $Z < -Z_{\alpha}$ (left) |
| Z-test prop. (2)          | Parametric     | ✅ compare two proportions<br>❌ small $n$                               | $Z = \dfrac{\hat p_1 - \hat p_2}{\sqrt{p(1-p)\bigl(\tfrac{1}{n_1}+\tfrac{1}{n_2}\bigr)}}$, $p=\tfrac{x_1+x_2}{n_1+n_2}$            | $\hat p_i,x_i,n_i,p$         | ∞ (approx.)                         | A:40/200=20% vs B:30/180≈16.7%                | $H_0: p_1 = p_2$<br>$H_a: p_1 \neq p_2$                               | Two-/One-sided | Two-sided: Reject $H_0$ if $\|Z\| > Z_{\alpha/2}$ or p < $\alpha$<br>One-sided: Reject if $Z > Z_{\alpha}$ (right) or $Z < -Z_{\alpha}$ (left) |
| Chi-square (gof)          | Non-Parametric | ✅ observed vs expected counts<br>❌ expected < 5                        | $\chi^2 = \sum_i \dfrac{(O_i - E_i)^2}{E_i}$                                                                                        | $O_i,E_i$                    | $\text{categories}-1$               | Die rolls vs expected                         | $H_0:$ matches<br>$H_a:$ differs                                      | Two-sided only | Reject $H_0$ if $\chi^2 > \chi^2_{\alpha, df}$ or p < $\alpha$                                              |
| Chi-square (independ.)    | Non-Parametric | ✅ association between categories<br>❌ sparse tables                    | $\chi^2 = \sum_{i,j} \dfrac{(O_{ij} - E_{ij})^2}{E_{ij}}$                                                                           | $O_{ij},E_{ij}$              | $(r-1)(c-1)$                        | Gender vs Yes/No                              | $H_0:$ independent<br>$H_a:$ associated                               | Two-sided only | Reject $H_0$ if $\chi^2 > \chi^2_{\alpha, df}$ or p < $\alpha$                                              |
| Pearson correlation       | Parametric     | ✅ linear rel’n<br>❌ non-linear or outliers                             | $r = \dfrac{\sum_i (x_i - \bar x)(y_i - \bar y)}{\sqrt{\sum_i (x_i - \bar x)^2 \sum_i (y_i - \bar y)^2}}$                           | $x_i,y_i,\bar x,\bar y$      | $n-2$                               | Height vs weight in 50 people                 | $H_0: \rho = 0$<br>$H_a: \rho \neq 0$                                 | Two-/One-sided | Two-sided: Reject $H_0$ if $\|t\| > t_{\alpha/2, n-2}$ or p < $\alpha$<br>One-sided: Reject if $t > t_{\alpha, n-2}$ (right) or $t < -t_{\alpha, n-2}$ (left) where $t = r \sqrt{\dfrac{n-2}{1-r^2}}$ |
| ANOVA                     | Parametric     | ✅ compare 3+ means<br>❌ non-normal or unequal variances                | $F = \dfrac{MS_b}{MS_w}, MS_b=\dfrac{SS_b}{k-1}, MS_w=\dfrac{SS_w}{N-k}$                                                            | $SS_b,SS_w,k,N$              | between: $k-1$<br>within: $N-k$     | Classes A/B/C scores                          | $H_0:$ all equal<br>$H_a:$ at least one differs                       | Two-sided only | Reject $H_0$ if $F > F_{\alpha, df_b, df_w}$ or p < $\alpha$                                                |
| Mann-Whitney U test       | Non-Parametric | ✅ two independent groups, non-normal<br>❌ parametric conditions        | $U = n_1 n_2 + \dfrac{n_1 (n_1 + 1)}{2} - R_1$                                                                                      | $n_i,R_1$                    | not applicable                      | Stress Day vs Night                           | $H_0:$ distributions equal<br>$H_a:$ differ                           | Two-/One-sided | Reject $H_0$ if $U < U_{crit}$ (two-tailed) or $U < U_{crit}$ (one-tailed) or p < $\alpha$          |
| Wilcoxon signed-rank test | Non-Parametric | ✅ paired non-normal<br>❌ parametric conditions                         | $W = \min(W^+,W^-), W^+=\sum_{d_i>0}R_i, W^-=\sum_{d_i<0}R_i$                                                                       | $d_i,R_i,W^+,W^-$            | $n-1$                               | Mood 1–10 before/after therapy                | $H_0:$ median diff=0<br>$H_a:$ median diff $\neq$ 0                   | Two-/One-sided | Reject $H_0$ if $W < W_{crit}$ (two-tailed) or $W < W_{crit}$ (one-tailed) or p < $\alpha$          |
| Kruskal-Wallis test       | Non-Parametric | ✅ 3+ groups non-normal<br>❌ ANOVA conditions                           | $H = \dfrac{12}{N(N+1)} \sum_i \dfrac{R_i^2}{n_i} - 3(N+1)$                                                                         | $R_i,n_i,N$                  | $k-1$                               | Satisfaction N/S/E                            | $H_0:$ distributions equal<br>$H_a:$ at least one differs             | Two-sided only | Reject $H_0$ if $H > \chi^2_{\alpha, k-1}$ or p < $\alpha$                                          |
