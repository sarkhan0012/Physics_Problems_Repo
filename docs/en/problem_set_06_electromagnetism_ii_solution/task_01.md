# Problem Set 06 – Electromagnetism II Solutions

# Task 01 – Lorentz force

## Problem Statement

Given the following data for a particle: magnetic field $\vec{B} = (0, 0, 1)\ \mathrm{T}$, velocity $\vec{v} = (2, 3, 0)\ \mathrm{m/s}$, and charge $q = 1\ \mathrm{mC}$. 
Determine the Lorentz force $\vec{F}$, the equation of motion (starting at the origin), the magnitude $|\vec{F}|$, the work done by the magnetic force, the trajectory radius for $m = 0.01\ \mathrm{kg}$, and the effect of doubling $B$ on the radius.

## Theory

The magnetic component of the Lorentz force acting on a moving charge is given by the cross product of velocity and magnetic field:

$$
\vec{F} = q(\vec{v} \times \vec{B})
$$

According to Newton's second law, this force dictates the acceleration of the particle:

$$
m\frac{d\vec{v}}{dt} = \vec{F}
$$

Because the magnetic force is always perpendicular to the velocity vector, it acts as a centripetal force, causing uniform circular motion without changing the kinetic energy. The radius of this circular trajectory is derived by equating the magnetic force magnitude to the required centripetal force:

$$
qvB = \frac{mv^2}{r}
$$

## Step-by-Step Solution

1. **Determine the Lorentz force:**
Calculate the cross product $\vec{v} \times \vec{B}$:

$$
\vec{v} \times \vec{B} = (3 \cdot 1 - 0 \cdot 0)\hat{i} - (2 \cdot 1 - 0 \cdot 0)\hat{j} + (2 \cdot 0 - 3 \cdot 0)\hat{k} = (3, -2, 0)\ \mathrm{m/s \cdot T}
$$

Multiply by the charge $q = 10^{-3}\ \mathrm{C}$:

$$
\vec{F} = 10^{-3} \cdot (3, -2, 0) = (3 \cdot 10^{-3}, -2 \cdot 10^{-3}, 0)\ \mathrm{N}
$$

2. **Solve the equation of motion:**
The motion is restricted to the $xy$-plane because $\vec{B}$ is along the $z$-axis. The cyclotron frequency is:

$$
\omega = \frac{qB}{m} = \frac{10^{-3} \cdot 1}{0.01} = 0.1\ \mathrm{rad/s}
$$

Solving the coupled differential equations $\ddot{x} = \omega \dot{y}$ and $\ddot{y} = -\omega \dot{x}$ with initial conditions $v_{x0} = 2$, $v_{y0} = 3$, $x(0)=0$, $y(0)=0$ yields:

$$
\begin{align}
x(t) &= 30 - 30\cos(0.1t) + 20\sin(0.1t) \\
y(t) &= -20 + 30\sin(0.1t) + 20\cos(0.1t) \\
z(t) &= 0
\end{align}
$$

3. **Calculate the magnitude $|\vec{F}|$:**

$$
|\vec{F}| = \sqrt{(3 \cdot 10^{-3})^2 + (-2 \cdot 10^{-3})^2} = 10^{-3}\sqrt{9 + 4} = \sqrt{13} \cdot 10^{-3}\ \mathrm{N}
$$

4. **Work done by magnetic force:**
Work is defined as $W = \int \vec{F} \cdot d\vec{r}$. Since $\vec{F}$ is perpendicular to $d\vec{r}$ (and $\vec{v}$) at all times, $\vec{F} \cdot d\vec{r} = 0$. The work done is exactly $0$.

5. **Determine the radius of the trajectory:**
The velocity in the $xy$-plane is $v = \sqrt{2^2 + 3^2} = \sqrt{13}\ \mathrm{m/s}$. 

$$
r = \frac{mv}{qB} = \frac{0.01 \cdot \sqrt{13}}{10^{-3} \cdot 1} = 10\sqrt{13}\ \mathrm{m}
$$

6. **Change in $r$ when $B$ is doubled:**
From the radius formula $r = \frac{mv}{qB}$, $r$ is inversely proportional to $B$. Doubling $B$ reduces $r$ by a factor of 2.

## Final Result

