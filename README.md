# love
## Theory
In Newtonian mechanics, the Love numbers $\lambda_i$ measure a body's tidal response to some external potential. Spherical harmonics are used in the expansion:

$$\phi_\text{ext} = \sum_l A_l\left[r^l + \lambda_l\frac{1}{r^{l+1}}\right]P_l(\cos\theta)$$

The growing mode $r^l$ are identified as tidal effects from the external body. The decaying modes $1/r^{l+1}$ are identified as tidal effects from the internal body structure. For a Schwarzschild solution, it's well-known that the Love numbers vanish: $\lambda_l = 0$. This is a strange conclusion unique to black holes. Other compact objects, e.g. the polytropic neutron star model, have nonvanishing Love numbers.

Because gravity is nonlinear, it's difficult to find exact solutions for tidal response to external potentials. Instead, we use perturbation theory to expand solutions around a vacuum metric. The point-particle effective field theory (EFT) uses a lowest-order action (the Nambu-Goto action) to describe the dynamics of a black hole at sufficiently far distance, for a spacetime with metric $g_{\mu\nu}$. Corrections due to internal structures are encoded in higher-derivative terms.

$$S_{NG} = -M\int d\tau \sqrt{-g_{\mu\nu}\frac{dx^\mu}{d\tau}\frac{dx^\nu}{d\tau}}$$

The spacetime metrics are then expanded perturbatively with $g_{\mu\nu} \rightarrow g_{\mu\nu} + h_{\mu\nu}$, $h_{\mu\nu} \ll 1$. In the Schwarzschild solution, we take advantage of spherical symmetry to decompose $h_{\mu\nu}$ into spherical harmonics, then further into even and odd modes.

$$\begin{gather*}
    h_{\mu\nu}^\text{even} = \begin{pmatrix}
      f(r)H_0(t, r) & H_1(t, r) & \mathcal H_0(t, r)\partial_\theta & \mathcal H_0(t, r)\partial_\varphi \\
      & \frac{1}{f(r)}H_2(t, r) & \mathcal H_1(t, r)\partial_\theta & \mathcal H_1(t, r)\partial_\varphi \\
      && r^2(\mathcal K(t, r) + \mathcal G(t, r)\partial_\theta^2) & r^2\mathcal G(t, r)\nabla_\theta\nabla_\varphi \\
        &&& r^2(\sin^2\theta \mathcal K(t, r) + \mathcal G(t, r)\nabla_\varphi^2)
    \end{pmatrix}Y_{lm} \\
    h_{\mu\nu}^\text{odd} = \begin{pmatrix}
        f(r)H_0(t, r) & H_1(t, r) & \mathcal H_0(t, r)\partial_\theta & \mathcal H_0(t, r)\partial_\varphi \\
        & \frac{1}{f(r)}H_2(t, r) & \mathcal H_1(t, r)\partial_\theta & \mathcal H_1(t, r)\partial_\varphi \\
        && r^2(\mathcal K(t, r) + \mathcal G(t, r)\partial_\theta^2) & r^2\mathcal G(t, r)\nabla_\theta\nabla_\varphi \\
        &&& r^2(\sin^2\theta\mathcal K(t, r) + \mathcal G(t, r)\nabla_\varphi^2)
    \end{pmatrix}Y_{lm}
\end{gather*}$$

To simplify the 10 fields $(H_0, H_1, H_2, \mathcal H_0, \mathcal H_1, \mathcal K, \mathcal G, h_0, h_1, h_2)$, the Regge-Wheeler gauge is used:

$$\mathcal H_0 = \mathcal H_1 = \mathcal G = h_2 = 0$$


## Project
This project is an attempt to do more hands-on work on black hole tidal response physics. The basic goal is to implement a numerical ODE solver in Python for the radial perturbative equations of the Schwarzschild and Kerr metrics in the Regge-Wheeler gauge. Once this is done, the results will be compared to that of a polytropic neutron star model, where Love numbers are nonzero. Throughout, the results will be compared against known results like the asymptotic behavior near the horizon & large radii, as a sanity check.

Resources:

- Slideshow overview: https://indico.in2p3.fr/event/30113/sessions/19512/attachments/80393/118128/AG-GdR-OG_seminar.pdf
- Reference (2009): https://arxiv.org/pdf/0906.1366
- Comprehensive review (2026): https://arxiv.org/pdf/2604.08653
- Ladder symmetries of black holes: https://arxiv.org/abs/2105.01069
- Love numbers of Bardeen black holes: https://arxiv.org/pdf/2512.05767
