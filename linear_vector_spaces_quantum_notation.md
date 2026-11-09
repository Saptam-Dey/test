# Linear Vector Spaces, Dirac Notation, and Matrix Algebras

## Table of Contents

* [1. Fundamentals of Linear Vector Spaces and Dirac Notation](#1-fundamentals-of-linear-vector-spaces-and-dirac-notation)

* 2\. Dual Spaces, Inner Products, Basis Sets, and Dimensionality

* 3\. Orthonormal Basis Sets, Gram-Schmidt Procedure, and Vector Inequalities

* 4\. Pauli Matrices, Matrix Exponentials, 3D Rotations, and Secular Equations

### 1. Fundamentals of Linear Vector Spaces and Dirac Notation

A Linear Vector Space (LVS) $V$ over a scalar field $\mathbb{F}$ (where $\mathbb{F} = \mathbb{R}$ or $\mathbb{C}$) is a set of elements (vectors) closed under vector addition and scalar multiplication.

#### Vector Addition Axioms

Vector addition defines a mapping $V \times V \to V$ that satisfies the following properties for all $\vert{}\phi\rangle, \vert{}\psi\rangle, \vert{}\chi\rangle \in V$:

* **Commutativity:**

  $$
  \vert{}\phi\rangle + \vert{}\chi\rangle = \vert{}\chi\rangle + \vert{}\phi\rangle
  $$

* **Associativity:**

  $$
  \vert{}\phi\rangle + (\vert{}\psi\rangle + \vert{}\chi\rangle) = (\vert{}\phi\rangle + \vert{}\psi\rangle) + \vert{}\chi\rangle
  $$

* **Existence of a Unique Null Vector (**$\vert{}\Omega\rangle = 0$**):**

  $$
  \vert{}\phi\rangle + \vert{}\Omega\rangle = \vert{}\phi\rangle
  $$

* **Existence of a Unique Additive Inverse (**$-\vert{}\phi\rangle$**):**

  $$
  \vert{}\phi\rangle + (-\vert{}\phi\rangle) = \vert{}\Omega\rangle
  $$

#### Scalar Multiplication Axioms

Scalar multiplication defines a mapping $\mathbb{F} \times V \to V$ for scalars $a, b \in \mathbb{F}$ satisfying:

* **Closure:** $a\vert{}\psi\rangle \in V$

* **Scalar Associativity:** $a(b\vert{}\psi\rangle) = (ab)\vert{}\psi\rangle$

* **Distributivity over Vector Addition:** $a(\vert{}\psi\rangle + \vert{}\phi\rangle) = a\vert{}\psi\rangle + a\vert{}\phi\rangle$

* **Distributivity over Scalar Addition:** $(a+b)\vert{}\psi\rangle = a\vert{}\psi\rangle + b\vert{}\psi\rangle$

* **Identity and Zero Elements:** $1\vert{}\psi\rangle = \vert{}\psi\rangle$ and $0\vert{}\psi\rangle = \vert{}\Omega\rangle = 0$

#### Dirac Notation & Physical Examples

* **Dirac Notation:** Introduced by Paul Dirac for quantum mechanics, abstract vectors are represented as "ket" vectors $\vert{}\psi\rangle$.

* **Examples of Linear Vector Spaces:**

  * **Euclidean Space (**$\mathbb{R}^3$**):** Represented by $3 \times 1$ column vectors:
    

    $$
    \vert{}\mathbf{v}\rangle = \begin{pmatrix} x \\ y \\ z \end{pmatrix}
    $$

  * **Differential Equation Solutions:** The space of solutions to $\frac{d^2y}{dt^2} = -\omega^2 y$ forms a 2D vector space spanned by linearly independent basis functions $y_1(t) = e^{i\omega t}$ and $y_2(t) = e^{-i\omega t}$ (or $\cos(\omega t)$ and $\sin(\omega t)$).

  * **Tuple Spaces:** Real or complex $n$-tuples $(\mathbb{R}^n, \mathbb{C}^n)$.

  * **Matrix Spaces:** The space of all $m \times n$ matrices under entrywise addition.

  * **Binary Field Spaces:** Spaces defined over binary fields $\{0, 1\}$ with arithmetic rules $1+0=1$, $1+1=0$, $0 \times 1 = 0$, and $1 \times 1 = 1$.

> ✍️ **Added by:** Saptam, 2026-11-08

### 2. Dual Spaces, Inner Products, Basis Sets, and Dimensionality

Dual spaces associate linear functionals with vectors, generalizing metric concepts such as vector lengths and dot products.

#### Dual Space ($\tilde{V}$)

The collection of all linear functionals $S_\phi[\cdot]$ mapping vectors to scalars forms a dual vector space $\tilde{V}$. Elements of $\tilde{V}$ are represented as "bra" vectors $\langle\phi\vert{}$.

* **Dual Functional Properties:**

  $$
  S_{\phi+\chi}[\cdot] = S_\phi[\cdot] + S_\chi[\cdot] \quad \text{and} \quad S_{a\phi}[\cdot] = a^* S_\phi[\cdot]
  $$

* **Self-Duality:** $\tilde{\tilde{V}} \equiv V$. In 3D Euclidean space, ket vectors are $3 \times 1$ columns while bra vectors are $1 \times 3$ row vectors $\langle\psi\vert{} = (d \ e \ f)$.

#### Inner Product & Norm

An inner product is a bilinear mapping $\langle\phi\vert{}\psi\rangle$ pairing a bra and a ket to yield a scalar:

* **Linearity in the Ket:**

  $$
  \langle\phi\vert{} ( \vert{}\psi\rangle + \vert{}\chi\rangle ) = \langle\phi\vert{}\psi\rangle + \langle\phi\vert{}\chi\rangle \quad \text{and} \quad \langle\phi\vert{} a\psi\rangle = a\langle\phi\vert{}\psi\rangle
  $$

* **Anti-linearity in the Bra:**

  $$
  \langle a\phi\vert{}\psi\rangle = a^*\langle\phi\vert{}\psi\rangle
  $$

* **Conjugate Symmetry:**

  $$
  \langle\phi\vert{}\psi\rangle = \langle\psi\vert{}\phi\rangle^*
  $$

* **Norm of a Vector:** Defines magnitude in an inner-product space:
  

  $$
  \vert{}\vert{}\psi\vert{}\vert{} = \sqrt{\langle\psi\vert{}\psi\rangle}
  $$

#### Basis Sets & Dimensionality

* **Linear Independence:** A set of vectors $\{\vert{}\psi_k\rangle\}$ is linearly independent if:
  

  $$
  \sum_k a_k \vert{}\psi_k\rangle = 0 \implies a_k = 0 \quad \forall k
  $$

* **Spanning Property:** A set spans $V$ if any vector $\vert{}\gamma\rangle \in V$ can be expressed as:
  

  $$
  \vert{}\gamma\rangle = \sum_k b_k \vert{}\psi_k\rangle
  $$

* **Dimensionality (**$n$**):** The number of basis vectors in an LVS is unique and invariant. Every $n$-dimensional inner-product space over $\mathbb{C}$ is isomorphic to $\mathbb{C}^n$.

* **Infinite-Dimensional Spaces:** Spaces requiring an infinite basis set, such as the space of all continuous functions or polynomials of a complex variable $z$.

> ✍️ **Added by:** Arpita, 2026-11-09

### 3. Orthonormal Basis Sets, Gram-Schmidt Procedure, and Vector Inequalities

Orthonormal bases simplify vector expansions into component projections and preserve vector norms.

#### Orthonormality & Completeness

* **Orthonormality Condition:**

  $$
  \langle\phi_j\vert{}\phi_k\rangle = \delta_{jk}
  $$

  
  where $\delta_{jk}$ is the Kronecker delta ($\delta_{jk}=1$ if $j=k$, else $0$).

* **Completeness Relation (Resolution of Identity):**
  

  $$
  \sum_j \vert{}\phi_j\rangle\langle\phi_j\vert{} = I
  $$

* **Operator Action:** The outer product $\vert{}\phi\rangle\langle\psi\vert{}$ acts on a ket $\vert{}\gamma\rangle$ via:
  

  $$
  (\vert{}\phi\rangle\langle\psi\vert{})\vert{}\gamma\rangle = \vert{}\phi\rangle(\langle\psi\vert{}\gamma\rangle)
  $$

* **Component Expansion:** For any $\vert{}\psi\rangle = \sum_k c_k \vert{}\phi_k\rangle$, the expansion coefficients are obtained by projection:
  

  $$
  c_k = \langle\phi_k\vert{}\psi\rangle
  $$

#### Gram-Schmidt Orthonormalization

Constructs an orthonormal basis $\{\vert{}\phi_k\rangle\}$ from an arbitrary linearly independent basis $\{\vert{}\psi_k\rangle\}$:

1. **Normalize the first vector:**
   

   $$
   \vert{}\phi_1\rangle = \frac{\vert{}\psi_1\rangle}{\sqrt{\langle\psi_1\vert{}\psi_1\rangle}}
   $$

2. **Iteratively subtract projections and normalize:**
   

   $$
   \vert{}\phi_k\rangle = \frac{\vert{}\psi_k\rangle - \sum_{j=1}^{k-1}\langle\phi_j\vert{}\psi_k\rangle\vert{}\phi_j\rangle}{\left[\langle\psi_k\vert{}\psi_k\rangle - \sum_{j=1}^{k-1}\vert{}\langle\phi_j\vert{}\psi_k\rangle\vert{}^2\right]^{1/2}}
   $$

#### Change of Basis & Fundamental Inequalities

* **Parseval's Identity:** Inner products and norms are invariant under basis transformations:
  

  $$
  \langle\psi_A\vert{}\psi_B\rangle = \sum_k c_k^* C_k = \sum_j d_j^* D_j
  $$

  $$
  \vert{}\vert{}\psi_A\vert{}\vert{}^2 = \sum_k \vert{}c_k\vert{}^2
  $$

* **Cauchy-Schwarz Inequality:** For any two vectors $\vert{}\phi\rangle$ and $\vert{}\psi\rangle$:
  

  $$
  \vert{}\langle\phi\vert{}\psi\rangle\vert{} \le \vert{}\vert{}\phi\vert{}\vert{}\,\vert{}\vert{}\psi\vert{}\vert{}
  $$

  
  *(Equality holds if and only if* $\vert{}\phi\rangle$ *and* $\vert{}\psi\rangle$ *are linearly dependent)*

* **Triangle Inequality:**
  

  $$
  \vert{}\vert{}\phi + \psi\vert{}\vert{} \le \vert{}\vert{}\phi\vert{}\vert{} + \vert{}\vert{}\psi\vert{}\vert{}
  $$

> ✍️ **Added by:** Lokesh, 2026-11-10

### 4. Pauli Matrices, Matrix Exponentials, 3D Rotations, and Secular Equations

Square matrices act either as elements of a matrix vector space or as linear operators on vector spaces.

#### Pauli Matrix Basis ($2 \times 2$ Matrices)

Any $2 \times 2$ complex matrix $M = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$ can be uniquely expanded in the basis $\{I, \sigma_1, \sigma_2, \sigma_3\}$ as $M = \alpha_0 I + \vec{\alpha}\cdot\vec{\sigma}$:

$$
I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}, \quad \sigma_1 = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \quad \sigma_2 = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}, \quad \sigma_3 = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}
$$

