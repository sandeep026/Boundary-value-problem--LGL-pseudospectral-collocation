# Solving boundary value problems using pseudospectral method

## Requirements

## Problem description

Consider the following boundary value problem from [^1] in equation 1 and its boundary conditione are provided in equation 2.

$$ 
\begin{equation}
\ddot{x}-t\dot{x}-x=0
\end{equation}
$$

$$ 
\begin{equation}
x(t=-1)=x(t=1)=1
\end{equation}
$$

## Analytical solution

The system has the solution $$x(t)=\exp(\frac{t^2-1}{2})$$

## Numerical solution

In order to solve the system  numerically, the problem is discretized using pseudospectral method. $x(t)$ is approximated using a global polynomial whose values are defined at the LGL collocation nodes. This polynomial is differentiated to the required degree and constraints are imposed. These include the boundary conditions and the satisfaction of the dynamics at the collocation points. Satifying the BC and dynamics at -1 and 1 leads to a overdetermined system. Hence, the BC are only imposed at the end points and dynamics constraints are ignored. This leads to a system of equation with equal number of variables and equations. Depending on the dynamics, linear/nonlinear system of equation are required to be solved.

## Implementation

In the code, the boundary conditions and  the dynamics are treated as nonlinear constraints by solver "IPOPT" and the objective it set to 0.

## Results

The numerical and analytical solution are identical as shown in the figure below. In addition, the spectral convergence of the method is also additional verified by increasing the grid size progressively.

![image](https://github.com/sandeep026/Boundary-value-problem--LGL-pseudospectral-collocation/assets/16457676/5064a0f2-45b0-46ea-9758-6516a3e98957)

![image](https://github.com/sandeep026/Boundary-value-problem--LGL-pseudospectral-collocation/assets/16457676/1b81e44a-6087-42e4-b34b-9bb81d2b0a6c)

![image](https://github.com/sandeep026/Boundary-value-problem--LGL-pseudospectral-collocation/assets/16457676/5b3b9bfb-1d86-4785-85aa-7fc8b9240e06)

## References

[^1]: Wang, L. L., Samson, M. D., & Zhao, X. (2014). A well-conditioned collocation method using a pseudospectral integration matrix. SIAM Journal on Scientific Computing, 36(3), A907-A929.




