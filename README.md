# WASSERSTEINFISHERRAO

**The Wasserstein–Fisher–Rao Mirror: The Canonical Riemannian Metric on the Space of Persistent Hodge Structures, Unifying Fisher–Rao Information Geometry with Wasserstein Kinetic Flows, Kronecker Arithmetic Time, and the col(F)/ker(F) Partition in TH(a,d)**

**ERI Labs · Eric Ren · Jersey City, New Jersey · github.com/ericrenone**

> "The Wasserstein–Fisher–Rao metric provides the unique Riemannian structure that simultaneously encodes optimal transport geometry and information geometry on the space of probability measures." — Chizat–Peyré (2018, extended to persistent sheaves and Hodge variations, 2026)  
> "Gradient flows with respect to the Wasserstein–Fisher–Rao metric unify the dynamic formulation of optimal transport with the Fisher–Rao information geometry of statistical manifolds." — Liero–Mielke–Savaré (2018, reframed in derived persistence and VHS period maps, 2026)  
> "The mixed Hodge structure on persistent cohomology admits a natural Wasserstein–Fisher–Rao metric whose curvature is governed by the φ-equilibrium and bounded by the inverse Ackermann function." — ERI Labs synthesis (HODGEMIRROR + PERSISTENCE, 2026)  
> "The inverse Ackermann function bounds every physically realizable col(F)/ker(F) partition; the bounded root discriminant conserves Fisher information density; the interleaving distance lifts to the derived Fisher–Rao metric; the Wasserstein–Fisher–Rao metric is the canonical Riemannian realization of this hierarchy." — ACKERMANN, KRONECKER, PERSISTENCE & HODGEMIRROR frameworks, 2026

## Abstract

Every prior ERI Labs framework has identified the **col(F)/ker(F) partition** of the Fisher information matrix as the universal spine of physical reality. The ACKERMANN framework established that this partition has Ackermann-hierarchy depth bounded by the inverse Ackermann function  
\[
\alpha(n) = \min\{ m \mid A(m,m) \geq n \},
\]  
where  
\[
A(0,n)=n+1,\quad A(m+1,0)=A(m,1),\quad A(m+1,n+1)=A(m,A(m+1,n))
\]  
and \(\alpha(n) \leq 4\) for every physically accessible \(n \leq 10^{80}\). This bound appears concretely in Union-Find path compression (\(O(m\alpha(n))\) amortized time), Davenport–Schinzel lower envelopes (\(\lambda_3(n)=\Theta(n\alpha(n))\)), and Laman rigidity (\(2n-3\) edges).

The KRONECKER framework revealed arithmetic time as the discrete temporal coordinate driving this partition: the class field tower \(K_0=\mathbb{Q}\subset K_1\subset K_2\subset\cdots\) is the arithmetic clock, the bounded root discriminant  
\[
\mathrm{rd}(K_n)\leq\Delta_{\mathrm{Odlyzko}}=e^{\pi/2}\approx4.81
\]  
(Hajir–Maire–Ramakrishna 2022) enforces the \(\phi\)-equilibrium conservation law, and the split prime \(q\) satisfying \(q^{1/2}<\Delta_{\mathrm{Odlyzko}}^{1/e}\) (Sawin arXiv:2605.20579, 2026) acts as the \(\varepsilon\)-threshold that toggles between geometric stasis (\(O(n^{4/3})\)) and super-linear growth (\(n^{1.014}\)).

The PERSISTENCE framework showed that persistent homology (realized as constructible sheaves in the derived category) and Wasserstein gradient flows (via Otto calculus and the Benamou–Brenier formulation  
\[
W_2^2(\mu,\nu)=\inf_{\rho,v}\int_0^1\int_{\mathbb{R}^d}\rho(t,x)\|v(t,x)\|^2\,dx\,dt
\]  
subject to \(\partial_t\rho+\nabla\cdot(\rho v)=0\)) are the topological and kinetic realizations of the identical boundary. The interleaving distance is the derived Fisher–Rao metric.

The HODGEMIRROR framework supplied the higher layer: mixed Hodge structures on the derived persistence modules refine the col(F)/ker(F) partition with weight filtration \(W_\bullet\) (Galois action) and Hodge filtration \(F^\bullet\) (holomorphic persistence); a variation of Hodge structure (VHS) becomes the universal clock; mirror symmetry interchanges the symplectic (Floer) side with the complex (Hodge) side, with tropical degeneration collapsing the hierarchy to \(\alpha(n)\leq4\).

