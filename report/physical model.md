## Physical Model

A physical model is evaluated so that we can understand the problem more properly.

### Solar-centered ecliptic coordinate system

Solar-centered ecliptic coordinate system is centered at the sun, using spring equinox as $x+$ or polar axis, ecliptic as $xy$ plane.

Earth loacation (polar)

$$
\mathbf{x}_e = (r_e, \theta_e, 0)
$$

where

$$
\theta_e = \frac{2 \pi}{T_{ey}} t + \theta_{e0}
$$

or (dirichlet)

$$
\mathbf{x}_e =
\begin{bmatrix}
    r_e \cos{(\cfrac{2 \pi}{T_{ey}} t + \theta_{e0})}\\
    r_e \sin{(\cfrac{2 \pi}{T_{ey}} t + \theta_{e0})}\\
    0\\
\end{bmatrix}
$$

other planets can have a similar definition.

### Earth-centered ecliptic coordinate system

Solar-centered ecliptic coordinate system is centered at the earth, using spring equinox as $x+$ or polar axis, ecliptic as $xy$ plane.

### Equatorial coordinate system

Equatorial coordinate system is centered at the earth, using spring equinox as $x+$ or polar axis, equator as $xy$ plane.

Planets location in such system is defined as right ascension $\alpha$ and declination $\delta$, 

as (polar)

$$
\mathbf{X}_p = (R_p, \frac{\pi}{2} - \delta, \alpha)
$$

as we normally do with spherical coordinate system $(r,\theta,\phi)$

or (dirichlet)

$$
\mathbf{X}_p =
\begin{bmatrix}
    R_p \cos\delta \cos\alpha\\
    R_p \cos\delta \sin\alpha\\
    R_p \sin\delta\\
\end{bmatrix}
$$

### Horizontal coordinate system

Horizontal coordinate system is centered at the observer, using local north as $x+$ or polar axis, local vertical up direction as $z+$.

Planets location in such system is defined as azimuth $A$ and altitude $a$,

as (polar)

$$
\hat \mathbf{X}_p = (R_p, \frac{\pi}{2} - a, A)
$$

as we normally do with spherical coordinate system $(r,\theta,\phi)$

or (dirichlet)

$$
\hat \mathbf{X}_p =
\begin{bmatrix}
    R_p \cos a \cos A\\
    R_p \cos a \sin A\\
    R_p \sin a\\
\end{bmatrix}
$$

### Coordinate transformation

It is easy to transform between the solar-centered ecliptic coordinate system and the earth-centered ecliptic coordinate system. A planet with coordinate $\mathbf{x}_p$ in solar-centered ecliptic coordinate system is at $\mathbf{x}_p - \mathbf{x}_e$ in earth-centered ecliptic coordinate system.

$$
\mathbf{x}_p - \mathbf{x}_e =
\begin{bmatrix}
    r_p \cos{(\cfrac{2 \pi}{T_{py}} t + \theta_{p0})} - r_e \cos{(\cfrac{2 \pi}{T_{ey}} t + \theta_{e0})}\\
    r_p \sin{(\cfrac{2 \pi}{T_{py}} t + \theta_{p0})} - r_e \sin{(\cfrac{2 \pi}{T_{ey}} t + \theta_{e0})}\\
    0\\
\end{bmatrix}
$$

transformation from the earth-centered ecliptic to equatorial coordinate system [^fn1]

$$
\begin{bmatrix}
    x_{\text{equatorial}}\\
    y_{\text{equatorial}}\\
    z_{\text{equatorial}}\\
    \end{bmatrix} =
\begin{bmatrix}
    1   & 0                & 0\\
    0   & \cos \varepsilon & -\sin \varepsilon \\
    0   & \sin \varepsilon & \cos \varepsilon \\
\end{bmatrix}
\begin{bmatrix}
    x_{\text{ecliptic}}\\
    y_{\text{ecliptic}}\\
    z_{\text{ecliptic}}\\