- $\vec{F} = (3, -2, 0) \cdot 10^{-3}\ \mathrm{N}$
- $x(t) = 30 - 30\cos(0.1t) + 20\sin(0.1t)$, $y(t) = -20 + 30\sin(0.1t) + 20\cos(0.1t)$
- $|\vec{F}| \approx 3.61 \cdot 10^{-3}\ \mathrm{N}$
- Work done is $0\ \mathrm{J}$.
- Radius $r = 10\sqrt{13} \approx 36.1\ \mathrm{m}$.
- Radius becomes $r/2$ if $B$ is doubled.

## Interpretation

A constant magnetic field alters the trajectory of a charged particle without altering its kinetic energy. The force acts strictly as a turning mechanism. The inverse relationship between magnetic field strength and turning radius demonstrates that stronger fields constrain charged particles to tighter orbits, a principle fundamental to mass spectrometry and cyclotron accelerators.

---

# Task 02 – Velocity selection (crossed fields)

## Problem Statement

Crossed electric and magnetic fields are used to select particles with a specific velocity. Given $\vec{E} = (0, E, 0)$ and $\vec{B} = (0, 0, B)$, derive the condition for rectilinear motion, calculate $v_d$ for $E = 400\ \mathrm{V/m}$ and $B = 0.8\ \mathrm{T}$, determine if kinetic energy changes, and interpret the operating principle.

## Theory

A charged particle moving through regions containing both electric and magnetic fields experiences a total Lorentz force:

$$
\vec{F}_{net} = q(\vec{E} + \vec{v} \times \vec{B})
$$

For rectilinear, undeflected motion, the net force must be zero. This requires the electric force to perfectly cancel the magnetic force.

## Step-by-Step Solution

1. **Derive condition for rectilinear motion:**
Set the net force to zero:

$$
q\vec{E} + q(\vec{v} \times \vec{B}) = 0
$$

$$
\vec{E} = -(\vec{v} \times \vec{B})
$$

Given $\vec{E}$ is along $\hat{j}$ and $\vec{B}$ is along $\hat{k}$, the velocity $\vec{v}$ must be strictly along $\hat{i}$ to produce a cross product along $-\hat{j}$. Let $\vec{v} = (v_x, 0, 0)$.

$$
E\hat{j} = -(v_x\hat{i} \times B\hat{k}) = -(v_x B(-\hat{j})) = v_x B\hat{j}
$$

$$
v_x = \frac{E}{B}
$$

2. **Calculate $v_d$:**
Substitute the given values $E = 400\ \mathrm{V/m}$ and $B = 0.8\ \mathrm{T}$:

$$
v_d = \frac{400}{0.8} = 500\ \mathrm{m/s}
$$

3. **Does the kinetic energy change?**
No. In steady rectilinear motion, the net force is zero, meaning acceleration is zero. Since velocity is perfectly constant, the kinetic energy $E_k = \frac{1}{2}mv^2$ remains constant.

## Final Result

- Rectilinear condition: $v = \frac{E}{B}$
- Drift velocity: $v_d = 500\ \mathrm{m/s}$
- Kinetic energy change: Zero ($\Delta E_k = 0$).

## Interpretation

The velocity selector utilizes perfectly opposing fields. The electric force is velocity-independent, while the magnetic force is linearly dependent on velocity. Only at the specific velocity $v = E/B$ do these forces balance. Particles traveling faster are deflected by the dominant magnetic force, while slower particles are deflected by the dominant electric force, thus filtering out all but the desired velocity.

---

# Task 03 – Magnetic moment of a loop

## Problem Statement

A conducting loop with $N$ turns, area $S$, and current $I$ is in a uniform magnetic field $\vec{B}$. Define the magnetic moment $\vec{\mu}$, determine the torque $\vec{M}$, identify the angle for maximum torque, determine the potential energy $U$, and indicate stable/unstable positions.

## Theory

A current-carrying loop acts as a magnetic dipole. The interaction between this dipole and an external magnetic field creates a torque that attempts to align the dipole moment with the external field lines.

## Step-by-Step Solution

1. **Define the magnetic moment:**

$$
\vec{\mu} = NIS\hat{n}
$$