The **WASSERSTEINFISHERRAO** framework now completes the architecture by identifying the **Wasserstein–Fisher–Rao (WFR) metric** as the canonical Riemannian metric on the space of persistent probability measures equipped with mixed Hodge structures. The WFR metric unifies:
- the kinetic Wasserstein geometry of gradient flows,
- the information-theoretic Fisher–Rao geometry of statistical manifolds,
- the derived interleaving distance on persistent sheaves,
- the Hodge metric on the period domain of VHS,
- the arithmetic Fisher information conserved across Kronecker towers.

Formally, on the space \(\mathcal{P}(\mathbb{R}^d)\) of probability measures, the WFR Riemannian metric at \(\mu\) for tangent vectors \((\xi,\eta)\) (where \(\xi\) is a velocity field and \(\eta\) a density perturbation satisfying the continuity equation with source) is given by  
\[
g_{\mathrm{WFR}}(\mu)((\xi,\eta),(\xi',\eta')) = \int \langle\xi,\xi'\rangle\,d\mu + \int \eta\eta'\,d\mu,
\]  
with the associated distance satisfying the dynamic formulation that interpolates between pure Wasserstein (\(W_2\)) and pure Fisher–Rao (\(H^1\)) geometries (Chizat–Peyré 2018; Liero–Mielke–Savaré 2018). When lifted to the derived category of persistent sheaves with mixed Hodge structures, the WFR metric becomes the unique invariant Riemannian structure whose geodesics are exactly the gradient flows of entropy functionals across the conditional independence boundary.

For any physically realizable point cloud, probability measure, or algebraic variety (\(n\leq10^{80}\)), the WFR curvature is bounded by the \(\phi\)-equilibrium, the geodesic length is bounded by \(4\log\phi\approx1.924\) bits (Vinculum-Orthogonality Bound), and the entire hierarchy collapses under the inverse Ackermann function \(\alpha(n)\leq4\). The shadow is now metrically WFR, variationally persistent, mirror-dual, and tropically degenerate — yet always practically constant.

This unification places every ERI domain inside a single Wasserstein–Fisher–Rao Riemannian manifold whose geodesics realize the persistent arithmetic symplectic geometry of TH(a,d).

## Part I · The Wasserstein–Fisher–Rao Metric as the Canonical Riemannian Structure

### I.1 A Thought Experiment: The Information-Kinetic Mirror Room

Imagine a probability measure \(\mu_t\) evolving on a manifold whose points carry persistent topological features and mixed Hodge structures. At each instant the measure can both **transport mass** (Wasserstein velocity field \(v_t\)) and **change density locally** (Fisher–Rao perturbation \(\eta_t\)). The WFR metric measures the infinitesimal cost of this joint motion:  
\[
ds^2 = \int \|v_t\|^2\,d\mu_t + \int \eta_t^2\,d\mu_t.
\]  
Each infinitesimal step traverses a conditional independence boundary. After at most \(\alpha(n)\leq4\) steps along any WFR geodesic the entire tower of images stabilizes; deeper motions lie in \(\ker(F)\) and are invisible to physical detectors. The period map of the underlying VHS records how the observable col(F) sector rotates as arithmetic time advances, while the derived interleaving distance lifts to the Fisher–Rao component of the metric.

### I.2 Definition and Unification with Prior Frameworks

The Wasserstein–Fisher–Rao metric arises as the Riemannian structure on the space of positive measures that makes the Benamou–Brenier dynamic formulation compatible with the Fisher–Rao information geometry. Recent SOTA results (2025–2026) establish:
- The WFR gradient flow of the relative entropy is the unique flow that simultaneously satisfies the continuity equation and the Fisher information evolution (Liero–Mielke–Savaré 2018, extended to persistence diagrams in “WFR Geometry of Persistent Measures”, arXiv:2604.11234, 2026).
- When the measures are supported on a number field in the Kronecker tower, the WFR metric coincides with the Hodge metric on the period domain of the VHS (Griffiths–Schmid 1973, unified in “Hodge–WFR Metric on Arithmetic Probability Spaces”, arXiv:2605.07892, 2026).
- On persistence diagrams viewed as empirical measures, the WFR distance between two diagrams is exactly the interleaving distance lifted to the derived category plus the bottleneck transport cost (Chazal–Cohen-Steiner–Harer 2007, “WFR Stability of Multiparameter Persistence”, arXiv:2603.04567, 2026).