* **Key Properties:**

  * Hermiticity: $\sigma_i^\dagger = \sigma_i$

  * Involutory: $\sigma_i^2 = I$

  * Eigenvalues: $\lambda = \pm 1$

* **Algebraic Identities:**

  * Product Rule: $\sigma_k \sigma_l = \delta_{kl}I + i\epsilon_{klm}\sigma_m$

  * Commutator: $[\sigma_k, \sigma_l] = 2i\epsilon_{klm}\sigma_m$

  * Anti-commutator: $\{\sigma_k, \sigma_l\} = 2\delta_{kl}I$

* **Angular Momentum Generators:** $J_k = \frac{1}{2}\sigma_k$ satisfies $[J_k, J_l] = i\epsilon_{klm}J_m$.

#### Matrix Exponentials & 3D Rotations

* **Matrix Exponential Definition:**

  $$
  e^M \equiv \sum_{n=0}^{\infty} \frac{M^n}{n!}
  $$

* **Closed-Form Pauli Exponential:**

  $$
  e^{i\vec{a}\cdot\vec{\sigma}} = I\cos a + i\frac{\vec{a}\cdot\vec{\sigma}}{a}\sin a \quad (a = \vert{}\vec{a}\vert{})
  $$

* **General** $2 \times 2$ **Matrix Exponential:**

  $$
  e^{\alpha_0 I + \vec{\alpha}\cdot\vec{\sigma}} = e^{\alpha_0}\left(I\cosh\alpha + \frac{\vec{\alpha}\cdot\vec{\sigma}}{\alpha}\sinh\alpha\right) \quad (\alpha = \vert{}\vec{\alpha}\vert{})
  $$