Where $\hat{n}$ is the unit normal vector to the loop area, determined by the right-hand rule with respect to the current direction.

2. **Determine the torque:**
The torque $\vec{M}$ (or $\vec{\tau}$) on a magnetic dipole in a magnetic field is the cross product of the magnetic moment and the field:

$$
\vec{M} = \vec{\mu} \times \vec{B}
$$

3. **Maximum torque angle:**
The magnitude of the torque is $M = \mu B \sin(\theta)$, where $\theta$ is the angle between $\vec{\mu}$ and $\vec{B}$. The function $\sin(\theta)$ is maximized at $\theta = 90^{\circ}$ (or $\frac{\pi}{2}\ \mathrm{rad}$).

4. **Determine potential energy $U$:**
The potential energy is defined by the dot product:

$$
U = -\vec{\mu} \cdot \vec{B} = -\mu B \cos(\theta)
$$

5. **Stable and unstable positions:**
Equilibrium occurs where torque is zero ($\theta = 0^{\circ}$ or $\theta = 180^{\circ}$).
- **Stable:** $\theta = 0^{\circ}$. $U = -\mu B$ (global minimum). Small perturbations result in a restoring torque.
- **Unstable:** $\theta = 180^{\circ}$. $U = +\mu B$ (global maximum). Small perturbations result in torque that drives the loop further away from this position.

## Final Result

- $\vec{\mu} = NIS\hat{n}$
- $\vec{M} = \vec{\mu} \times \vec{B}$
- Maximum torque at $\theta = 90^{\circ}$.
- $U = -\vec{\mu} \cdot \vec{B}$
- Stable position: $\vec{\mu}$ parallel to $\vec{B}$. Unstable position: $\vec{\mu}$ anti-parallel to $\vec{B}$.

## Interpretation

The loop behaves analogously to a compass needle in Earth's magnetic field. It possesses minimum potential energy when fully aligned with the external field, which naturally represents its stable equilibrium state. Mechanical work is required to rotate the loop out of this alignment.

---

# Task 04 – Rotating loop (induction)

## Problem Statement

A loop of area $S$ and $N$ turns rotates in a uniform magnetic field $\vec{B}$ with angular velocity $\omega$ around an axis perpendicular to $\vec{B}$. Determine the flux $\Phi(t)$, the EMF $\mathcal{E}(t)$, its amplitude $\mathcal{E}_0$, the dependence on $\omega$, and interpret the generation mechanism.

## Theory

Electromagnetic induction is governed by Faraday's Law, which states that a time-varying magnetic flux through a circuit induces an electromotive force (EMF) in that circuit:

$$
\mathcal{E} = -\frac{d\Phi}{dt}
$$

## Step-by-Step Solution

1. **Determine $\Phi(t)$:**
The magnetic flux is the dot product of the magnetic field and the area vector. For $N$ turns:

$$
\Phi(t) = N(\vec{B} \cdot \vec{S}) = NBS\cos(\theta(t))
$$

Assuming the loop starts at an angle of zero at $t=0$, $\theta(t) = \omega t$:

$$
\Phi(t) = NBS\cos(\omega t)
$$

2. **Determine $\mathcal{E}(t)$:**
Apply Faraday's Law by taking the time derivative of the flux:

$$
\begin{align}
\mathcal{E}(t) &= -\frac{d}{dt}[NBS\cos(\omega t)] \\
&= -NBS(-\omega\sin(\omega t)) \\
&= NBS\omega\sin(\omega t)
\end{align}
$$

3. **Calculate the amplitude $\mathcal{E}_0$:**
The amplitude is the maximum possible value of the time-varying function $\sin(\omega t)$, which is $1$. 

$$
\mathcal{E}_0 = NBS\omega
$$

4. **Dependence on $\omega$:**
The amplitude $\mathcal{E}_0$ is directly and linearly proportional to the angular velocity $\omega$. 

## Final Result

- $\Phi(t) = NBS\cos(\omega t)$
- $\mathcal{E}(t) = NBS\omega\sin(\omega t)$
- Amplitude $\mathcal{E}_0 = NBS\omega$
- $\mathcal{E}_0 \propto \omega$

## Interpretation