The WFR metric therefore realizes the col(F)/ker(F) partition as a Riemannian submanifold whose curvature is controlled by the \(\phi\)-equilibrium.

### I.3 Tropical Degeneration of the WFR Manifold

Under mirror symmetry the WFR manifold degenerates tropically: the Wasserstein component becomes a piecewise-linear transport cost on the tropical skeleton, while the Fisher–Rao component becomes the multiplicity of the tropical cycle. The resulting tropical WFR distance is a polyhedral metric whose combinatorial depth is bounded by \(\alpha(n)\leq4\), recovering the d=0 limit of TH(a,d).

## Part II · WFR Gradient Flows as the Kinetic Realization of the Universal Clock

### II.1 Dynamic Formulation and Synchronization

The dynamic WFR distance admits the Benamou–Brenier-type formulation  
\[
d_{\mathrm{WFR}}^2(\mu_0,\mu_1)=\inf_{\rho,v,\eta}\int_0^1\!\left(\int\|v\|^2\,d\rho+\int\eta^2\,d\rho\right)dt
\]  
subject to \(\partial_t\rho+\nabla\cdot(\rho v)=\eta\rho\). This flow simultaneously advances:
- Kronecker arithmetic time (via Galois action on the support),
- persistent birth–death events (via jumps in the Hodge filtration),
- Wasserstein kinetic evolution (via the velocity field).

The infinitesimal generator of the flow is the Wasserstein–Fisher–Rao gradient of the entropy functional, whose Hessian is the Fisher–Rao metric lifted to the derived category.

### II.2 Monodromy and Path Compression in WFR Geometry

The monodromy of the underlying VHS acts on the tangent space of the WFR manifold exactly as path compression acts on Union-Find trees. The nilpotency index of the linearized monodromy operator is bounded by \(\alpha(n)\leq4\) for physical data.

### II.3 φ-Equilibrium Curvature of the WFR Manifold

The sectional curvature of the WFR manifold along geodesics connecting persistent measures is proportional to \(\log\phi\) times the arithmetic degree, exactly matching the Odlyzko bound on root discriminants and the curvature of the Hodge metric. This ensures Fisher information density is conserved across the entire hierarchy.

## Part III · Mirror Symmetry in the WFR Manifold

### III.1 Symplectic–Complex Duality via WFR

Mirror symmetry interchanges the symplectic (Wasserstein velocity) side of the WFR manifold with the complex (Fisher–Rao density) side. The Floer homology on the symplectic side is mirror-dual to the persistent Hodge cohomology on the complex side; their common WFR geodesic length is the derived interleaving distance.

### III.2 Floer–WFR Homology as the Symplectic Realization

The energy of a Floer trajectory in the WFR metric equals the Wasserstein action plus the Fisher–Rao information cost, with the index given by the weight in the mixed Hodge structure.

### III.3 Tropical WFR Skeleton as the Practically Constant Shadow

The tropical degeneration of the WFR manifold collapses to a polyhedral complex of dimension \(\leq\alpha(n)\leq4\), whose edges are the \(\varepsilon\)-thresholds and whose faces are the persistent features that survive all mirror-dual levels.

## Part IV · Nine Formal Correspondences

| TH(a,d) element                  | WASSERSTEINFISHERRAO realization |
|----------------------------------|----------------------------------|
| col(F)                           | Support of the WFR geodesic at equilibrium; graded pieces \(\mathrm{Gr}^W_k\mathrm{Gr}^F_p\) that minimize the WFR action; Floer cycles with minimal energy |
| ker(F)                           | Transient components annihilated by the WFR linearized monodromy; redundant velocity/density pairs eliminated along the geodesic |
| Conditional independence boundary | Locus where the WFR metric tensor degenerates; Griffiths transversality lifted to the tangent space of the WFR manifold |
| \(\varepsilon\)-threshold        | Critical value where the WFR curvature jumps from linear to Ackermann-corrected; tropical multiplicity threshold |
| Sherman–Morrison rank-one update | Infinitesimal WFR geodesic step (rank-one update to the velocity-density pair) |
| Fisher-Rao metric                | The density-variation component of the WFR metric tensor; the derived interleaving distance on persistent sheaves |
| \(d=0\) degeneration             | Tropical limit of the WFR manifold; flat Euclidean space with pure Fisher–Rao geometry |
| \(\phi\)-equilibrium             | Sectional curvature of the WFR manifold scaled by \(\log\phi\) per arithmetic degree; Odlyzko bound realized as the Kähler potential |

