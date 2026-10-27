# econ5200-lab08-hypothesis-testing# Diagnosing Underpowered Studies and P-Hacking

## Objective
I investigated how low statistical power, multiple testing, p-hacking, and outliers can affect the reliability of statistical results.

## Methodology
- Analyzed the statistical power of a pilot study with 15 participants per group and calculated the sample size needed for 80% power.
- Applied the Benjamini-Hochberg correction to 20 subgroup tests to identify potentially misleading significant results.
- Simulated 1,000 experiments involving 20 tests of true null hypotheses to examine false positives.
- Wrote my own Benjamini-Hochberg function and compared its results against statsmodels, using data with two planted real effects.
- Compared Welch's t-test, Yuen's 20% trimmed t-test, and permutation tests using ordinary and trimmed means on heavy-tailed earnings data.
- Simulated how p-hacking can push borderline results toward statistical significance.

## Key Findings
- **Statistical power:** The pilot study had only 15 participants per group, highlighting the importance of checking whether a study has enough power to detect a real effect.
- **Multiple testing:** Examined how testing 20 subgroups increases the risk of false positives and how the Benjamini-Hochberg correction controls the false discovery rate.
- **False positives:** Simulated 1,000 experiments to study how frequently at least one false positive occurs when testing 20 true null hypotheses.
- **Benjamini-Hochberg validation:** Tested my function against statsmodels using two planted real effects.
- **Heavy-tailed earnings:** Welch's t-test (p = 0.2650) and the ordinary-mean permutation test (p = 0.3496) found no significant difference. Yuen's trimmed t-test (p = 0.0066) and the trimmed-mean permutation test (p = 0.0056) found significant differences.
- **Effect of outliers:** The ordinary-mean permutation test measured a $3,541 difference, while the trimmed-mean permutation test measured a $2,033 difference. The methods disagreed based on the statistic being tested, not whether they were parametric or permutation-based.

## Conclusion
I learned that statistically significant findings depend on sample size, multiple testing, and the choice of statistic. This lab showed me why researchers should check statistical power, correct for multiple comparisons, and consider the influence of extreme observations before interpreting their results.
