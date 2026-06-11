# Problem Set 10 – Solutions

## Task 1 – Time dilation

### Problem Statement
A spacecraft is moving with a velocity $v = 0.8c$. Calculate the Lorentz factor, determine the time passed on Earth if 5 years pass on the ship, find the percentage effect of the dilation, analyze the limit $v \to c$, and interpret the result physically.

### Theory
Time dilation describes how time is measured differently by observers in relative motion. The proper time $\Delta t_0$ is measured in the rest frame of the moving object. The dilated time $\Delta t$ measured by a stationary observer is given by

$$
\Delta t = \gamma \Delta t_0
$$

The Lorentz factor $\gamma$ dictates the magnitude of relativistic effects and depends on the relative velocity $v$.

### Step-by-Step Solution
First, compute the Lorentz factor for $v = 0.8c$:

$$
\begin{align}
\gamma &= \frac{1}{\sqrt{1-\frac{v^2}{c^2}}} \\
       &= \frac{1}{\sqrt{1-0.8^2}} \\
       &= \frac{1}{\sqrt{1-0.64}} \\
       &= \frac{1}{\sqrt{0.36}} \\
       &= \frac{1}{0.6} \\
       &= \frac{5}{3} \approx 1.667
\end{align}
$$

Next, calculate the time elapsed on Earth. The proper time on the ship is $\Delta t_0 = 5\,\mathrm{years}$.

$$
\Delta t = \frac{5}{3} \times 5 = \frac{25}{3} \approx 8.33\,\mathrm{years}
$$

To find the percentage effect of the dilation, compute the relative difference:

$$
\text{Effect} = \frac{8.33 - 5.00}{5.00} \times 100\% = 66.7\%
$$

In the limit $v \to c$, the ratio $v^2/c^2 \to 1$. Consequently, the denominator of the Lorentz factor approaches zero.

$$
\lim_{v \to c} \gamma = \infty
$$

### Final Result
- Lorentz factor: $\gamma = 1.667$
- Time on Earth: $8.33\,\mathrm{years}$
- Percentage effect: $66.7\%$
- Limit $v \to c$: $\gamma \to \infty$, causing $\Delta t \to \infty$.

### Interpretation
An observer on Earth measures the moving clock on the spacecraft to be ticking slower. If the spacecraft could theoretically reach the speed of light, an infinite amount of time would pass on Earth for any non-zero duration on the ship, effectively stopping time in the moving frame relative to the stationary observer.

---

## Task 2 – Length contraction

### Problem Statement
A rocket with a proper length $L_0 = 120\,\mathrm{m}$ moves with a velocity of $0.6c$. Calculate the observed length, the percentage of contraction, determine if the observer in the rocket sees the contraction, identify an invariant quantity, and interpret the "rocket in a tunnel" paradox.

### Theory
Length contraction dictates that an object's length measured in a frame where it is moving is shorter than its proper length $L_0$ measured in its rest frame. The relation is

$$
L = \frac{L_0}{\gamma}
$$

### Step-by-Step Solution
Calculate the Lorentz factor for $v = 0.6c$:

$$
\begin{align}
\gamma &= \frac{1}{\sqrt{1 - 0.6^2}} \\
       &= \frac{1}{\sqrt{1 - 0.36}} \\
       &= \frac{1}{0.8} = 1.25
\end{align}
$$

Calculate the contracted length $L$ observed by the stationary observer:

$$
L = \frac{120}{1.25} = 96\,\mathrm{m}
$$

Determine the percentage of contraction:

$$
\text{Contraction} = \frac{120 - 96}{120} \times 100\% = 20\%
$$

### Final Result
- Observed length: $96\,\mathrm{m}$
- Percentage of contraction: $20\%$
- The observer inside the rocket measures the proper length ($120\,\mathrm{m}$) and does not observe the rocket contracting.
- Invariant quantities across inertial frames include proper length, proper time, and the spacetime interval.

### Interpretation
The "rocket in a tunnel" paradox involves a $120\,\mathrm{m}$ rocket traveling through a $100\,\mathrm{m}$ tunnel. A stationary observer sees the rocket contract to $96\,\mathrm{m}$, fitting entirely inside. The rocket observer sees the tunnel contract and concludes the rocket cannot fit. The paradox is resolved by the relativity of simultaneity: the front and back ends of the rocket aligning with the tunnel entrances are not simultaneous events in both reference frames.

---

## Task 3 – Lorentz transformation