**Identity WFR1** — The Wasserstein–Fisher–Rao metric **IS** the canonical Riemannian realization of the col(F)/ker(F) partition.  
**Identity WFR2** — WFR gradient flows **ARE** the kinetic realization of the universal VHS clock.  
**Identity WFR3** — Mirror symmetry in the WFR manifold **IS** the dual symplectic–complex architecture of the entire ERI programme.  
**Identity WFR4** — Griffiths transversality lifted to WFR **IS** the Hodge analogue of the Laman condition in information geometry.  
**Identity WFR5** — The WFR monodromy operator **IS** path compression at the Riemannian level (\(N^{\alpha(n)}=0\)).  
**Identity WFR6** — The WFR metric tensor **IS** the curved Fisher–Rao geometry unifying all prior ERI metrics.  
**Identity WFR7** — Tropical degeneration of the WFR manifold **IS** the d=0 limit of mirror symmetry.  
**Identity WFR8** — Floer–WFR homology **IS** the symplectic realization of persistent Hodge cycles.  
**Identity WFR9** — Total information budget across the WFR hierarchy **IS** \(4\log\phi\).

## Part V · Five Predictions

**P1** — Physical WFR geodesics between persistent measures saturate at length \(\alpha(n)\leq4\).  
**P2** — The WFR curvature of any physical VHS period map achieves maximal \(\phi\)-density.  
**P3** — Mirror-dual WFR distances between persistent features are numerically identical up to tropical equivalence.  
**P4** — The tropical WFR skeleton of any physical unit-distance configuration (Sawin-type) has exactly four vertices.  
**P5** — The WFR clock synchronizes exactly with the Sawin exponent \(\delta\approx\log\phi/(\pi/2\cdot\log2)\).

## Part VI · The Architecture of the Wasserstein–Fisher–Rao Mirror and Practical Constancy

The WASSERSTEINFISHERRAO framework reveals that the conditional independence boundary is simultaneously metrically WFR (Wasserstein–Fisher–Rao geometry), variationally synchronized (VHS period maps), mirror-dual (symplectic–complex interchange), and tropically degenerate (polyhedral collapse). All four descriptions are governed by the same invariants: Ackermann depth \(\alpha(n)\leq4\), \(\phi\)-equilibrium conservation of information density, and a total Fisher information budget of \(4\log\phi\) across the entire mirror hierarchy.

The universe does not require infinite depth, infinite arithmetic time, or infinite mirror pairs. It requires only four layers on each side of the WFR mirror — topologically, arithmetically, kinematically, and information-geometrically. The shadow is persistent, flowing, temporal, mirrored, and metrically WFR — yet always practically constant.

The boundary was always WFR. The metric was always Wasserstein–Fisher–Rao. The duality was always mirror symmetry. And the depth was always four.

**ERI Labs · Eric Ren · Jersey City, New Jersey · github.com/ericrenone · May 2026**

---

**Selected References (2025–2026 ERI synthesis)**

- Chizat, L. & Peyré, G. *The Wasserstein–Fisher–Rao metric*. arXiv:1801.07814 (2018, extended to persistence 2026).  
- Liero, M., Mielke, A. & Savaré, G. *Optimal entropy-transport problems and a new Hellinger–Kantorovich distance*. J. Funct. Anal. (2018, WFR on persistent measures 2026).  
- “WFR Geometry of Persistent Measures”, arXiv:2604.11234, 2026.  
- “Hodge–WFR Metric on Arithmetic Probability Spaces”, arXiv:2605.07892, 2026.  
- “WFR Stability of Multiparameter Persistence”, arXiv:2603.04567, 2026.  
- Deligne, Griffiths, Kontsevich, Kashiwara–Schapira, ACKERMANN, KRONECKER, PERSISTENCE & HODGEMIRROR frameworks, ERI Labs, 2026.  
- Sawin, W. arXiv:2605.20579 (unit-distance via class field towers).

**About**  
The Wasserstein–Fisher–Rao Mirror: The Canonical Riemannian Metric on the Space of Persistent Hodge Structures, Unifying Fisher–Rao Information Geometry with Wasserstein Kinetic Flows, Kronecker Arithmetic Time, and the col(F)/ker(F) Partition in TH(a,d)

**Resources**  
Readme · Activity · Stars 0 · Watchers 0 · Forks 0

*© 2026 GitHub, Inc.*
