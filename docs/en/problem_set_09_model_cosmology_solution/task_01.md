# Task 01 – Ptolemy's Model

## Problem Statement

Describe the motion of a planet in the Ptolemaic geocentric model as a sum of motion along a main circle (deferent) and a secondary circle (epicycle). 
1. Write the parametric representation of the trajectory.
2. Derive the parametric equations.
3. Investigate the mathematical condition for retrograde motion to occur.
4. Determine the exact moments when the apparent direction of motion changes in angular projection.
5. Detail the parameters required for an interactive visualization.

## Theory

In the Ptolemaic system, planetary motion is modeled kinematically to explain the apparent complex paths of planets as observed from Earth. Earth is placed at the origin. The motion is decomposed into two superimposed circular uniform motions:
1. The **deferent**: A large circle centered on Earth with radius $R$ and angular velocity $\omega$.
2. The **epicycle**: A smaller circle with radius $r$ and angular velocity $\Omega$, whose center moves along the deferent.

The apparent angular velocity of the planet, as viewed from the origin, is the derivative of its ecliptic longitude $\varphi$. Retrograde motion occurs when this angular velocity becomes negative.

## Step-by-Step Solution

Let the position vector of the center of the epicycle be $\vec{R}(t)$ and the position vector of the planet relative to the center of the epicycle be $\vec{r}(t)$.

The Cartesian components of these vectors are:

$$
\vec{R}(t) = \begin{pmatrix} R \cos(\omega t) \\ R \sin(\omega t) \end{pmatrix}
$$

$$
\vec{r}(t) = \begin{pmatrix} r \cos(\Omega t) \\ r \sin(\Omega t) \end{pmatrix}
$$

The total position vector of the planet is the sum of these two vectors:

$$
\vec{p}(t) = \vec{R}(t) + \vec{r}(t)
$$

This gives the parametric equations of the trajectory:

$$
x(t) = R \cos(\omega t) + r \cos(\Omega t)
$$

$$
y(t) = R \sin(\omega t) + r \sin(\Omega t)
$$

To find the condition for retrograde motion, we must determine when the apparent angular velocity $\dot{\varphi}$ is less than zero. The polar angle $\varphi$ satisfies $\tan(\varphi) = \frac{y}{x}$. Differentiating with respect to time yields:

$$
\dot{\varphi} = \frac{x \dot{y} - y \dot{x}}{x^2 + y^2}
$$

The denominator is always positive, so the sign of $\dot{\varphi}$ depends entirely on the numerator $N(t) = x \dot{y} - y \dot{x}$. 

We compute the time derivatives of the coordinates:

$$
\dot{x}(t) = -R \omega \sin(\omega t) - r \Omega \sin(\Omega t)
$$

$$
\dot{y}(t) = R \omega \cos(\omega t) + r \Omega \cos(\Omega t)
$$

Substitute $x, y, \dot{x}, \dot{y}$ into the numerator:

$$
N(t) = (R \cos(\omega t) + r \cos(\Omega t))(R \omega \cos(\omega t) + r \Omega \cos(\Omega t)) - (R \sin(\omega t) + r \sin(\Omega t))(-R \omega \sin(\omega t) - r \Omega \sin(\Omega t))
$$

Expanding and applying the trigonometric identity $\cos(\alpha) \cos(\beta) + \sin(\alpha) \sin(\beta) = \cos(\alpha - \beta)$, we obtain:

$$
N(t) = R^2 \omega + r^2 \Omega + R r (\omega + \Omega) \cos((\Omega - \omega)t)
$$

Retrograde motion requires $N(t) < 0$. The minimum value of $N(t)$ occurs when $\cos((\Omega - \omega)t) = -1$, which geometrically corresponds to the planet being on the inner edge of the epicycle (closest to Earth).

Setting the cosine term to $-1$:

$$
N_{\text{min}} = R^2 \omega + r^2 \Omega - R r (\omega + \Omega)
$$

Factoring the expression:

$$
N_{\text{min}} = (R - r)(R \omega - r \Omega)
$$

Assuming $R > r$ (the deferent is larger than the epicycle), the condition for $N_{\text{min}} < 0$ simplifies to:

$$
R \omega - r \Omega < 0
$$

$$
r \Omega > R \omega
$$

The apparent direction of motion changes when the planet transitions between prograde and retrograde motion. These are the stationary points where $\dot{\varphi} = 0$, meaning $N(t) = 0$:

$$
R^2 \omega + r^2 \Omega + R r (\omega + \Omega) \cos((\Omega - \omega)t) = 0
$$

Solving for $t$:

$$
\cos((\Omega - \omega)t) = -\frac{R^2 \omega + r^2 \Omega}{R r (\omega + \Omega)}
$$

$$
t = \frac{1}{\Omega - \omega} \arccos\left(-\frac{R^2 \omega + r^2 \Omega}{R r (\omega + \Omega)}\right) + \frac{2\pi k}{\Omega - \omega}
$$

where $k \in \mathbb{Z}$.

## Final Result

The parametric equations of the planet's trajectory are:

$$
\begin{align}
x(t) &= R \cos(\omega t) + r \cos(\Omega t) \\
y(t) &= R \sin(\omega t) + r \sin(\Omega t)
\end{align}
$$

The condition for retrograde motion is:

$$
r \Omega > R \omega
$$

The moments of change in direction occur at:

$$
t_k = \frac{1}{\Omega - \omega} \arccos\left(-\frac{R^2 \omega + r^2 \Omega}{R r (\omega + \Omega)}\right) + \frac{2\pi k}{\Omega - \omega}
$$

## Interpretation

The condition $r \Omega > R \omega$ indicates that retrograde motion only occurs if the linear velocity of the planet along the epicycle exceeds the linear velocity of the epicycle's center along the deferent. 

For the required HTML visualization, the kinematic state is fully defined by four independent parameters:
- $R$ (deferent radius)
- $r$ (epicycle radius)
- $\omega$ (deferent angular velocity)
- $\Omega$ (epicycle angular velocity)

By mapping ecliptic longitude $\varphi(t) = \arctan\left(\frac{y(t)}{x(t)}\right)$ on a graph, the periods of retrogradation visually manifest as intervals where the slope of the curve is negative.
# Task 02 – Copernicus's Model

## Problem Statement

1. Implement the motion of two planets (Earth and Mars) in circular orbits around the Sun.
2. Determine the position vector of Mars relative to Earth.
3. Identify the moments of retrogradation in the heliocentric model.
4. Compare the relative trajectory with the geocentric epicyclic model.

## Theory

The Copernican heliocentric model places the Sun at the center of the system. Planets move in simple circular orbits around the Sun with radii $R_i$ and angular velocities $\omega_i$. Kepler's laws later refined this to ellipses, but uniform circular motion is sufficient to reproduce the primary kinematic effects, including retrogradation.

Retrograde motion is explained not by complex physical looping (epicycles), but as a purely optical effect caused by parallax. When a faster-moving inner planet (Earth) overtakes a slower-moving outer planet (Mars), the outer planet appears to move backwards against the distant background stars.

## Step-by-Step Solution

Let the Sun be at the origin $(0,0)$. The position vector of Earth ($Z$) is:

$$
\vec{r}_Z(t) = \begin{pmatrix} R_Z \cos(\omega_Z t) \\ R_Z \sin(\omega_Z t) \end{pmatrix}
$$

The position vector of Mars ($M$) is:

$$
\vec{r}_M(t) = \begin{pmatrix} R_M \cos(\omega_M t) \\ R_M \sin(\omega_M t) \end{pmatrix}
$$

To find the position of Mars relative to Earth, we subtract Earth's position vector from Mars's position vector:

$$
\vec{r}_{M/Z}(t) = \vec{r}_M(t) - \vec{r}_Z(t)
$$

$$
\vec{r}_{M/Z}(t) = \begin{pmatrix} R_M \cos(\omega_M t) - R_Z \cos(\omega_Z t) \\ R_M \sin(\omega_M t) - R_Z \sin(\omega_Z t) \end{pmatrix}
$$

To find the moments of retrogradation, we must determine when the apparent angular velocity of Mars as seen from Earth is negative. The relative angle is $\varphi_{M/Z} = \arctan\left(\frac{y_{M/Z}}{x_{M/Z}}\right)$.

The condition for retrogradation is mathematically identical to the stationary point analysis in Task 1, but applied to the relative coordinates. Let $x = x_{M/Z}$ and $y = y_{M/Z}$. The angular velocity is proportional to the cross product $N(t) = x \dot{y} - y \dot{x}$.

Computing the derivatives:

$$
\dot{x}(t) = -R_M \omega_M \sin(\omega_M t) + R_Z \omega_Z \sin(\omega_Z t)
$$

