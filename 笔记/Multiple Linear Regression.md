
The motivation we develop [[Multiple Linear Regression]] is that [[Simple Linear Regression]] only contains one variable that could *explaining* $Y$.

That is, it will face a serious [[Omitted Variable Bias]] (OVB) problem.

## OLS under OVB

The true model:

$$
Y_i = \beta_0 +\beta_1 X_{1i}+\beta_2 X_{2i}+U_I
$$

However, we incorrectly assume:

$$
Y_i = \alpha_0 +\alpha_{1i} X_{1i}+V_i
$$

Where $E[V_i|X_{1i}]=0$





