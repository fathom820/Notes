# Chapter 6: Categorical Variable Inference

Remember *confidence interval* equation for ***p***

## 6.1: Sample Size Determination

It is often the case when conducting an experiment that you want your estimate (maybe interval) to have a certain precision (set confidence interval width)

- We can control the confidence interval width (or at least bounds) with the *sample size*.
- confidence level plays a factor as well

- If you're doing an experiment where it costs money to take data (real world), then how many samples you can get matters. For hypothetical examples, the more the better, but IRL you need to have accurate data with a reasonable sample size.

Right hand side of *confidence interval equation* controls the confidence interval width.

**Example**: A university newspaper is conducting a survey to determine what fractio nof students support a $200 per year increase in fees to pay for a new football stadium. How big of a smaple is required to ensure the margin of error is samaller that 0.04 using a 95% confidence level?
<br>
<center>
<img src="https://ncalculators.com/images/formulas/margin-error-calculation.jpg" width="250">
</center>
<br>

- z* is connected to `1.96` confidence interval
- Find point where only `2.5%` lies to the right
- Do we know *p* from the problem? **No.**
  - What do we put in for *p*?
    - Worst case `(p * (1-p)) = 0.5`

## 6.2: Inference for a Difference of Two Proportions

*skipping for now*

## 6.3/6.4: Association Between Categorical Variables

### Association
- Some type of dependence between two different variables. 
- Independence is a lack of association!

For two events `A` and `B`, they are independent if `P(A && B) = P(A)P(B)`

With that definition, we get two more definitions of independence
```
get these from the lecture slides
```

---
# Your Turn

H<sub>0</sub> = neighborhood and occupation are independent

H<sub>A</sub> = neighborhood and occupation are associated (not dependent)

1. Significance level: *a* = 0.05 (5%)
2. Assumptions:
   1. Two variables are categorical [Yes]
   2. Data taken w/ random sample [Yes]
   3. All expected cell counts are `> 5` [Assume it is true, we will see it later]
3. Calculate test statistic *T*
   1. **Minitab**

**Minitab**
Pearson: 24.571
- Deg. of Freedom: 6
- *p*-value: 0.000

Likelihood Ratio: 25.279
- DF: 6
- *p*-value: 0.000

<img src="../Screenshot 2022-04-04 133513.png"></img>
Reject H<sub>0</sub>

Conclusion: at the 5% significance level, there is enough evidence to suggest that neighborhood and occupation are related