$$
\dot{y}(t) = R_M \omega_M \cos(\omega_M t) - R_Z \omega_Z \cos(\omega_Z t)
$$

Substitute into $N(t) = x \dot{y} - y \dot{x}$:

$$
N(t) = R_M^2 \omega_M + R_Z^2 \omega_Z - R_M R_Z (\omega_M + \omega_Z) \cos((\omega_Z - \omega_M)t)
$$

Retrograde motion begins and ends when $N(t) = 0$. The maximum retrogradation occurs at opposition, where the planets are collinear with the Sun on the same side. This happens when $(\omega_Z - \omega_M)t = 2\pi k$. At this point, $\cos(0) = 1$.

Substituting $\cos = 1$ into $N(t)$ to check the angular velocity at opposition:

$$
N_{\text{opp}} = R_M^2 \omega_M + R_Z^2 \omega_Z - R_M R_Z (\omega_M + \omega_Z)
$$

$$
N_{\text{opp}} = (R_M - R_Z)(R_M \omega_M - R_Z \omega_Z)
$$

By Kepler's Third Law (or basic observational data), $\omega^2 R^3 = \text{const}$. Therefore, $\omega \propto R^{-3/2}$. 
This implies that $R_M \omega_M < R_Z \omega_Z$. 
Since $R_M > R_Z$, the first term $(R_M - R_Z)$ is positive, and the second term $(R_M \omega_M - R_Z \omega_Z)$ is negative. Thus, $N_{\text{opp}} < 0$, proving that retrogradation always occurs at opposition.

The moments of retrogradation start and end when $N(t) = 0$:

$$
\cos((\omega_Z - \omega_M)t) = \frac{R_M^2 \omega_M + R_Z^2 \omega_Z}{R_M R_Z (\omega_M + \omega_Z)}
$$

## Final Result

The relative trajectory of Mars as seen from Earth is given by:

$$
\vec{r}_{M/Z}(t) = \begin{pmatrix} R_M \cos(\omega_M t) - R_Z \cos(\omega_Z t) \\ R_M \sin(\omega_M t) - R_Z \sin(\omega_Z t) \end{pmatrix}
$$

The moments determining the boundaries of the retrograde loop occur at times $t$:

$$
t = \frac{1}{\omega_Z - \omega_M} \arccos\left(\frac{R_M^2 \omega_M + R_Z^2 \omega_Z}{R_M R_Z (\omega_M + \omega_Z)}\right) + \frac{2\pi k}{\omega_Z - \omega_M}
$$

## Interpretation

Comparing the relative position vector $\vec{r}_{M/Z}(t)$ to the Ptolemaic equation from Task 1:

$$
\vec{p}_{\text{Ptolemy}}(t) = \begin{pmatrix} R \cos(\omega t) + r \cos(\Omega t) \\ R \sin(\omega t) + r \sin(\Omega t) \end{pmatrix}
$$

