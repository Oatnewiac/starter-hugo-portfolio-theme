---
title: Quantum mechanics lecture notes
summary: Notes for the 2022 fall Quantum Mechanics course
tags:
  - QM
date: 2022-07-01
---
[toc]
# chap0. Operators



## Hermitian opertator
Consider an operator $\hat A$ and its **Hermitian conjugate** $\hat A^\dagger$ satisfies
$$\langle \hat A f\ket{g} = \langle f\ket{\hat A^\dagger g}$$
Particularly, operators whose Hemitian conjugates are themselves are called **Hermitian operators**
$$\hat Q = \hat Q^\dagger$$


## Commutator

The commutator between two operators is defined as

$$[\hat A,\hat B] =\hat A\hat B - \hat B\hat A$$

### <span id="jump1"> canonical commutation relation</span>

We can easily dedude that $\left[ \hat x,\hat p\right] \psi =i\hbar\psi$, where $\hat x = x$ and $\hat p =- i\hbar\dfrac{\partial }{\partial x}$, thus

$$[\hat x,\hat p] =i\hbar \,\mathbb {I}$$ 

where $\mathbb {I}$ is the unit operator, sometimes it is 1. The operators whose commutator is not equal to zero is called the <font color=red>canonical commutation relation</font>. 



# chap1. Wave function
## Schrödinger Equation

$$i\hbar\dfrac{\partial \Psi}{\partial t}=-\dfrac{\hbar^2}{2m}\nabla^2\Psi+V\Psi$$

With Hamiltonian $H = \dfrac{p^2}{2m}+V$, correspondingly, Hamiltonian operator $\hat H=-\dfrac{\hbar^2}{2m}\nabla^2+V$ with $\hat p = -i\hbar\nabla$, it goes

$$i\hbar\dfrac{\partial}{\partial t}\Psi=\hat H\Psi$$

## collapse

wave function—initially in a superposition of several eigenstates—reduces to a single eigenstate due to the **measurement**

![6edb24176861eaf0f63a674f595d26fd.png](:/d460236a25d0443c820bbc1776dd1d62)

When making a second measurement immediately after the first we will get the same result because of the collapsing. However the wave function spread out again soon.

# chap2. Time-independent Schrödinger equation



## stationary state
**Q:** Is there a difference with time-independent states and stationary states in the Schrodinger's equation?

**A:** If you talk about stationary currents, or stationary states, it means that it is actually moving, there is actually a time dependence (a transport), but you don't see it, because what is transported away is replaced again. So, a stationary current is a current; a time dependence, a charge transport but the current itself is time independent. What flows away flows back again.

The wave function, i.e., the state itself, is time-dependent, i.e. something flows away and is replaced at the other end, so that the overall probability of residence does not change. The probability that the particles can be found in location A is at any time the same in the sense it is stationary but the states <font color = #0f2541>themselves</font> are time-dependent. Stationary states are time-dependent!


## One-d infinite potential Well

consider the potential 

$$V(x) = \begin{cases}0  & 0<x<a \\ \infty & \text{otherwise}\end{cases}$$

## Simple harmonic oscillator

$$V(x) = \frac 12 kx^2 = \frac 12 m\omega ^2 x^2$$

The time-independent Schrodinger equation (TISE) goes

$$\frac 1{2m}\left[  \hat p^2+(m\omega x)^2   \right] \psi = E\psi$$

**<font color=#ff0000>Ladder operators</font>** 

$$\hat a_\pm \equiv \dfrac{1}{\sqrt{2m\hbar \omega}} (\mp i\hat p + m\omega x) $$

The $\hat a_+$ is called **raising operator**, while $\hat a_{-}$ is **lowering operator**, ~~and obviously they are the complex conjugates of each other.~~  $i\hat p$~~is actually a real operator, as $\hat p= -i\hbar \nabla$~~. Howvere, they are the <font color=red>Hermitian conjugates</font> of each other. $\hat a_-$ is sometimes written as $\hat a$, and thus $\hat a_+$ can be written as $\hat a^\dagger$

