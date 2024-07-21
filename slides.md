---
layout: cover
lang: en-en
theme: default
coverAuthorUrl: [https://www.ugr.es/local/pedro]
title: "The isomorphism problem for ideal class monoids of numerical semigroups"
coverDate: ""
background: ""
fonts:
  # basically the text
  sans: Lato
  # use with `font-serif` css class from UnoCSS
  serif: Robot Slab
  # for code blocks, inline code, etc.
  mono: Fira Code
---
<style>
    h1,h2 {
        color: rgb(60, 122, 169);
    }
    h3,h4 {
        color: darkgrey;
    }
    .katex { font-size: 1.1em; }
</style>

## The isomorphism problem for ideal class monoids of numerical semigroups

<br>

**Pedro A. García Sánchez** <br> Departamento de Álgebra and IMAG, Universidad de Granada

<br><br>

### AMS-UMI International Joint Meeting 2024 
### Palermo, 23–26 July 2024

<br><br><br>

<p style="font-size:0.6em;  line-height: 1.5; text-align: left;">Supported by the grant number ProyExcel_00868 (Proyecto de Excelencia de la Junta de Andalucía) and by the Junta de Andalucía Grant Number FQM-343; grant PID2022-138906NB-C21 funded by MICIU/AEI/10.13039/501100011033 and by ERDF "A way of making Europe", and by the Spanish Ministry of Science and Innovation (MICINN), through the "Severo Ochoa and María de Maeztu Programme for Centres and Unities of Excellence" (CEX2020-001105-M). </p>



---

# The ideal class monoid 

Let $S$ be a numerical semigroup

An **ideal** of $S$ is a set $I$ of integers such that

- $I+S\subseteq I$
- $z+I\subseteq S$ for some integer $z$ 

Let $\mathcal{I}(S)$ be the set of ideals of $S$

We write $I\sim J$ if there exists $z\in\mathbb{Z}$ such that $I=z+J$

The **ideal class monoid** of $S$ is 

$$
 \mathcal{C}\ell(S) = \mathcal{I}(S)/\sim  
$$

Addition is defined as $[I]+[J]=[I+J]$

---

# The set of normalized ideals 

Let $\mathcal{I}_0(S) = \{ I\in \mathcal{I}(S) : \min(I)=0 \}$, the set of normalized ideals of $S$

It follows easily that

$$
\mathcal{C}\ell(S)\cong \mathcal{I}_0(S), [I]\mapsto -\min(I)+I
$$

For $I\in \mathcal{I}_0(S)$, there exists $g_1,\dots,g_k\in\operatorname{G}(S)$ such that 

$$
I=\{0,g_1,\dots,g_k\}+S
$$

Moreover, $\{g_1,\ldots,g_k\}$ can be taken to be an anti-chain with respect to 

$$a\le_S b  \text{ if } b-a\in S$$

Thus, the cardinality of $\mathcal{C}\ell(S)$ equals the number of antichains in $(\mathbb{N}\setminus S,\le_S)$

---

# Hasse diagram of normalized ideals wrt inclusion

Let $S$ be a numerical semigroup with multiplicity $m$

<Transform :scale="0.9">

<div class="grid grid-cols-[60%_40%] gap-4">

<div>

- $\min_\subseteq(\mathcal{I}_0(S))=S$
- $\max_\subseteq(\mathcal{I}_0(S))=\mathbb{N}$

- Maximal non-trivial ideals:  
    
    $\{0,1,\dots,i-1,i+m,i+1,\dots,m-1\}+S$

    $|\operatorname{Maximals}_\subseteq(\mathcal{I}_0(S)\setminus\{\mathbb{N}\})|= m-1$

- Minimal non-tivial ideals: 
    
    $\{0,f\}+S$, $f\in\operatorname{Maximals}_{\le_S}(\mathbb{Z}\setminus S)$
    
    $|\operatorname{Minimals}_\subseteq(\mathcal{I}_0(S)\setminus\{S\})| = \operatorname{t}(S)$, the type of $S$
- Height equals $|\mathbb{N}\setminus S|+1$

</div>

<div>

<figure>

<img src="/NSGraph4.svg" alt="469-ideal-min-gen" width="90%">

<figcaption align="center">

Hasse diagram of $\footnotesize{(\mathcal{I}_0(\langle 4,6,9\rangle),\subseteq)}$, nodes labelled by sets of minimal generators

</figcaption>
</figure>


</div>

</div>

</Transform>

---

# How to fully recover $S$ from $(\mathcal{I}_0(S),\subseteq)$?

**Idea**: $\{0,g\}+S\subseteq \{0,g'\}+S$ if and only if $g'\le_S g$

Thus, if we can tell apart the ideals of the form $\{0,g\}+S$, with $g\in \mathbb{N}\setminus S$, then we recover $(\mathbb{N}\setminus S,\le_S)$

Define $\mathcal{P}_0(S) = \big\lbrace {\{0,g\}+S} : g\in \mathbb{N}\setminus S \big\rbrace\subseteq \mathcal{I}_0(S)$

**Result**: An ideal $I$ is in $\mathcal{P}_0(S)$ if and only if it only covers a unique ideal in the Hasse diagram of $(\mathcal{I}_0(S),\subseteq)$

<div class="absolute left-25% top-48%">

<img src="/469-blind-inclusion.svg" alt="469-ideal" width="40%">

</div>


<div class="absolute left-55% top-60%">

<img src="/469-gaps-blind.svg" alt="469-gap" class="right" width="40%">

</div>

<!--<div class="grid grid-cols-[45%_10%_45%] gap-4">

<div>


<img src="/469-blind-inclusion.svg" alt="469-ideal" style="float:right" width="35%">


</div>

<div>

<br>

</div>

<div>

<img src="/469-gaps-blind.svg" alt="469-gap" class="right" width="40%">


</div>


</div>-->

---

# How to fully reconstruct $S$ from $(\mathbb{N}\setminus S,\le_S)$?

**Idea**: counting "divisors"

For $h\in \mathbb{N}\setminus S$, set $\operatorname{nd}(h)=|\{ h'\in \mathbb{N}\setminus S : h'\le_S h\}|$

**Result:** For every $h,h'\in \mathbb{N}\setminus S$, $h\le h'$, 
$$|S\cap [h,h']| = \operatorname{nd}(h')-\operatorname{nd}(h)$$


<div class="absolute left-20% top-50%">

The given Hasse diagram

<img src="/469-gaps-n-divs.svg" alt="469-gap-ndivs"  width="75%">


</div>

<div class="absolute left-50% top-50%">

Our semigroup

<br><br><br>
$0$, <v-click> $\textcolor{red}{\sout{1}}$, $\textcolor{red}{\sout{2}}$, $\textcolor{red}{\sout{3}}$, </v-click>  <v-click> $4$, </v-click> <v-click> $\textcolor{red}{\sout{5}}$, </v-click>  <v-click> $6$, </v-click> <v-click> $\textcolor{red}{\sout{7}}$, </v-click> <v-click> $8$, $9$, $10$, </v-click> <v-click> $\textcolor{red}{\sout{10}}$, </v-click> <v-click> $11$, $\to$ </v-click> 

</div>

---

# Poset isomorphism (wrt inclusion)

**Result:** If $S$ and $T$ are numerical semigroups such that the poset $(\mathcal{I}_0(S),\subseteq)$ is isomorphic to $(\mathcal{I}_0(T),\subseteq)$,<br> then $S=T$


If $(\mathcal{I}_0(S),\subseteq)$ is isomorphic to $(\mathcal{I}_0(T),\subseteq)$, then $(\mathbb{N}\setminus S,\le_S)$ is isomorphic to $(\mathbb{N}\setminus T,\le_T)$

From $(\mathbb{N}\setminus S,\le_S)$ and $(\mathbb{N}\setminus T,\le_T)$, we recover $S$ and $T$; the "number of divisors" function is the same in both posets

Thus, $S=T$

---

# Monoid isomorphism problem

If $S$ and $T$ are numerical semigroups such that the monoid $(\mathcal{I}_0(S),+)$ is isomorphic to $(\mathcal{I}_0(T),+)$,<br> can we ensure that  $S=T$?

For $I,J\in \mathcal{I}_0(S)$, write $I\preceq J$ if there exists $K\in \mathcal{I}_0(S)$ such that $I+K=J$


Recall that $S$ is *irreducible* if it is not the intersection of two semigroups properly containing it


1. Oversemigroups of $S$ are precisely the ideals of $\mathcal{I}_0(S)$ such that $I+I=I$ (idempotent)

1. Unitary extensions of $S$ are minimal idempotents with respect to $\preceq$ (idempotent quarks)

1. The genus of $S$ is the maximum $k$ such that there exists a chain $I_0\prec I_1 \prec \dots \prec I_k$ in $\mathcal{I}_0(S)$

1. For $E\in \mathcal{I}_0(S)$, with $E+E=E$, the set $C_E=\{I\in \mathcal{I}_0(S) : I+E=I\}=\mathcal{I}_0(E)$ 

---

# Monoid isomorphism problem (solution)

If $S$ and $T$ are numerical semigroups such that the monoid $(\mathcal{I}_0(S),+)$ is isomorphic to $(\mathcal{I}_0(T),+)$,<br> then  $S=T$?

1. Apply induction on the genus: $S$ and $T$ have the same genus and the same unitary extensions

1. The intersection of all the unitary extensions of $S\neq \mathbb{N}$ equals $S$ or 
   
   $S\cup \{\operatorname{F}(S)\}$ (if $S$ is irreducible)


1. $S$ is irreducible if and only if $\mathcal{I}_0(S)$ has at most two quarks; if $S\neq \mathbb{N}$,
    
   - one quark means symmetric
    
   - two quarks translates pseudo-symmetry

1. In the irreducible case, we recover $\operatorname{F}(S)$ from the genus of $S$

---

# The other (unsolved) poset isomorphism

If $S$ and $T$ are numerical semigroups such that the poset $(\mathcal{I}_0(S),\preceq)$ is isomorphic to $(\mathcal{I}_0(T),\preceq)$,<br> can we ensure that  $S=T$?


<div class="absolute left-35% top-25%">

<figure>


<img src="/469-dotm.svg" alt="469-dotm" width="50%">


<figcaption>

<p style="font-size:0.75em">

Hasse diagram of $\mathcal{I}_0(\langle 4,6,9\rangle)$<br> 
nodes labelled with sets of minimal generators<br>
idempotents in gray

</p>

</figcaption>

</figure>

</div>

---

# The other (unsolved) poset isomorphism

If $S$ and $T$ are numerical semigroups such that the poset $(\mathcal{I}_0(S),\preceq)$ is isomorphic to $(\mathcal{I}_0(T),\preceq)$,<br> can we ensure that  $S=T$?


<div class="absolute left-35% top-25%">

<figure>


<img src="/37-dotm.svg" alt="ov-3-7" width="50%">


<figcaption>

<p style="font-size:0.75em">

Hasse diagram of $\mathcal{I}_0(\langle 3,7\rangle)$<br> 
Solved for multiplicity three  <span style="color:green"> &check;</span>
</p>

</figcaption>

</figure>

</div>


---

# Ongoing problems

Let $S$ be a numerical semigroup and denote by $\mathcal{O}(S)$ the set of oversemigroups of $S$, which is the set of idempotent elments of $\mathcal{I}_0(S)$


<div class="grid grid-cols-[60%_40%] gap-4">

<div>

- Study the poset $(\mathcal{O}(S),\preceq)$

    - Detect oversemigroups by Kunz coordinates <span style="color:green"> &check;</span>
    - When is $(\mathcal{O}(S),\preceq)$ a lattice? 
    - When is $(\mathcal{O}(S),\preceq)$ a distributive lattice? 

- Determine when $\preceq$ equals $\subseteq$ in $\mathcal{I}_0(S)$ 

- Determine when $(\mathcal{I}_0(S),\preceq)$ is a lattice 


All these properties hold when the multiplicity of $S$ is small

</div>

<div>

<figure>
    <img src="/31317.svg" alt="31317" width="75%">

<figcaption>

<p style="font-size:0.75em">

Hasse diagram of $(\mathcal{I}_0(\langle 3,13,17\rangle),\preceq)$; nodes <br> labelled with their Kunz coordinates

</p>

</figcaption>

</figure>


</div>


</div>

---

# Ongoing problems

Let $S$ be a numerical semigroup and denote by $\mathcal{O}(S)$ the set of oversemigroups of $S$, which is the set of idempotent elments of $\mathcal{I}_0(S)$


<div class="grid grid-cols-[60%_40%] gap-4">

<div>

- Study the poset $(\mathcal{O}(S),\preceq)$

    - Detect oversemigroups by Kunz coordinates  <span style="color:green"> &check;</span>
    - When is $(\mathcal{O}(S),\preceq)$ a lattice? (always) <span style="color:green"> &check;</span> 
    - When is $(\mathcal{O}(S),\preceq)$ a distributive lattice? 

- Determine when $\preceq$ equals $\subseteq$ in $\mathcal{I}_0(S)$ 

- Determine when $(\mathcal{I}_0(S),\preceq)$ is a lattice 


All these properties hold when the multiplicity of $S$ is small

</div>

<div>


<figure>
<img src="/ov-4-6-9.svg" alt="ov-4-6-9" width="65%">

<figcaption>

<p style="font-size:0.75em">

Hasse diagram of $(\mathcal{O}(\langle 4,6,9\rangle),\preceq)$; <br>irreducibles in gray

</p>

</figcaption>
</figure>


</div>


</div>

---


# Ongoing problems

Let $S$ be a numerical semigroup and denote by $\mathcal{O}(S)$ the set of oversemigroups of $S$, which is the set of idempotent elments of $\mathcal{I}_0(S)$


<div class="grid grid-cols-[60%_40%] gap-4">

<div>

- Study the poset $(\mathcal{O}(S),\preceq)$

    - Detect oversemigroups by Kunz coordinates  <span style="color:green"> &check;</span>
    - When is $(\mathcal{O}(S),\preceq)$ a lattice? (always) <span style="color:green"> &check;</span> 
    - When is $(\mathcal{O}(S),\preceq)$ a distributive lattice? <span style="color:green"> &check;</span> 

- Determine when $\preceq$ equals $\subseteq$ in $\mathcal{I}_0(S)$ 

- Determine when $(\mathcal{I}_0(S),\preceq)$ is a lattice 


All these properties hold when the multiplicity of $S$ is small

</div>

<div>


<figure>
<img src="/37-dotm.svg" alt="3-7" width="45%">

<figcaption>

<p style="font-size:0.75em">

Hasse diagram of $(\mathcal{I}_0(\langle 3,7\rangle),\preceq)$; <br>idempotents in gray

</p>

</figcaption>
</figure>


</div>


</div>

---

# Ongoing problems

Let $S$ be a numerical semigroup and denote by $\mathcal{O}(S)$ the set of oversemigroups of $S$, which is the set of idempotent elments of $\mathcal{I}_0(S)$


<div class="grid grid-cols-[60%_40%] gap-4">

<div>

- Study the poset $(\mathcal{O}(S),\preceq)$

    - Detect oversemigroups by Kunz coordinates  <span style="color:green"> &check;</span>
    - When is $(\mathcal{O}(S),\preceq)$ a lattice? (always) <span style="color:green"> &check;</span> 
    - When is $(\mathcal{O}(S),\preceq)$ a distributive lattice? <span style="color:green"> &check;</span> 

- Determine when $\preceq$ equals $\subseteq$ in $\mathcal{I}_0(S)$ <span style="color:green"> &check;</span> 

- Determine when $(\mathcal{I}_0(S),\preceq)$ is a lattice 


All these properties hold when the multiplicity of $S$ is small

</div>

<div>


<figure>
<img src="/35-dotm.svg" alt="3-5" width="45%">

<figcaption>

<p style="font-size:0.75em">

Hasse diagram of $(\mathcal{I}_0(\langle 3,5\rangle),\preceq)$; <br>idempotents in gray

</p>

</figcaption>
</figure>


</div>


</div>

---


# Ongoing problems

Let $S$ be a numerical semigroup and denote by $\mathcal{O}(S)$ the set of oversemigroups of $S$, which is the set of idempotent elments of $\mathcal{I}_0(S)$


<div class="grid grid-cols-[60%_40%] gap-4">

<div>

- Study the poset $(\mathcal{O}(S),\preceq)$

    - Detect oversemigroups by Kunz coordinates  <span style="color:green"> &check;</span>
    - When is $(\mathcal{O}(S),\preceq)$ a lattice? (always) <span style="color:green"> &check;</span> 
    - When is $(\mathcal{O}(S),\preceq)$ a distributive lattice? <span style="color:green"> &check;</span> 

- Determine when $\preceq$ equals $\subseteq$ in $\mathcal{I}_0(S)$ <span style="color:green"> &check;</span> 

- Determine when $(\mathcal{I}_0(S),\preceq)$ is a lattice <span style="color:orange"> &check;</span> 


All these properties hold when the multiplicity of $S$ is small

</div>

<div>


<figure>
<img src="/469-dotm.svg" alt="3-7" width="65%">

<figcaption>

<p style="font-size:0.75em">

Hasse diagram of $(\mathcal{I}_0(\langle 4,6,9\rangle),\preceq)$; <br>idempotents in gray

</p>

</figcaption>
</figure>


</div>

</div>

---


# References

- V. Barucci, F. Khouja, On the class semigroup of a numerical semigroup, Semigroup Forum, 92 (2016), 377-392

- S. Bonzio, P. A. García-Sánchez, Posets and lattices of normalized ideals of numerical semigroups, in progress

- L. Casabella, M. D'Anna, P. A. García-Sánchez Apéry sets and the ideal class monoid of a numerical semigroup, Mediterr. J. Math. 21:7 (2024)

- P. A. García-Sánchez, The isomorphism problem for ideal class monoids of numerical semigroups, Semigroup Forum 108 (2024), 365–376.

- M. Delgado,  P.A.  García-Sánchez,  and  J. Morais, NumericalSgps, A package for numerical semigroups, Version 1.3.1 (2022), (Refereed GAP package), https://gap-packages.github.io/numericalsgps



---
layout: cover
background: ""
---

# Thank you for your attention!

Find our more at [numerical-semigroups.github.io](http://numerical-semigroups.github.io/)

Slides produced with [slidev](https://es.sli.dev/)

<!--<SlideCurrentNo /> -->