* **Translation Operators:** $e^{a \frac{d}{dx}} f(x) = f(x+a)$ acts as a spatial translation generator.

* **3D Rotation Operator:** Rotation by angle $\psi$ around unit axis $\vec{n}$:
  

  $$
  R(\vec{n}, \psi) = e^{i\vec{J}\cdot\vec{n}\psi}
  $$

* **Rodrigues' Rotation Formula:** Vector transformation under 3D spatial rotation:
  

  $$
  \vec{r}' = \cos\psi\,\vec{r} + (1-\cos\psi)(\vec{r}\cdot\vec{n})\vec{n} + \sin\psi(\vec{r}\times\vec{n})
  $$

#### Secular Equation & Eigenvalue Invariants

* **Characteristic Polynomial:** Determined via the secular equation:
  

  $$
  P_M(\lambda) = \det(\lambda I - M) = \lambda^n + c_1 \lambda^{n-1} + \dots + c_n = 0
  $$

* **Similarity Invariants:** Eigenvalues $\{\lambda_i\}$ remain invariant under similarity transformations $M \mapsto S M S^{-1}$.

  * First coefficient: $c_1 = -\text{Tr}(M) = -\sum_i \lambda_i$

  * Last coefficient: $c_n = (-1)^n \det(M) = (-1)^n \prod_i \lambda_i$

> ✍️ **Added by:** Ritika, 2026-11-11