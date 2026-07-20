---
permalink: /quantum-notes/
title: "Quantum Mechanics Notes"
author_profile: true
layout: single
toc: true
toc_sticky: true
---

## Preface

These notes document my journey through quantum mechanics — from foundational principles to advanced topics. I use them alongside interactive simulations at my [Quantum Physics Lab](https://jasonscott39927-ops.github.io/quantum-physics-lab/).

---

## 1. Mathematical Foundations

### 1.1 Hilbert Space

Quantum states live in a complex Hilbert space $$\mathcal{H}$$. A state vector $$\vert\psi\rangle \in \mathcal{H}$$ contains all physical information about the system.

- **Inner product**: $$\langle\phi\vert\psi\rangle$$ — probability amplitude
- **Norm**: $$\Vert\psi\Vert = \sqrt{\langle\psi\vert\psi\rangle}$$ — normalized to 1
- **Completeness**: Any state can be expanded in an orthonormal basis $$\{\vert n\rangle\}$$: 

$$\vert\psi\rangle = \sum_n c_n \vert n\rangle, \quad c_n = \langle n\vert\psi\rangle$$

### 1.2 Operators

Physical observables are represented by Hermitian operators $$\hat{A} = \hat{A}^\dagger$$.

- **Eigenvalue equation**: $$\hat{A}\vert a_n\rangle = a_n\vert a_n\rangle$$
- **Expectation value**: $$\langle\hat{A}\rangle = \langle\psi\vert\hat{A}\vert\psi\rangle$$
- **Uncertainty**: $$\Delta A \Delta B \geq \frac{1}{2}\vert\langle[\hat{A},\hat{B}]\rangle\vert$$

### 1.3 Dirac Notation

| Concept | Notation |
|---------|----------|
| Ket (state vector) | $$\vert\psi\rangle$$ |
| Bra (dual vector) | $$\langle\psi\vert$$ |
| Inner product | $$\langle\phi\vert\psi\rangle$$ |
| Outer product | $$\vert\psi\rangle\langle\phi\vert$$ |
| Projection operator | $$\hat{P}_n = \vert n\rangle\langle n\vert$$ |

---

## 2. The Schrödinger Equation

### 2.1 Time-Dependent Form

$$i\hbar\frac{\partial}{\partial t}\vert\psi(t)\rangle = \hat{H}\vert\psi(t)\rangle$$

The Hamiltonian $$\hat{H} = \frac{\hat{p}^2}{2m} + V(\hat{x})$$ governs time evolution.

### 2.2 Time-Independent Form

For stationary states with definite energy $$E$$:

$$\hat{H}\vert\psi\rangle = E\vert\psi\rangle$$

In position representation:

$$-\frac{\hbar^2}{2m}\nabla^2\psi(\mathbf{r}) + V(\mathbf{r})\psi(\mathbf{r}) = E\psi(\mathbf{r})$$

### 2.3 Time Evolution Operator

$$\vert\psi(t)\rangle = \hat{U}(t)\vert\psi(0)\rangle = e^{-i\hat{H}t/\hbar}\vert\psi(0)\rangle$$

Key property: unitary, $$\hat{U}^\dagger\hat{U} = \mathbb{1}$$, preserving probability.

---

## 3. Exactly Solvable Systems

### 3.1 Free Particle

$$V(x) = 0 \Rightarrow \psi_k(x) = Ae^{ikx} + Be^{-ikx}, \quad E = \frac{\hbar^2 k^2}{2m}$$

Continuous spectrum. Momentum eigenstates: $$\hat{p}\vert k\rangle = \hbar k\vert k\rangle$$.

### 3.2 Infinite Square Well

$$V(x) = \begin{cases} 0 & 0 < x < L \\ \infty & \text{otherwise} \end{cases}$$

Solutions:

$$\psi_n(x) = \sqrt{\frac{2}{L}}\sin\left(\frac{n\pi x}{L}\right), \quad E_n = \frac{n^2\pi^2\hbar^2}{2mL^2}, \quad n = 1,2,3,\ldots$$

### 3.3 Quantum Harmonic Oscillator

$$\hat{H} = \frac{\hat{p}^2}{2m} + \frac{1}{2}m\omega^2\hat{x}^2$$

Ladder operators:

$$\hat{a} = \sqrt{\frac{m\omega}{2\hbar}}\left(\hat{x} + \frac{i\hat{p}}{m\omega}\right), \quad \hat{a}^\dagger = \sqrt{\frac{m\omega}{2\hbar}}\left(\hat{x} - \frac{i\hat{p}}{m\omega}\right)$$

Spectrum: $$E_n = \hbar\omega\left(n + \frac{1}{2}\right), \quad n = 0,1,2,\ldots$$

Number states: $$\hat{a}^\dagger\hat{a}\vert n\rangle = n\vert n\rangle$$

### 3.4 Hydrogen Atom

Radial equation with Coulomb potential $$V(r) = -\frac{e^2}{4\pi\epsilon_0 r}$$:

$$E_n = -\frac{me^4}{2(4\pi\epsilon_0)^2\hbar^2}\frac{1}{n^2} = -\frac{13.6\text{ eV}}{n^2}$$

Quantum numbers: $$n$$ (principal), $$\ell$$ (orbital), $$m$$ (magnetic).

---

## 4. Angular Momentum & Spin

### 4.1 Orbital Angular Momentum

$$\hat{\mathbf{L}} = \hat{\mathbf{r}} \times \hat{\mathbf{p}}, \quad [\hat{L}_i, \hat{L}_j] = i\hbar\epsilon_{ijk}\hat{L}_k$$

Simultaneous eigenstates of $$\hat{L}^2$$ and $$\hat{L}_z$$:

$$\hat{L}^2\vert\ell,m\rangle = \hbar^2\ell(\ell+1)\vert\ell,m\rangle, \quad \hat{L}_z\vert\ell,m\rangle = \hbar m\vert\ell,m\rangle$$

### 4.2 Spin-1/2

Pauli matrices: 

$$\sigma_x = \begin{pmatrix}0&1\\1&0\end{pmatrix}, \quad \sigma_y = \begin{pmatrix}0&-i\\i&0\end{pmatrix}, \quad \sigma_z = \begin{pmatrix}1&0\\0&-1\end{pmatrix}$$

Spin operator: $$\hat{\mathbf{S}} = \frac{\hbar}{2}\boldsymbol{\sigma}$$

Spin precession in magnetic field $$\mathbf{B} = B\hat{z}$$:

$$\vert\psi(t)\rangle = e^{-i\omega t\sigma_z/2}\vert\psi(0)\rangle, \quad \omega = \frac{geB}{2m}$$

### 4.3 Addition of Angular Momentum

Clebsch-Gordan coefficients: 

$$\vert J,M\rangle = \sum_{m_1,m_2} C^{JM}_{j_1 m_1 j_2 m_2} \vert j_1,m_1\rangle \otimes \vert j_2,m_2\rangle$$

---

## 5. Approximation Methods

### 5.1 Time-Independent Perturbation Theory

For $$\hat{H} = \hat{H}_0 + \lambda\hat{V}$$:

**First order:**
$$E_n^{(1)} = \langle n^{(0)}\vert\hat{V}\vert n^{(0)}\rangle$$

$$\vert n^{(1)}\rangle = \sum_{k \neq n} \frac{\langle k^{(0)}\vert\hat{V}\vert n^{(0)}\rangle}{E_n^{(0)} - E_k^{(0)}}\vert k^{(0)}\rangle$$

### 5.2 Variational Method

For any trial state $$\vert\tilde{\psi}\rangle$$:

$$E_0 \leq \frac{\langle\tilde{\psi}\vert\hat{H}\vert\tilde{\psi}\rangle}{\langle\tilde{\psi}\vert\tilde{\psi}\rangle}$$

### 5.3 WKB Approximation

For slowly varying potentials:

$$\psi(x) \approx \frac{C}{\sqrt{p(x)}}\exp\left(\pm\frac{i}{\hbar}\int^x p(x')dx'\right), \quad p(x) = \sqrt{2m[E - V(x)]}$$

---

## 6. Scattering Theory

### 6.1 Lippmann-Schwinger Equation

$$\vert\psi^{(\pm)}\rangle = \vert\phi\rangle + \frac{1}{E - \hat{H}_0 \pm i\epsilon}\hat{V}\vert\psi^{(\pm)}\rangle$$

### 6.2 Born Approximation

First-order scattering amplitude:

$$f^{(1)}(\mathbf{k}',\mathbf{k}) = -\frac{2m}{\hbar^2}\frac{1}{4\pi}\int d^3r\, e^{-i\mathbf{q}\cdot\mathbf{r}}V(\mathbf{r}), \quad \mathbf{q} = \mathbf{k}' - \mathbf{k}$$

### 6.3 Partial Wave Expansion

$$\frac{d\sigma}{d\Omega} = \vert f(\theta)\vert^2, \quad f(\theta) = \frac{1}{k}\sum_{\ell=0}^\infty (2\ell+1)e^{i\delta_\ell}\sin\delta_\ell P_\ell(\cos\theta)$$

---

## 7. Quantum Entanglement

### 7.1 Bell States

Maximally entangled two-qubit states:

$$\vert\Phi^\pm\rangle = \frac{1}{\sqrt{2}}(\vert 00\rangle \pm \vert 11\rangle)$$

$$\vert\Psi^\pm\rangle = \frac{1}{\sqrt{2}}(\vert 01\rangle \pm \vert 10\rangle)$$

### 7.2 Bell's Inequality

CHSH form: for measurements $$A,A'$$ on Alice's side and $$B,B'$$ on Bob's:

$$\mathcal{S} = \vert\langle AB\rangle + \langle AB'\rangle + \langle A'B\rangle - \langle A'B'\rangle\vert \leq 2$$

Quantum mechanics violates this: $$\mathcal{S} \leq 2\sqrt{2}$$ (Tsirelson bound).

---

## 8. Advanced Topics

### 8.1 Berry Phase

For adiabatic evolution along a closed path $$C$$ in parameter space:

$$\gamma_n(C) = i\oint_C \langle n(\mathbf{R})\vert\nabla_{\mathbf{R}}\vert n(\mathbf{R})\rangle \cdot d\mathbf{R}$$

Berry curvature: $$\boldsymbol{\Omega}_n = \nabla_{\mathbf{R}} \times \mathbf{A}_n, \quad \mathbf{A}_n = i\langle n\vert\nabla_{\mathbf{R}}\vert n\rangle$$

### 8.2 Second Quantization

Field operators:

$$\hat{\psi}(\mathbf{r}) = \sum_n \phi_n(\mathbf{r})\hat{a}_n, \quad \hat{\psi}^\dagger(\mathbf{r}) = \sum_n \phi_n^*(\mathbf{r})\hat{a}_n^\dagger$$

Commutation relations: $$[\hat{a}_n, \hat{a}_m^\dagger] = \delta_{nm}$$ (bosons), $$\{\hat{a}_n, \hat{a}_m^\dagger\} = \delta_{nm}$$ (fermions).

### 8.3 Rabi Oscillation

Two-level system driven by resonant field:

$$\hat{H} = \frac{\hbar\omega_0}{2}\sigma_z + \hbar\Omega\cos(\omega t)\sigma_x$$

Rabi frequency: $$\Omega_R = \sqrt{\Omega^2 + \delta^2}$$, where $$\delta = \omega - \omega_0$$.

Population oscillates: $$P_e(t) = \frac{\Omega^2}{\Omega_R^2}\sin^2\left(\frac{\Omega_R t}{2}\right)$$

---

## References

- Sakurai, *Modern Quantum Mechanics*
- Griffiths, *Introduction to Quantum Mechanics*
- Ashcroft & Mermin, *Solid State Physics*
- Negele & Orland, *Quantum Many-Particle Systems*
- Nielsen & Chuang, *Quantum Computation and Quantum Information*

---

*Last updated: July 2026*