$$\hat a_-\hat a_+ = \dfrac{1}{ {2m} \hbar \omega} \left[{\hat p^2 + (m\omega x)^2} \right]  - \dfrac{i}{2\hbar} [\hat x,\hat p]=\dfrac{\hat H}{\hbar \omega} + \dfrac{1}{2} $$
The second step is according to [canonical commutation relation](#jump1) that suggest $[\hat x,\hat p ]=i\hbar$ . And $\hat a_+\hat a_- = \dfrac{\hat H}{\hbar \omega} - \dfrac{1}{2}$, so their commutator can be calculated to be $1$
$$[\hat a_-,\hat a_+] =  \hat a_-\hat a_+ - \hat a_+\hat a_- =1$$

So we can rewrite the Hamiltonian by ladder operators
$$\hat H = \hbar\omega(\hat a_-\hat a_+ - {1 \over 2})  \quad or \quad \hat H =  \hbar\omega(\hat a_+\hat a_- + {1 \over 2})  $$

With these two formulas, we are now going to prove that $\hat a_-\psi$ is a solution to the TISE with energy $E-\hbar \omega$, which is $\color{red}{\hat H(\hat a_-\psi) = (E-\hbar \omega)(\hat{a}_{-} \psi)}$:
$$
\begin{aligned}
\hat{H}\left(\hat{a}_{-} \psi\right) &=\hbar \omega\left(\hat{a}_{-} \hat{a}_{+}-\frac{1}{2}\right)\left(\hat{a}_{-} \psi\right)=\hbar \omega \hat{a}_{-}\left(\hat{a}_{+} \hat{a}_{-}-\frac{1}{2}\right) \psi \\
&=\hat{a}_{-}\left[\hbar \omega\left(\hat{a}_{-} \hat{a}_{+}-1-\frac{1}{2}\right) \psi\right]=\hat{a}_{-}(\hat{H}-\hbar \omega) \psi=\hat{a}_{-}(E-\hbar \omega) \psi \\
&=(E-\hbar \omega)\left(\hat{a}_{-} \psi\right)
\end{aligned}
$$
Similarly, $\color{red}{\hat H(\hat a_+\psi) = (E+\hbar \omega)(\hat{a}_{+} \psi)}$ is also established, and those are why they are called *ladder operators*. 

If we use lowering operator $\hat a_-$ on $\psi$ multiple times, we end up with TISE with energy $0$ and cannot use it anymore, which is to say, $\exist \psi_0$ makes that there is no state whose wavefunction is $\hat a_-\psi_0$, as a result, its wavefunction can't be normalized for it is 0 everywhere, i.e.
$$\hat a_-\psi_0 = 0$$
Here $\psi_0$ is <font color=blue>ground state</font>, which can be obtained by solving the above equation, with $\hat a_- = \dfrac{1}{2m\hbar\omega}(i\hat p+m\omega x)$ and $\hat p = -i\hbar\dfrac{\partial}{\partial x}$, the equation goes
$$\dfrac{1}{2m\hbar\omega}\left( \hbar\dfrac{\partial}{\partial x}  + m\omega x\right)\psi_0 = 0$$
Solve the equation and introduce the normalization condition ($\int |\psi_0|^2 \mathrm d x= 1$), we can get the ground state
$$\psi_{0}(x)=\left(\frac{m \omega}{\pi \hbar}\right)^{1 / 4} e^{-\frac{m \omega}{2 \hbar} x^{2}}$$

We simply apply the raising operator (repeatedly) to generate the <font color=red>excited states</font>, increasing the energy by $\hbar \omega$ with each step



$$\psi_{n}=\frac{1}{\sqrt{n !}}\left(\hat{a}_{+}\right)^{n} \psi_{0},\quad \text{with}\quad E_n = (n+\dfrac12 )\hbar \omega$$



<center> 

![SHO](:/794af24ff395404797644df41113ba26) </center>
How we determinated coefficient:
$$\braket{\hat a_+\psi|\hat a_+\psi} = \braket{ \psi | \hat a_-\hat a_+\psi   }= \left(\dfrac{E}{\hbar \omega} + \dfrac12\right)\braket{\psi|\psi}=    (n+1)\braket{\psi|\psi} $$
here we used $E = (n+1/2)\hbar\omega$ and $\braket{\psi_n|\psi_n} = \braket{\psi_{n+1}|\psi_{n+1}} = 1$ (normalization). Simlarly
$$\braket{\hat a_-\psi|\hat a_-\psi} = n\braket{\psi|\psi}$$
So, we get those two formulas:
$$\hat a_+\psi_n = \sqrt{n+1}\,\psi_{n+1}  \quad   \hat a_-\psi_n = \sqrt{n}\,\psi_{n-1}$$

## Free particle

# chap3. Formalism
## inner product

- conjugate symmetric(共轭对称)
$$
        \braket{f|g} = \braket{g|f}^\dagger
$$
- conjugate linear(共轭线性)
    $$\begin{cases}
		\braket{af|g} = a^\dagger\braket{f|g}\quad \braket{f|bg} = b\braket{f|g}\\
        \braket{af_1+bf_2|g} = a^\dagger\braket{f_1|g}+ b^\dagger\braket{f_2|g}\\
        \braket{f|ag_1+bg_2} = a\braket{f|g_1}+ b\braket{f|g_2}
    \end{cases}$$
- The inner product of an element with itself is positive definite
    $$
        \braket{f|f} \ \begin{cases}
            >0 &x\neq 0\\
            =0 &x=0  
        \end{cases}
   $$
   
## uncertainty principle
In QM, the **uncertainty** $\sigma$ of a observable $\hat O$ is its variance.
$$\sigma^2 = \braket{(\hat O-\braket{\hat O})^2} = \braket{O^2} - \braket{O}^2$$
consider a wave function $\psi$ satisfies $\braket{\hat x} = 0,\braket{\hat p}=0$, as a result,
$$\begin{cases}
\sigma^2_p = \braket{\hat p^2} - \braket{\hat p}^2 =\braket{\hat p^2} = \braket{\psi|\hat p^2\psi} \\
\sigma^2_x = \braket{\hat x^2} - \braket{\hat x}^2 =\braket{\hat x^2} = \braket{\psi|\hat x^2\psi}
\end{cases}$$
Next consider a one-parameter ($s\in\mathbb R$) family of states $\Psi_s = (\hat p-is\hat x)\psi$. Because every wave function lives in **Hilbert space**, $\Psi_s$ satisfies
$$\braket{\Psi_s|\Psi_s} =\braket{(\hat p-is\hat x)\psi|(\hat p-is\hat x)\psi} \ge 0$$
Obviously, $(\hat p-is\hat x)^\dagger = (\hat p+is\hat x)$  , hence
$$\braket{\Psi_s|\Psi_s} =\braket{\psi|(\hat p+is\hat x)(\hat p-is\hat x)\psi} = \braket{\psi|(\hat p^2+is[\hat x,\hat p]+s^2\hat x^2)\psi}\ge 0$$
with $[\hat x,\hat p]=i\hbar$, we get 
$$\braket{\psi|(\hat p^2-s\hbar+s^2\hat x^2)\psi}\ge 0 \rightarrow \sigma^2_p-s\hbar+s^2\sigma^2_x \ge 0 $$
This is a quadratic equation for $s$, to greater than or equal to 0, it satisfies
$$\hbar^2-4\sigma^2_x\sigma^2_p\le0$$
After transposition and taking square root, it goes the form of **Heisenberg uncertainty relation** 
$$\sigma_x\sigma_p\ge\dfrac{\hbar}{2}$$
### Energy-Time uncertainty principle
**Generalized Ehrenfest theorem**
$$\frac{d}{d t}\langle Q\rangle=\frac{i}{\hbar}\langle[\hat{H}, \hat{Q}]\rangle+\left\langle\frac{\partial \hat{Q}}{\partial t}\right\rangle$$

# QM in 3D

## Angular Momentum L
Commutation relations of angular momentum $\bf L$
$$[\hat L_i, \hat L_j] = i\hbar \epsilon_{ ijk} \hat L_k$$
eigenvalues of opertators ($[L^2,L_z] = 0$, where $L_z = - i\hbar \dfrac{\partial}{\partial \phi}$)
$$H\psi = E\psi \quad L^2\psi = \hbar^2l(l+1)\psi \quad L_z \psi = \hbar m \psi$$


## Spin
Commutation relations of instrinsic angular momentum $\bf S$
$$[\hat S_i, \hat S_j] = i\hbar \epsilon_{ ijk} \hat S_k$$
eigenvalues of opertators ($[S^2,S_z] = 0$, where $S_z =$)
$$S^2\ket{s\ m} = \hbar^2s(s+1)\ket{s\ m} \quad S_z \ket{s\ m} = \hbar m \ket{s\ m}$$
**the spin** $s$ is a special and imutable number for any given particle. 
$$s = 0,\dfrac 12,1,\dfrac 32,\cdots;\quad m=-s,-s+1,\cdots,s-1,s$$

## Spin 1/2
$s = 1/2$ is the spin of the particles that make up ordinary matter (protons, neutrons, and electrons). When $s=1/2$, there are two cases, namely $m=\pm 1/2$
$$\ket{\frac 12\  \frac 12} \rightarrow\cal X_+ \quad \ket{\frac 12 \ -\frac 12}\rightarrow\cal X_-$$


### Pauli matrices
$$\sigma_x = \begin{pmatrix} 0 & 1\\ 1&0 \end{pmatrix} \quad \sigma_y = \begin{pmatrix} 0 & -i\\ i&0 \end{pmatrix} \quad \sigma_z = \begin{pmatrix} 1 & 0\\ 0&-1 \end{pmatrix}$$

$$[{\sigma_i},{\sigma_j}] = 2i\epsilon_{ijk}\sigma_k $$



## Two-Electron System
consider two electrons that spin 1/2
- uncoupled representation(非耦合表象), using $\ket{s_1 \,m_1\,s_2\,m_2}$
$${span} \{\ket{\uparrow\uparrow}   , \ket{\downarrow\downarrow} ,   \ket{\uparrow\downarrow} , \ket{\downarrow\uparrow} \}$$

- coupled represemtation $\ket{S\,M\,s_1\,m_1}$
$$span\{    \ket{1\,1} , \ket{1 \,-1}, \ket{1\,0}      ,\ket{0\,0}  \}$$

to transform:
$$\begin{cases}
    \ket{1 \quad1} &= \ket{\uparrow\uparrow} \\
    \ket{1\ {-1}} &= \ket{\downarrow\downarrow} \\
    \ket{1\quad 0} &= \frac{1}{\sqrt{2}}\left(\ket{\uparrow\downarrow} + \ket{\downarrow\uparrow} \right) \\
    \ket{0\quad 0} &= \frac{1}{\sqrt{2}}(\ket{\uparrow\downarrow} - \ket{\downarrow\uparrow})
\end{cases}$$
