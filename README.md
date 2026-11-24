# Ratio-Data

This dataset is an orbit diagram / bifurcation simulation of the classic **Ricker map** (exponential logistic model), defined by:

$$y_{n+1} = y_n \exp\big(r(1 - y_n)\big)$$

where $x$ represents the intrinsic growth rate parameter $r$, and the $299$ points per $x$ represent iterated states $y_n$ on the attractor (to numerical precision, consecutive columns satisfy $|y_{n+1} - y_n e^{r(1-y_n)}| < 10^{-14}$).

---

### Structure & Dynamical Regimes

1. **Fixed-Point Regime ($0 < r \le 2.0$):**
   * The fixed point $y^* = 1$ is globally stable.
   * Linearizing around $y^* = 1$ gives the multiplier $\lambda = f'(1) = 1 - r$.
   * As long as $|\lambda| < 1 \iff 0 < r < 2$, the iterations converge monotonically (for $r < 1$) or via damped oscillations (for $1 < r < 2$) to $y^* = 1$.

2. **Period-Doubling Bifurcation ($r = 2.0$):**
   * At $r = 2$, $\lambda = -1$, triggering a supercritical flip (period-doubling) bifurcation.
   * For $2.0 < r \lesssim 2.692$, the system alternates between two values $\{y_A, y_B\}$ satisfying $y_A + y_B = 2.0$ (centered symmetrically around the unstable fixed point $1$).

3. **Cascade and Chaos ($r \gtrsim 2.692$ up to $r = 4.0$):**
   * The system follows the Feigenbaum period-doubling cascade into deterministic chaos.
   * Fluctuations widen significantly: near $r = 4.0$, state values swing between deep crashes ($y \sim 5 \times 10^{-7}$) and sharp overshoots ($y \approx 5.02$), while maintaining a long-term time-average $\langle y \rangle \approx 1$.
