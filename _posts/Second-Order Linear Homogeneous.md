The general linear second-order constant coefficient differential equation is
$$ay''(t) + by'(t) + cy(t) = f(t)$$
for constants $a,b,$ and $c$, where $a \ne 0$. We are only concerned with the case where $a,b$, and $c$ are real numbers.
When $f(t)$ is the constant function $0$, the equation is called a homogeneous differential equation:
$$ay'' + by' + cy = 0$$
We will discuss how to solve this equation now and save the general case for later.

To explain the procedure for solving the differential equation (*), we need a definition.

Definition: Two functions $y_1(t)$ and $y_2(t)$ are said to be linearly independent on an interval $I$ if neither of them is a constant multiple of the other. Otherwise, they are linearly dependent.

Example: $e^{2t}$ and $e^{3t}$ are linearly independent.

Example: $e^t$ and $t e^t$ are linearly independent.

Example: $2e^t$ and $3t^t$ are linearly dependent because $3t^t = \frac{3}{2} \cdot 2 e^t$.

Having defined linear independence, we can state the following theorem:

Theorem: If $y_1$ and $y_2$ are linearly independent solutions to $(*)$, then the general solution to $(*)$ is
$$
y = C_1 y_1 + C_2 y_2
$$
for any constants $C_1$ and $C_2$.

The theorem says that to solve $(*)$, we jsut need to find two linearly independent solutions. How do we find these? This is the equation we will now answer.

Starting from


$$ay'' + by' + cy = 0,$$


the first step is to write down what is called the auxiliary equation,
$$
ar^2 + br + c=0.
$$
The next step is to find the roots of the equation. There are three cases.

Case 1: If we get $2$ distinct real roots $r_1$ and $r_2$ (distinct means that $r_1 \ne r_2$), then $y_1(t) = e^{r_1 t}$ and $y_2(t) = e^{r_2 t}$ are linearly independent solutions to $(*)$.

Case 2: If we get a repeated root $r$, then $y_1 = e^{rt}$ and $y_2 = t e^{rt}$ are linearly independent solutions to $(*)$.

Case 3: If we get two complex conjugate roots $\alpha \pm i \beta$ (meaning that one of the roots is $r_1 = \alpha + i \beta$ and the other root is $r_2 = \alpha - i \beta$), then $y_1 = e^{\alpha t} \cos(\beta t)$ and $y_2 = e^{\alpha t} \sin(\beta t)$ are two linearly independent solutions to $(*)$.

This gives a complete answer to how to solve $(*)$. We find $y_1$ and $y_2$ using the steps above, and then the general solution is $y = C_1 y_1 + C_2 y_2$.

It is not too difficult to check that the $y_1$ and $y_2$ are solutions to $(*)$ in each of the three cases. Remember that to check that a function is a solution to a DE, all you have to do is to check that the DE is satisfied. But we still have the question of how anyone would be able to come up with these $y_1$ and $y_2$ if they didn't know that these would work in advance. For Case 1 it's not that hard to imagine how someone would come up with $e^{rt}$ as a solution (if $r$ is a root of the auxiliary equation). Just take the derivative to get $y' = re^{rt}$ and then differentiate again to get $y'' = r^2 e^{rt}$. Then observe that $ay'' + by' + cy = a r^2 e^{rt} + br e^{rt} + c e^{rt} = e^{rt}(ar^2 + br + c)$, and since $r$ is a root, $ar^2 + br+c=0$, so $ay'' + by' + cy = 0$. To see where $y_1$ and $y_2$ in case 3 come from, we'll need to learn more about the complex exponential $e^{z}$ where $z$ is a complex number.

For the remainder of this lecture, we will give some examples.