### Problem Statement
Given events in frame $S$: $x_1 = 0, t_1 = 0$ and $x_2 = 900\,\mathrm{m}, t_2 = 4\,\mu\mathrm{s}$. Frame $S'$ moves with $v=0.6c$. Apply the transformation, calculate coordinates of the second event in $S'$, verify if the order of events can change, and calculate the spacetime interval to verify its invariance.

### Theory
The Lorentz transformation connects the spacetime coordinates of two inertial frames:

$$
x' = \gamma (x - vt)
$$

$$
t' = \gamma \left(t - \frac{vx}{c^2}\right)
$$

The spacetime interval $s^2$ is an invariant scalar quantity:

$$
s^2 = (c \Delta t)^2 - (\Delta x)^2
$$

### Step-by-Step Solution
The velocity is $v = 0.6c = 1.8 \times 10^8\,\mathrm{m/s}$. The Lorentz factor is $\gamma = 1.25$. 

For Event 1 ($x_1=0, t_1=0$), the coordinates in $S'$ remain $x_1'=0, t_1'=0$.

For Event 2 ($x_2 = 900\,\mathrm{m}, t_2 = 4 \times 10^{-6}\,\mathrm{s}$):

$$
\begin{align}
x_2' &= 1.25 \left( 900 - (1.8 \times 10^8)(4 \times 10^{-6}) \right) \\
     &= 1.25 (900 - 720) \\
     &= 1.25 (180) = 225\,\mathrm{m}
\end{align}
$$

$$
\begin{align}
t_2' &= 1.25 \left( 4 \times 10^{-6} - \frac{(1.8 \times 10^8)(900)}{(3 \times 10^8)^2} \right) \\
     &= 1.25 \left( 4 \times 10^{-6} - \frac{1.62 \times 10^{11}}{9 \times 10^{16}} \right) \\
     &= 1.25 (4 \times 10^{-6} - 1.8 \times 10^{-6}) \\
     &= 1.25 (2.2 \times 10^{-6}) = 2.75\,\mu\mathrm{s}
\end{align}
$$

Calculate the spacetime interval in frame $S$:

$$
\begin{align}
s^2 &= (3 \times 10^8 \times 4 \times 10^{-6})^2 - 900^2 \\
    &= 1200^2 - 900^2 \\
    &= 1440000 - 810000 \\
    &= 630000\,\mathrm{m}^2
\end{align}
$$

Verify the interval in frame $S'$:

$$
\begin{align}
s'^2 &= (3 \times 10^8 \times 2.75 \times 10^{-6})^2 - 225^2 \\
     &= 825^2 - 225^2 \\
     &= 680625 - 50625 \\
     &= 630000\,\mathrm{m}^2
\end{align}
$$

### Final Result
- Coordinates in $S'$: $x_2' = 225\,\mathrm{m}, t_2' = 2.75\,\mu\mathrm{s}$.
- Spacetime interval: $s^2 = s'^2 = 630000\,\mathrm{m}^2$.
- The interval is strictly positive ($c^2 \Delta t^2 > \Delta x^2$), defining a timelike interval. The temporal order of events cannot change.

### Interpretation
Because $s^2 > 0$, the two events are causally connected. A signal traveling slower than light can pass between them. The invariant nature of $s^2$ demonstrates that while different observers measure varying times and distances, the fundamental geometric separation in spacetime remains constant.

---

## Task 4 – Twin paradox

### Problem Statement
Twin A stays on Earth. Twin B travels at $0.9c$ for 10 years (Earth time) and returns. Calculate proper time, determine the age difference, assess the symmetry of reference frames, identify where symmetry breaks, and interpret geometrically.

### Theory
The traveling twin experiences time dilation. Proper time $\Delta t_0$ accumulated by the moving twin is given by:

$$
\Delta t_0 = \frac{\Delta t}{\gamma}
$$

### Step-by-Step Solution
Calculate the Lorentz factor for $v = 0.9c$:

$$
\begin{align}
\gamma &= \frac{1}{\sqrt{1 - 0.9^2}} \\
       &= \frac{1}{\sqrt{0.19}} \approx 2.294
\end{align}
$$

Calculate the proper time of Twin B during the $10\,\mathrm{years}$ elapsed on Earth:

$$
\Delta t_0 = \frac{10}{2.294} \approx 4.36\,\mathrm{years}
$$

Calculate the age difference upon return:

$$
\text{Difference} = 10 - 4.36 = 5.64\,\mathrm{years}
$$

