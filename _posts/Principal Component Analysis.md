In this section, we give a brief overview of principal component analysis. 

Recall that the general quadratic form in two variables
$ax_1 + bx_1 x_2 + c x_2^2$
is equal to $\begin{bmatrix}
    x_1 & x_2
\end{bmatrix} \begin{bmatrix}
    a & b/2 \\
    b/2 & c
\end{bmatrix}
\begin{bmatrix}
    x_1 \\
    x_2
\end{bmatrix}.$
The matrix in the middle is a symmetric matrix; we'll call it $S$. It has a diagonalization
$S = Q \Lambda Q^{-1}$
where $Q$ is orthogonal and $\Lambda$ is diagonal:
$Q = [\textbf u_1 \ \textbf u_2] \quad \Lambda = \begin{bmatrix}
    \lambda_1 & \ \\
    \ & \lambda_2
\end{bmatrix}$
with $\textbf u_1,\textbf u_2$ orthogonal unit vectors. Thus, $\textbf u_1$ and $\textbf u_2$ are orthonormal eigenvectors of $A$, with eigenvalues $\lambda_1$ and $\lambda_2$. Furthermore, the $\lambda_i$'s are real. We arrange the $\lambda_i$'s so that $\lambda_1 \ge \lambda_2$.

Now we use $\textbf u_1$ and $\textbf u_2$ to create new axes. In terms of the variables $u_1$ and $u_2$, the quadratic form $z(x_1,x_2) = ax_1^2 + bx_1 x_2 + c x_2^2$ is equal to $z(x_1,x_2) = \lambda_1 u_1^2 + \lambda_2 u_2^2.$ Then $\lambda_1$ is the largest value of $z$ on the unit circle and $\lambda_2$ is the least value of $z$ on the unit circle.

We will apply these facts to a data set. Suppose there are six people, and two quantities, Quantity 1 and Quantity 2, are measured. We get the following matrix of observations $A = \begin{bmatrix}
    19 & 22 & 6 & 3 & 2 & 20 \\
    12 & 6 & 9 & 15 & 13 & 5 \end{bmatrix}$
Given a vector $\langle t_1,...,t_N \rangle$, we define its \textbf{sample mean} to be 
$m = \dfrac{1}{N}(t_1+ \dots + t_N)$
and the \textbf{sample variance} to be 
$\dfrac{1}{N-1}\sum_{i=1}^N (t_i-m)^2 = \dfrac{1}{N} \langle t_1-m,...,t_N-m \rangle \cdot \langle t_1-m,...,t_N-m \rangle.$
For example, in row 1, $N=6$, and
$m = \dfrac{1}{6}(19+22+6+3+2+20)=12.$
In row 2, $N=6$ and $m=10$.

We form the matrix $B$ by subtracting the row means from each row:
$B = \begin{bmatrix}
    7 & 10 & -6 & -9 & -10 & 8 \\
    2 & -4 & -1 & 5 & 3 & -5
\end{bmatrix}$
Suppose that $\textbf u$ and $\textbf v$ are vectors in $\textbf R^N$ with mean $0$. We define the sample covariance of $\textbf u$ and $\textbf v$ to be
$\dfrac{1}{N-1} \textbf u \cdot \textbf v.$
Notice that the sample covariance of $\textbf u$ and $\textbf u$ is just the sample variance of $\textbf u$.

We define the \textbf{sample covariance matrix} to be 
$S = [s_{ij}]=[\text{Cov}(\textbf u_i,\textbf u_j)].$
Then $S = \dfrac{1}{N-1}BB^T.$
Notice that $S$ is symmetric in general. In the example above,
$S = \begin{bmatrix}
    86 & -27 \\
    -27 & 16
\end{bmatrix}$
By definition, the sample variance of $c\textbf u + d\textbf v$ is $\dfrac{1}{N-1}(c\textbf u + d\textbf v) \cdot (c\textbf u + d \textbf v).$ Now $c\textbf u + d \textbf v$ is precisely
\[
\begin{bmatrix}
    c & d
\end{bmatrix} B,
\]
so the sample variance of $c\textbf u + d \textbf v$ is
\[
\dfrac{1}{N-1}[c \ d] B B^T \begin{bmatrix}
    c \\
    d
\end{bmatrix},
\]
a quadratic form! Let $\lambda_1$ and $\lambda_2$ be the eigenvalues of $S$, with $\lambda_1 \ge \lambda_2$. Suppose we restrict $(c,d)$ to be a unit vector. By what we have seen:

- The largest sample variance is $\lambda_1$, occurring at $\textbf u_1$;
- The least sample variance is $\lambda_2$, occurring at $\textbf u_2$.

