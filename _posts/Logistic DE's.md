In an isolated environment, a disease spreads at a rate proportional to the product of the infected and non-infected populations. Let $I(t)$ denote the number of infected individuals. Suppose that the total population is 3,000, the proportionality constant is 0.0003, and that $1\%$ of the population is infected at time $t=0$. Write down the initial value problem and the solution $I(t)$.

The initial value problem is:
$\dfrac{dI}{dt} = 0.0003 I(3000-I)$, $I(0)=30$.

This can be solved using separation of variables.

$\dfrac{dI}{I(3000-I)} = \dfrac{3}{10000} dt$

We can use partial fractions:

$\dfrac{A}{I} + \dfrac{B}{3000-I}  = \dfrac{1}{I(3000-I)}$

$A(3000-I) + BI = 1 + 0I$

$3000A + (B-A)I = 1 + 0I$, so

$A = \dfrac{1}{3000}$ and $B=\dfrac{1}{3000}$.

So we get

$\dfrac{1}{3000}\left( \dfrac{1}{I} + \dfrac{1}{3000-I} \right) = \dfrac{3}{10000} dt$

$\ln(I) - \ln(3000-I) = \dfrac{9}{10}t + C$

$\ln \left( \dfrac{I}{3000-I} \right) = \dfrac{9}{10} t + C$

$\dfrac{I}{3000-I}  = C_2 e^{9t/10}$

$I = \dfrac{3000 C_2 e^{9t/10}}{1 + C_2 e^{9t/10}} = \dfrac{3000}{1 + D e^{-9t/10}}$.

Now we substitute the initial value $I(0) = 30$ to get

$30 = \dfrac{3000}{D+1}$,

so that $D = 99$. Thus the solution is

$I = \dfrac{3000}{I + 99e^{-9t/10}}$.