### Final Result
- Proper time of Twin B: $4.36\,\mathrm{years}$.
- Twin B is $5.64\,\mathrm{years}$ younger upon return.
- The symmetry of the reference frames is incomplete. Symmetry is broken during acceleration (turning around).

### Interpretation
In Minkowski spacetime, proper time is the arc length of a worldline. The straight worldline (Twin A) represents the maximum proper time between two spacetime events. Twin B follows a bent path (due to acceleration), which corresponds to a shorter proper time. The acceleration phase breaks the inertial symmetry, definitively identifying Twin B as the traveler.

---

## Task 5 – Muons in the atmosphere

### Problem Statement
Muons are created at an altitude of $10\,\mathrm{km}$ with proper lifetime $\tau_0 = 2.2\,\mu\mathrm{s}$ and velocity $v = 0.995c$. Calculate the Lorentz factor, the mean lifetime in Earth's frame, the average distance traveled, and determine if they would reach the surface without relativity.

### Theory
Subatomic particles moving near the speed of light exhibit macroscopic time dilation and length contraction, allowing them to travel distances far exceeding their classical limits before decaying.

### Step-by-Step Solution
Compute the Lorentz factor:

$$
\begin{align}
\gamma &= \frac{1}{\sqrt{1 - 0.995^2}} \\
       &\approx \frac{1}{\sqrt{1 - 0.990025}} \\
       &\approx \frac{1}{\sqrt{0.009975}} \approx 10.01
\end{align}
$$

Compute the mean lifetime in the Earth's frame:

$$
\begin{align}
\tau &= \gamma \tau_0 \\
     &= 10.01 \times 2.2\,\mu\mathrm{s} \\
     &\approx 22.02\,\mu\mathrm{s}
\end{align}
$$

Calculate the average distance traveled in the Earth's frame:

$$
\begin{align}
d &= v \tau \\
  &= (0.995 \times 3 \times 10^8) \times (22.02 \times 10^{-6}) \\
  &\approx 6573\,\mathrm{m} \approx 6.57\,\mathrm{km}
\end{align}
$$

Calculate the classical distance without relativistic time dilation:

$$
\begin{align}
d_{\text{classical}} &= v \tau_0 \\
                     &= (0.995 \times 3 \times 10^8) \times (2.2 \times 10^{-6}) \\
                     &\approx 656.7\,\mathrm{m}
\end{align}
$$

### Final Result
- Lorentz factor: $10.01$
- Mean lifetime on Earth: $22.02\,\mu\mathrm{s}$
- Average distance traveled: $\approx 6.57\,\mathrm{km}$
- Without relativity, muons would only travel $\approx 657\,\mathrm{m}$ and would not reach the Earth's surface.

### Interpretation
Relativistic time dilation extends the effective lifetime of high-speed muons, enabling a significant fraction to traverse the $10\,\mathrm{km}$ atmosphere and be detected at the surface. From the muon's perspective, atmospheric length contraction reduces the $10\,\mathrm{km}$ distance to approximately $1\,\mathrm{km}$, allowing the journey to be completed within the proper lifetime of $2.2\,\mu\mathrm{s}$.

---

## Task 6 – Minkowski diagram

### Problem Statement
Implement the Lorentz transformation as a matrix. Draw the $ct$ and $x$ axes, $ct'$ and $x'$ axes, mark the light cone, allow velocity change, and geometrically interpret time dilation and length contraction (implementation via HTML requested, represented via matrix structure here).

### Theory
The Lorentz transformation linearly maps coordinates from frame $S$ to $S'$. In a two-dimensional spacetime $(ct, x)$, this mapping is represented mathematically by a transformation matrix.

### Step-by-Step Solution
The Lorentz transformation matrix $\Lambda$ operates on a spacetime coordinate vector:

$$
\begin{pmatrix}
ct' \\
x'
\end{pmatrix}
=
\begin{pmatrix}
\gamma & -\gamma \frac{v}{c} \\
-\gamma \frac{v}{c} & \gamma
\end{pmatrix}
\begin{pmatrix}
ct \\
x
\end{pmatrix}
$$

To create an HTML/JavaScript simulation:
1. Define a canvas coordinate system.
2. The $x$-axis and $ct$-axis are orthogonal straight lines.
3. The light cone consists of lines $x = ct$ and $x = -ct$ (drawn at $45^\circ$).
4. The $x'$-axis has a slope of $v/c$ relative to the $x$-axis.
5. The $ct'$-axis has a slope of $v/c$ relative to the $ct$-axis (or $c/v$ relative to $x$).