This system is the foundational model of an alternating current (AC) generator. The rotation mechanically alters the effective area exposed to the field lines, ensuring continuous flux variation. The linear dependence on $\omega$ demonstrates that spinning the generator faster not only increases the frequency of the AC voltage but also proportionally increases the peak voltage output.

---

# Task 08 – Self-induction

## Problem Statement

An RL circuit with $L=0.20\ \mathrm{H}$ and $R=5.0\ \Omega$ is powered by a DC voltage $U=12\ \mathrm{V}$. After reaching a steady state, the supply is disconnected at $t=0$, leaving the circuit without a source. Determine the steady current $I_0$, derive $I(t)$ and $U_L(t)$ after disconnection, calculate the stored magnetic energy, show it converts to Joule heat, and explain overvoltage.

## Theory

Inductors resist abrupt changes in current by inducing a counter-EMF proportional to the rate of change of the current:

$$
\mathcal{E}_L = -L\frac{dI}{dt}
$$

In an unpowered RL loop, Kirchhoff's voltage law dictates that the voltage across the inductor must equal the voltage drop across the resistor.

## Step-by-Step Solution

1. **Determine the steady current $I_0$:**
In a steady DC state, $dI/dt = 0$, so the inductor acts as a short circuit ($\mathcal{E}_L = 0$).

$$
I_0 = \frac{U}{R} = \frac{12}{5.0} = 2.4\ \mathrm{A}
$$

2. **Derive $I(t)$, $\tau$, and $U_L(t)$:**
After disconnection, KVL states:

$$
L\frac{dI}{dt} + IR = 0
$$

Separating variables and integrating from $I_0$ to $I(t)$:

$$
\int_{I_0}^{I} \frac{dI}{I} = -\int_{0}^{t} \frac{R}{L}dt
$$

$$
\ln\left(\frac{I}{I_0}\right) = -\frac{R}{L}t \implies I(t) = I_0 e^{-\frac{R}{L}t}
$$

The time constant is $\tau = \frac{L}{R} = \frac{0.20}{5.0} = 0.04\ \mathrm{s}$.
The current function is $I(t) = 2.4 e^{-25t}\ \mathrm{A}$.
The voltage across the coil is:

$$
U_L(t) = -L\frac{dI}{dt} = -L \left(-I_0 \frac{R}{L} e^{-\frac{R}{L}t} \right) = I_0 R e^{-\frac{t}{\tau}} = 12 e^{-25t}\ \mathrm{V}
$$

3. **Calculate initial stored energy:**

$$
W = \frac{1}{2}LI_0^2 = \frac{1}{2}(0.20)(2.4)^2 = 0.1 \cdot 5.76 = 0.576\ \mathrm{J}
$$

4. **Show energy converts to Joule heat:**
Integrate the power dissipated by the resistor $P(t) = I(t)^2 R$ from $t=0$ to $\infty$:

$$
\begin{align}
E_{heat} &= \int_{0}^{\infty} (I_0 e^{-\frac{t}{\tau}})^2 R dt \\
&= I_0^2 R \int_{0}^{\infty} e^{-\frac{2t}{\tau}} dt \\
&= I_0^2 R \left[ -\frac{\tau}{2} e^{-\frac{2t}{\tau}} \right]_{0}^{\infty} \\
&= I_0^2 R \left( 0 - \left(-\frac{\tau}{2}\right) \right) \\
&= I_0^2 R \frac{L}{2R} \\
&= \frac{1}{2}LI_0^2
\end{align}
$$

This perfectly matches the initial stored energy $W$.

## Final Result

- $I_0 = 2.4\ \mathrm{A}$
- $I(t) = 2.4 e^{-25t}\ \mathrm{A}$, $\tau = 0.04\ \mathrm{s}$, $U_L(t) = 12 e^{-25t}\ \mathrm{V}$
- $W = 0.576\ \mathrm{J}$
- Integral of $I^2R$ yields precisely $\frac{1}{2}LI_0^2$.

## Interpretation

An overvoltage phenomenon occurs because an instantaneous drop in current to zero would require $dt \to 0$, causing $dI/dt \to \infty$. To sustain the existing current, the collapsing magnetic field in the inductor generates a massive induced voltage (often visible as sparking at a switch). This energy is safely dissipated as thermal heat through the circuit's resistive components in a closed loop.