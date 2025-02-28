# 25.1 Mathed


**Goal: solve for the number of rounds to get to timecap**

*assuming the same pace is kept throughout

Notation:
- $\Delta t_b$ base time to complete 3 burpees + 3 clean to overhead
- $\Delta t_w$ time to complete 30 feet walking lunge
- $T_c$ is the timecap

The time elapsed for round $i>0$ is therefore $T_i = i\Delta t_b + \Delta t_w$

And therefore the total time for all n rounds cumulatively is:

$$
\begin{aligned}
T_n &= \sum_{i=1}^n \left[i\Delta t_b + \Delta t_w\right] \\
&= n\Delta t_w +  \sum_{i=1}^n i\Delta t_b \\
&= n\Delta t_w +  \sum_{i=1}^{n+1} (i-1)\Delta t_b
\end{aligned}
$$

The second part is an arithmetic series. The sum of an arithmetic series is:

$$
\begin{aligned}
S &= \sum_{i=1}^m a_0 + (i-1)d \\
&= \frac{m}{2} (2a_0 + (m-1)d)
\end{aligned}
$$

In our case, $a\leftarrow 0$, $d \leftarrow \Delta t_b$, $m\leftarrow n+1$.

$$
S_b = \frac{n+1}{2} (n \Delta t_b) \\
$$

We have to factor in the walking lunges now to get the total elapsed time

$$
\begin{aligned}
S_t &= S_b + S_w \\
&= n\Delta t_w + \frac{n+1}{2} (n \Delta t_b)
\end{aligned}
$$


This is a quadratic equation that can be rewritten as

$$
0 = \frac{\Delta t_b}{2}n^2 + \left(\Delta t_w + \frac{\Delta t_b}{2}\right)n - S_t
$$

Meaning the solution for rounds with $S_n \leftarrow T_c$ is

$$
n = \frac{-\left(\Delta t_w + \frac{\Delta t_b}{2}\right) + \sqrt{\left(\Delta t_w + \frac{\Delta t_b}{2}\right)^2 + 2 \Delta t_b T_c}}{\Delta t_b}
$$