We can see an exact mathematical equivalence if we set:
- $R = R_M$ (the deferent corresponds to Mars's orbit)
- $\omega = \omega_M$ (deferent velocity corresponds to Mars's angular velocity)
- $r = -R_Z$ (the epicycle corresponds to Earth's orbit)
- $\Omega = \omega_Z$ (epicycle velocity corresponds to Earth's angular velocity)

This demonstrates that Ptolemy's epicycle was not a random physical circle, but rather a geometric projection of Earth's own orbit onto the motion of the other planets. The heliocentric model is mathematically isomorphic to the epicyclic model, but conceptually far more unified, as it explains *all* planetary epicycles using the single shared motion of the Earth.

# Task 03 – Comparison of Models: Number of Parameters and Quality of Description

## Problem Statement

1. Fit the epicycle parameters to the trajectory generated in the heliocentric model.
2. Compare the number of parameters required in both models.
3. Evaluate which model is more economically viable.
4. Interpret the result in the context of simplifying the physical description of astronomical phenomena.

## Theory

Scientific models are evaluated not just on their predictive power, but on their theoretical economy, often guided by Ockham's razor. A model with fewer arbitrary parameters that fits the data equally well is considered superior because it reveals deeper underlying physical symmetries.

The Ptolemaic system uses separate geometric constructs (deferents and epicycles) for each planet. The Copernican system places the Sun at the center, meaning the Earth's orbital motion is implicitly projected onto the apparent motion of all other celestial bodies.

## Step-by-Step Solution

From Task 02, the relative position of Mars as seen from Earth in the Copernican model is:

$$
\vec{r}_{M/Z}(t) = \begin{pmatrix} R_M \cos(\omega_M t) - R_Z \cos(\omega_Z t) \\ R_M \sin(\omega_M t) - R_Z \sin(\omega_Z t) \end{pmatrix}
$$

The position of a planet in the Ptolemaic epicycle model is:

$$
\vec{p}(t) = \begin{pmatrix} R \cos(\omega t) + r \cos(\Omega t) \\ R \sin(\omega t) + r \sin(\Omega t) \end{pmatrix}
$$

To fit the epicycle parameters to the heliocentric trajectory, we map the terms directly. The first term in the Copernican equation corresponds to the deferent, and the second term corresponds to the epicycle:

$$
\begin{align}
R &= R_M \\
\omega &= \omega_M \\
r &= -R_Z \\
\Omega &= \omega_Z
\end{align}
$$

For a single planet (Mars), both models require exactly four kinematic parameters to describe the 2D orbit: two radii and two angular velocities. 

However, if we extend this to an $N$-planet system:
- In the Ptolemaic model, every planet requires its own independent epicycle parameters. For $N$ planets, this requires $4N$ parameters.
- In the Copernican model, the Earth's orbit ($R_Z$ and $\omega_Z$) is shared across all relative observations. For $N$ planets, we need 2 parameters for Earth, plus 2 parameters for each of the other planets. The total is $2N + 2$ parameters.

## Final Result

For $N$ planets, the number of independent parameters is:
- Epicyclic Model: $4N$ parameters.
- Heliocentric Model: $2N + 2$ parameters.

## Interpretation

The Copernican model is far more economical. By physically attributing the epicycle to the Earth's own motion around the Sun, the heliocentric model removes redundant parameters. The Ptolemaic model had to "tune" the epicycle of every single outer planet to perfectly match the Sun's apparent motion (a mysterious coincidence in geocentrism). Heliocentrism naturally explains this coincidence, drastically reducing the degrees of freedom required to model the solar system.

# Task 04 – Kepler's First and Second Laws

## Problem Statement

1. Implement the mathematical representation of an elliptical orbit.
2. Investigate the variation of eccentricity $e$ on the trajectory's shape.
3. Numerically and analytically calculate the area swept out in equal time intervals.
4. Verify the law of equal areas (Kepler's Second Law).

## Theory

Kepler's First Law states that planets move in elliptical orbits with the Sun at one focus. The polar equation of an ellipse relative to a focus is given by the conic section equation.

Kepler's Second Law states that the line joining a planet and the Sun sweeps out equal areas during equal intervals of time. This is a direct geometric consequence of the conservation of angular momentum in a central force field.

## Step-by-Step Solution

The radial distance $r$ as a function of the true anomaly $\theta$ is:

$$
r(\theta) = \frac{a(1-e^2)}{1 + e \cos \theta}
$$

where $a$ is the semi-major axis and $e$ is the eccentricity. The shape changes as follows:
- $e = 0$: Circle.
- $0 < e < 1$: Ellipse.
- $e \ge 1$: Open trajectories (parabola/hyperbola, violating the bound orbit assumption).

The differential area $dA$ swept out by the radius vector in a small angle $d\theta$ is the area of an infinitesimal sector:

$$
dA = \frac{1}{2} r^2 \, d\theta
$$

To find the area swept out over time, we divide by the time differential $dt$:

$$
\frac{dA}{dt} = \frac{1}{2} r^2 \frac{d\theta}{dt}
$$

$$
\frac{dA}{dt} = \frac{1}{2} r^2 \omega
$$

In a central force field, the angular momentum $L$ is conserved. The magnitude of angular momentum for a mass $m$ is:

$$
L = m r v_{\perp} = m r (r \omega) = m r^2 \omega
$$

Substituting $r^2 \omega = \frac{L}{m}$ into the area rate equation:

$$
\frac{dA}{dt} = \frac{L}{2m}
$$

## Final Result

The area swept out in a time interval $\Delta t$ is:

$$
\Delta A = \int_{t_0}^{t_0 + \Delta t} \frac{dA}{dt} dt = \frac{L}{2m} \Delta t
$$

## Interpretation

Because the central force (gravity) exerts no torque, the angular momentum $L$ is strictly constant. Consequently, the areal velocity $\frac{dA}{dt}$ is a constant. This mathematical proof verifies Kepler's Second Law. When the planet is closer to the Sun ($r$ is small), its angular velocity $\omega$ must increase to keep the swept area constant, resulting in faster linear motion at perihelion compared to aphelion.

# Task 05 – Kepler's Third Law (Data Analysis)

## Problem Statement

1. Establish the relationship between the orbital period $T$ and the semi-major axis $a$.
2. Formulate a linear regression model to verify $T^2 \propto a^3$.
3. Estimate the proportionality constant $C$.
4. Determine the theoretical physical basis for this constant.

## Theory

Kepler's Third Law states that the square of the orbital period of a planet is directly proportional to the cube of the semi-major axis of its orbit. Using Newtonian mechanics, this kinematic observation can be derived dynamically from the equilibrium between the gravitational force and centripetal acceleration in a circular orbit approximation.

## Step-by-Step Solution

Assume a circular orbit of radius $a$ where the gravitational force provides the centripetal force:

$$
\frac{G M m}{a^2} = m \frac{v^2}{a}
$$

The orbital velocity $v$ is related to the period $T$ by:

$$
v = \frac{2\pi a}{T}
$$

Substitute $v$ into the force balance equation:

$$
\frac{G M}{a} = \left(\frac{2\pi a}{T}\right)^2
$$

$$
\frac{G M}{a} = \frac{4\pi^2 a^2}{T^2}
$$

Rearranging to solve for $T^2$:

$$
T^2 = \frac{4\pi^2}{G M} a^3
$$

This matches the empirical law:

$$
T^2 = C a^3
$$

To analyze empirical data linearly, we can take the natural logarithm of both sides:

$$
\ln(T^2) = \ln(C a^3)
$$

$$
2 \ln(T) = 3 \ln(a) + \ln(C)
$$

By plotting $y = \ln(T)$ against $x = \ln(a)$, the data points will form a straight line. Linear regression will yield a slope of $1.5$ and a y-intercept of $\frac{1}{2} \ln(C)$.

## Final Result

The theoretical proportionality constant $C$ is:

$$
C = \frac{4\pi^2}{G M}
$$

The linear regression equation for data fitting is:

$$
\ln(T) = 1.5 \ln(a) + 0.5 \ln(C)
$$

## Interpretation

The goodness of fit ($R^2$ approaching 1.0) on solar system data perfectly validates Newtonian gravity. Furthermore, the constant $C$ depends entirely on the mass of the central body $M$ and the universal gravitational constant $G$. By measuring $T$ and $a$ for any orbiting body (like a planet around the Sun, or a moon around Jupiter), the mass of the central body can be precisely determined.

# Task 06 – Two-Body Motion and the Barycenter

## Problem Statement

1. Define the center of mass (barycenter) for a two-body system.
2. Prove that the center of mass moves with constant velocity for an isolated system.
3. Write the Newtonian equations of motion for both bodies.
4. Investigate how the trajectories depend on the mass ratio $m_1/m_2$.

## Theory

In Newtonian mechanics, isolated systems are not subjected to external forces. According to Newton's Third Law, internal forces are equal and opposite. The collective motion of the system can be decoupled into the uniform motion of its center of mass and the relative motion of the bodies around it.

## Step-by-Step Solution

The center of mass vector $\vec{R}$ is defined as:

$$
\vec{R} = \frac{m_1 \vec{r}_1 + m_2 \vec{r}_2}{m_1 + m_2}
$$

Differentiating twice with respect to time yields the acceleration of the center of mass:

$$
\ddot{\vec{R}} = \frac{m_1 \ddot{\vec{r}}_1 + m_2 \ddot{\vec{r}}_2}{m_1 + m_2}
$$

According to Newton's Second Law, $m_i \ddot{\vec{r}}_i = \vec{F}_i$. Let $\vec{F}_{12}$ be the force exerted on body 1 by body 2, and $\vec{F}_{21}$ be the force on body 2 by body 1.

$$
\ddot{\vec{R}} = \frac{\vec{F}_{12} + \vec{F}_{21}}{m_1 + m_2}
$$

By Newton's Third Law, $\vec{F}_{12} = -\vec{F}_{21}$, so $\vec{F}_{12} + \vec{F}_{21} = 0$:

$$
\ddot{\vec{R}} = 0
$$

Integrating with respect to time shows that the total momentum is constant:

$$
m_1 \dot{\vec{r}}_1 + m_2 \dot{\vec{r}}_2 = \text{const}
$$

The specific equations of motion using Newton's Law of Universal Gravitation are:

$$
m_1 \ddot{\vec{r}}_1 = - G \frac{m_1 m_2}{|\vec{r}_1 - \vec{r}_2|^3} (\vec{r}_1 - \vec{r}_2)
$$

$$
m_2 \ddot{\vec{r}}_2 = - G \frac{m_1 m_2}{|\vec{r}_2 - \vec{r}_1|^3} (\vec{r}_2 - \vec{r}_1)
$$

## Final Result

The barycenter definition ensures that:

$$
m_1 \vec{r}_1 + m_2 \vec{r}_2 = (m_1 + m_2) \vec{R}(t)
$$

Because $\ddot{\vec{R}} = 0$, the quantity $m_1 \dot{\vec{r}}_1 + m_2 \dot{\vec{r}}_2$ is strictly conserved. 

## Interpretation

Both bodies orbit their common center of mass. The distance each body sits from the barycenter is inversely proportional to its mass. If $m_1 \gg m_2$ (e.g., Sun and Earth), the barycenter lies very close to the center of $m_1$, making $m_1$ appear nearly stationary while $m_2$ performs a large orbit. If $m_1 \approx m_2$ (e.g., binary stars of equal mass), both bodies trace identical symmetrical orbits around a central empty point in space.

# Task 07 – Newton's Gravity and Orbit Classification

## Problem Statement

1. Define the specific total energy $E$ for motion in a central gravitational field.
2. Investigate the mathematical cases mapping energy to orbital geometry (bound, parabolic, hyperbolic).
3. Determine the initial velocity conditions required to achieve these specific orbit types.

## Theory

The nature of a Keplerian orbit is entirely dictated by the total mechanical energy of the system, which is the sum of kinetic energy and gravitational potential energy. Since gravity is a conservative force, this total energy remains constant throughout the orbit.

## Step-by-Step Solution

The total energy $E$ of a body of mass $m$ at distance $r$ from a central mass $M$ with velocity $v$ is:

$$
E = \frac{1}{2} m v^2 - \frac{GMm}{r}
$$

The orbit classification relies strictly on the sign of $E$:

1. **$E < 0$ (Bound Orbit):** The kinetic energy is insufficient to overcome the gravitational potential well. The maximum radius (apocenter) is finite. The orbit is an **ellipse** (or a circle if exactly perfectly balanced).
2. **$E = 0$ (Marginally Unbound):** The kinetic energy exactly cancels the potential well. The body will reach infinity with exactly zero velocity left. The orbit is a **parabola**.
3. **$E > 0$ (Unbound Orbit):** The kinetic energy exceeds the gravitational binding energy. The body will reach infinity with a residual positive velocity ($v_{\infty} > 0$). The orbit is a **hyperbola**.

To find the critical initial velocity that separates bound from unbound orbits (escape velocity, $v_e$), we set $E = 0$:

$$
\frac{1}{2} m v_e^2 - \frac{GMm}{r} = 0
$$

Solving for $v_e$:

$$
v_e = \sqrt{\frac{2GM}{r}}
$$

## Final Result

The initial velocity $v_0$ given at an initial radius $r_0$ dictates the orbit:

$$
\begin{align}
v_0 &< \sqrt{\frac{2GM}{r_0}} \implies E < 0 \quad (\text{Ellipse}) \\
v_0 &= \sqrt{\frac{2GM}{r_0}} \implies E = 0 \quad (\text{Parabola}) \\
v_0 &> \sqrt{\frac{2GM}{r_0}} \implies E > 0 \quad (\text{Hyperbola})
\end{align}
$$

## Interpretation

The condition $E < 0$ guarantees that the planet cannot escape to infinity, locking it into periodic motion. Spacecraft leaving Earth must perform a "trans-lunar" or "interplanetary" injection burn specifically designed to push their kinetic energy high enough to transition their orbit from $E < 0$ to $E > 0$ relative to Earth's reference frame.

# Task 08 – Orbit Perturbation and Precession

## Problem Statement

1. Formulate the equations of motion for a modified gravitational potential featuring an inverse-square term.
2. Investigate the effect of this modified potential on the orbital geometry.
3. Quantify how the perturbation parameter $\alpha$ drives the precession of the perihelion.

## Theory

Perfect Newtonian gravity ($U \propto -1/r$) yields perfectly closed, stationary ellipses. However, relativistic effects, planetary oblateness, or multi-body interactions can be approximated by adding a small perturbation term $\alpha/r^2$ to the potential. This breaks the perfect closure of the orbit, causing the ellipse itself to slowly rotate over time—a phenomenon known as apsidal precession.

## Step-by-Step Solution

The modified potential is:

$$
U(r) = -\frac{GMm}{r} + \frac{\alpha}{r^2}
$$

The force is the negative gradient of the potential:

$$
F(r) = -\frac{dU}{dr}
$$

$$
F(r) = -\frac{GMm}{r^2} + \frac{2\alpha}{r^3}
$$

Because the force is still entirely central (acts solely along the radial vector $\hat{r}$), angular momentum $L = mr^2\dot{\theta}$ is strictly conserved. We can write the effective potential by incorporating the centrifugal barrier:

$$
U_{\text{eff}}(r) = \frac{L^2}{2mr^2} + U(r)
$$

$$
U_{\text{eff}}(r) = \frac{L^2}{2mr^2} - \frac{GMm}{r} + \frac{\alpha}{r^2}
$$

Grouping the $1/r^2$ terms:

$$
U_{\text{eff}}(r) = \frac{L^2 + 2m\alpha}{2mr^2} - \frac{GMm}{r}
$$

This is mathematically identical to standard Newtonian gravity, but with a shifted angular momentum $L' = \sqrt{L^2 + 2m\alpha}$. In standard gravity, the angle between successive perihelions is exactly $2\pi$. With the perturbed angular momentum, the angle $\Delta \theta$ required to return to perihelion is scaled:

$$
\Delta \theta = 2\pi \frac{L}{L'} = 2\pi \left(1 + \frac{2m\alpha}{L^2}\right)^{-1/2}
$$

## Final Result

Applying a Taylor expansion for small $\alpha$ ($2m\alpha \ll L^2$):

$$
\Delta \theta \approx 2\pi \left(1 - \frac{m\alpha}{L^2}\right)
$$

The precession angle per orbit is the difference between this and $2\pi$:

$$
\delta \theta = 2\pi - \Delta \theta \approx \frac{2\pi m \alpha}{L^2}
$$

## Interpretation

If $\alpha > 0$, the effective inverse-square repulsion slightly pushes the body outward, causing the orbit to precess "forward" (prograde precession) such that the perihelion slowly drifts in the direction of motion. General relativity naturally introduces an effective $\alpha$ term, famously explaining the anomalous precession of Mercury's perihelion that purely classical Newtonian models failed to solve.

# Task 09 – Three-Body System

## Problem Statement

1. Write the fully coupled equations of motion for three interacting point masses.
2. Formulate the system for numerical integration (e.g., using Runge-Kutta 4th order).
3. Discuss the stability and predictability of the resulting configuration.

## Theory

Unlike the two-body problem, the general three-body problem under Newtonian gravity has no closed-form analytical solution. The presence of a third gravitational source makes the system of differential equations highly non-linear, leading to deterministic chaos, where microscopic changes in initial conditions result in macroscopically divergent trajectories.

## Step-by-Step Solution

Let the three masses be $m_1, m_2, m_3$ with position vectors $\vec{r}_1, \vec{r}_2, \vec{r}_3$. The force on mass $i$ is the vector sum of the gravitational pulls from the other two masses:

$$
\vec{F}_i = \sum_{j \neq i} G \frac{m_i m_j}{|\vec{r}_j - \vec{r}_i|^3} (\vec{r}_j - \vec{r}_i)
$$

The acceleration for each body is $\ddot{\vec{r}}_i = \vec{F}_i / m_i$:

$$
\ddot{\vec{r}}_1 = G \frac{m_2}{|\vec{r}_2 - \vec{r}_1|^3}(\vec{r}_2 - \vec{r}_1) + G \frac{m_3}{|\vec{r}_3 - \vec{r}_1|^3}(\vec{r}_3 - \vec{r}_1)
$$

$$
\ddot{\vec{r}}_2 = G \frac{m_1}{|\vec{r}_1 - \vec{r}_2|^3}(\vec{r}_1 - \vec{r}_2) + G \frac{m_3}{|\vec{r}_3 - \vec{r}_2|^3}(\vec{r}_3 - \vec{r}_2)
$$

$$
\ddot{\vec{r}}_3 = G \frac{m_1}{|\vec{r}_1 - \vec{r}_3|^3}(\vec{r}_1 - \vec{r}_3) + G \frac{m_2}{|\vec{r}_2 - \vec{r}_3|^3}(\vec{r}_2 - \vec{r}_3)
$$

To solve this numerically using an RK4 method, these three 2nd-order differential equations must be decomposed into six 1st-order differential equations by introducing velocity vectors $\vec{v}_i = \dot{\vec{r}}_i$.

The state vector for the system at any time $t$ is:

$$
\vec{Y} = \begin{pmatrix} \vec{r}_1 \\ \vec{r}_2 \\ \vec{r}_3 \\ \vec{v}_1 \\ \vec{v}_2 \\ \vec{v}_3 \end{pmatrix}
$$

The time derivative of the state vector is:

$$
\frac{d\vec{Y}}{dt} = \begin{pmatrix} \vec{v}_1 \\ \vec{v}_2 \\ \vec{v}_3 \\ \ddot{\vec{r}}_1 \\ \ddot{\vec{r}}_2 \\ \ddot{\vec{r}}_3 \end{pmatrix}
$$

## Final Result

The three-body system is governed by a set of coupled non-linear ODEs that update the state vector $\vec{Y}$ iteratively via numerical integration algorithms:

$$
\vec{Y}_{n+1} = \vec{Y}_n + \frac{\Delta t}{6} (\vec{k}_1 + 2\vec{k}_2 + 2\vec{k}_3 + \vec{k}_4)
$$

where $\vec{k}_i$ are the standard RK4 slopes evaluated across the multi-dimensional vector field.

## Interpretation

Except for specific, highly restricted initial conditions (like the figure-eight orbit or Lagrange point configurations), a generic three-body system is unstable. Usually, energy is exchanged chaotically between the bodies until one body achieves escape velocity ($E > 0$) and is ejected from the system, reducing the remaining two bodies back to a stable, integrable two-body binary system.

# Task 10 – Stability Analysis and Conserved Quantities

## Problem Statement

1. Identify the quantities that must remain conserved during the numerical integration of an $N$-body system.
2. Evaluate how numerical integration schemes affect these conserved quantities over time.
3. Investigate the impact of the time step $\Delta t$ on simulation stability.

## Theory

In a computationally simulated closed system, tracking invariant properties provides the primary metric for algorithmic accuracy. While standard explicit integration schemes (like Euler or standard RK4) truncate mathematical series to approximate curves, they inherently violate physical conservation laws over long periods.

## Step-by-Step Solution

The analytical constants of motion for the isolated multi-body problem are:

1. **Total Energy ($E$):** The sum of kinetic energies of all bodies and the total gravitational potential energy of all unique pairs.

$$
E(t) = \sum_{i=1}^N \frac{1}{2} m_i \vec{v}_i^2 - \sum_{i=1}^{N-1} \sum_{j=i+1}^N \frac{G m_i m_j}{|\vec{r}_i - \vec{r}_j|}
$$

2. **Total Angular Momentum ($\vec{L}$):**

$$
\vec{L}(t) = \sum_{i=1}^N \vec{r}_i \times (m_i \vec{v}_i)
$$

3. **Center of Mass State ($\vec{R}$ and $\dot{\vec{R}}$):** The barycenter must not accelerate.

During numerical integration, the discrete time step $\Delta t$ introduces truncation errors.
- If $\Delta t$ is too large, the simulated bodies might "jump" too far along tangent lines, overestimating distances and causing the total energy $E(t)$ to artificially drift upwards (energy non-conservation).
- Standard RK4 is not *symplectic*. This means it does not preserve the geometric volume of phase space. Over millions of iterations, RK4 will inevitably cause orbits to artificially decay or expand.

## Final Result

The stability of the numerical method is continuously monitored by calculating the fractional energy error at each time step:

$$
\epsilon_E = \left| \frac{E(t) - E(0)}{E(0)} \right|
$$

## Interpretation

For long-term astronomical simulations, traditional RK4 is abandoned despite its single-step accuracy. Instead, symplectic integrators (like the Leapfrog or Verlet methods) are used. Symplectic integrators natively preserve the Hamiltonian structure of the system, meaning that while they may have small positional inaccuracies at any given moment, the total energy fluctuates around a constant mean rather than drifting boundlessly to infinity.