The total variance is just the sample variance of $\u$ plus the sample variance of $\textbf v$. This is the sum of the diagonal entries of the sample covariance matrix. In other words, it's the \textit{trace} of the sample covariance matrix. By the general theory, this is the sum of the eigenvalues. The total variance of the data is $\lambda_1 + \lambda_2$. We can phrase what we've found as follows:

- Out of all possible unit vectors, the direction $\textbf u_1$ captures the largest amount of variance in the data.
- The direction $\textbf u_2$ captures the next largest amount of variance in the data in the possible directions orthogonal to $\textbf u_1$.
- The percentage of the total variance captured by the direction $\textbf u_i$ is $\dfrac{\lambda_i}{\sum_{j=1}^N \lambda_j}$.

In this scenario, we get
$\textbf u_1 = \begin{bmatrix}
    .95 \\
    -.32
\end{bmatrix}, \quad \lambda_1=95.2$
and
$\textbf{u}_2 = \begin{bmatrix}
    .32 \\
    .95
\end{bmatrix}, \quad \lambda_2 = 6.8.$
The total variance in the data is $95.2+6.8=102$. (Check that this is, in fact, the sum of the diagonal entries of $S$!)

The direction $\textbf u_1$ captures $\dfrac{95.2}{102} \approx 93.3\%$ of the total variance. The direction $\textbf  u_2$ captures approximately $6.7\%$ of the total variance.

We call $\textbf u_1$ and $\textbf u_2$ the \textbf{principal components} of the data (in the matrix of observations $A$). The \textbf{first principal component} is the eigenvector corresponding to the largest eigenvalue of the sample covariance matrix $S$, the \textbf{second principal component} is the eigenvector corresponding to the second largest eigenvalue, and so on. \textit{Principal component analysis} is based on the spectral theorem for symmetric matrices.

We have learned about lines of best fit using least squares. Principal component analysis is equivalent to something called orthogonal regression, as we now explain. Recall that if $B$ has row means of $0$, we have the sample covariance matrix $S = \dfrac{1}{N-1}BB^T$. Suppose that $\textbf u$ is a vector in $\textbf R^N$. Then
\begin{align*}
    \textbf u^T S\textbf u &= \dfrac{1}{N-1} (\begin{bmatrix}
    x_1 & x_2 
    \end{bmatrix}\begin{bmatrix}
    \textbf{b}_1 & \textbf{b}_2 & \dots & \textbf{b}_N
    \end{bmatrix}) \left([x_1 \ x_2][\textbf{b}_1 \ \textbf{b}_2 \ \dots \ \textbf{b}_N]\right)^T \\
    &= \dfrac{1}{N-1}[\textbf{b}_1 \cdot \u \ \dots \textbf{b}_N \cdot \textbf u]\begin{bmatrix}
    \textbf{b}_1 \cdot \u \\
    \vdots \\
    \textbf{b}_N \cdot \u
    \end{bmatrix} \\
    &= \dfrac{1}{N-1}\sum_{i=1}^N (\textbf{b}_i \cdot \textbf u)^2.
\end{align*}
Now suppose that $\u$ is a unit vector. Then $\sum_{i=1}^N (\textbf{b}_i \cdot \textbf u)^2$ is the sum of the squares of the lengths of the projections of the $\textbf{b}_i$ on the line spanned by $\textbf u$.

Notice that $||\textbf{b}_i||^2 = (\textbf{b}_i \cdot \textbf u)^2 + (\textbf{b}_i-\textbf{b}_i \cdot \textbf u)^2$
expresses the square of the magnitude of $\textbf{b}_i$ as the square of the length of the projection of $\textbf{b}_i$ onto $\textbf u$ and the square of the distance from $\textbf{b}_i$ to the line spanned by $\textbf u$. Therefore,
$\sum_{i=1}^N ||\textbf{b}_i||^2 = \sum_{i=1}^N (\textbf{b}_i \cdot \textbf u)^2 + \sum_{i=1}^N \text{dist}(\textbf{b}_i,\ell_\textbf u)^2.$
Since the left side is a fixed constant (because the $\textbf{b}_i$'s are given, we see that maximizing $\sum_{i=1}^N (\textbf{b}_i \cdot \u)^2$ is equivalent to minimizing $\sum_{i=1}^N \text{dist}(\textbf{b}_i,\ell_\textbf u)^2$. But maximizing $\sum_{i=1}^N (\textbf{b}_i \cdot \textbf u)^2$ is equivalent to maximizing $\textbf u^T S\textbf u$! We have seen that the $\textbf u$ that does this is the first principal component. Therefore, the line $t \textbf u$ is the best approximation to the data, in the sense that the sum of the squares of the \textit{orthogonal} distances to the line is minimized. For this reason, principal component analysis is equivalent to what is termed \textit{orthogonal regression}.