\end{bmatrix}
$$

where ecliptic obliquity

$$
ε=23\degree26'20.512''
$$

so we have

$$
\begin{aligned}
    \begin{bmatrix}
        R_p \cos\delta \cos\alpha\\
        R_p \cos\delta \sin\alpha\\
        R_p \sin\delta\\
    \end{bmatrix} &=
    \begin{bmatrix}
        1   & 0                & 0\\
        0   & \cos \varepsilon & -\sin \varepsilon \\
        0   & \sin \varepsilon & \cos \varepsilon \\
    \end{bmatrix}
    \begin{bmatrix}
        r_p \cos{(\cfrac{2 \pi}{T_{py}} t + \theta_{p0})} - r_e \cos{(\cfrac{2 \pi}{T_{ey}} t + \theta_{e0})}\\
        r_p \sin{(\cfrac{2 \pi}{T_{py}} t + \theta_{p0})} - r_e \sin{(\cfrac{2 \pi}{T_{ey}} t + \theta_{e0})}\\
        0\\
    \end{bmatrix} \\ &=
    \begin{bmatrix}
        r_p \cos{(\cfrac{2 \pi}{T_{py}} t + \theta_{p0})} - r_e \cos{(\cfrac{2 \pi}{T_{ey}} t + \theta_{e0})}\\
        \cos \varepsilon (r_p \sin{(\cfrac{2 \pi}{T_{py}} t + \theta_{p0})} - r_e \sin{(\cfrac{2 \pi}{T_{ey}} t + \theta_{e0})})\\
        \sin \varepsilon (r_p \sin{(\cfrac{2 \pi}{T_{py}} t + \theta_{p0})} - r_e \sin{(\cfrac{2 \pi}{T_{ey}} t + \theta_{e0})})\\
    \end{bmatrix}
\end{aligned}
$$

transformation from equatorial to horizontal coordinate system [^fn2]

$$
\cos A\cdot \cos a=-\cos \phi \cdot \sin \delta +\sin \phi \cdot \cos \delta \cdot \cos H
$$

$$
\sin A\cdot \cos a=\cos \delta \cdot \sin H
$$

$$
\sin a=\sin \phi \cdot \sin \delta +\cos \phi \cdot \cos \delta \cdot \cos H
$$

or

$$
\begin{aligned}
    \begin{bmatrix}
        \cos A\cdot \cos a\\
        \sin A\cdot \cos a\\
        \sin a\\
    \end{bmatrix} &=
    \begin{bmatrix}
        \sin \phi   & 0 & -\cos \phi\\
        0           & 1 & 0\\
        \cos \phi   & 0 & \sin \phi \\
    \end{bmatrix}
    \begin{bmatrix}
        \cos\delta \cos H\\
        \cos\delta \sin H\\
        \sin\delta\\
    \end{bmatrix} \\
\end{aligned}
$$

where hour angle[^fn3]

$$
H(t,\alpha) = GST(t) + \lambda - \alpha
$$

One of the final goal of this project is to predict $A$ and $a$ with $t$, given longitude $\lambda$ and latitude $\phi$ under specific model, which we are to try explaing.

## Note

- Planets are actually in ellipse orbits instead of circle ones and $z$ is not $0$ to be precise, here we made some simplification just to show the complexity of the problem
- A slow motion of Earth's axis, precession, causes a slow, continuous turning of the coordinate system westward about the poles of the ecliptic, completing one circuit in about 26,000 years.

## Reference

[^fn1]: Ecliptic coordinate system - Wikipedia, https://en.wikipedia.org/wiki/Ecliptic_coordinate_system

[^fn2]: Horizontal coordinate system - Wikipedia, https://en.wikipedia.org/wiki/Horizontal_coordinate_system

[^fn3]: Hour angle - Wikipedia, https://en.wikipedia.org/wiki/Hour_angle