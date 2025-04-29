A **set-formal-system** is a *formal-system* that extends a *first-order-formal-system* with a particular collection of *axioms*. This collection of *axioms* (that are added to the *axioms-system* of the *first-order-formal-system*) are known as a **set-axiomatic-system**. Any *variable* in a *set-formal-system* is called a **set** and is a formalization of the natural concept of collection. The **set-membership-relation** $\in$ is a *binary-relation* which is completely defined by the choice of *set-axiomatic-system*. The *binary-relation* (in *infix-notation*) $x \in y$ is read "the *set* $y$ **contains** the *set* $x$", or "the *set* $x$ is an **element** of the *set* $y$" (formally defining the words *contains* and *element*).

> All the *elements* of a *set* $x$ (all the *sets* $y$ that satisfy $y \in x$) are generally listed between brackets. E.g. the *set* of vowels is $x:=\{a,e,i,o,u\}$.

> Although there are several, here we'll use the most widely used *set-axiomatic-system*, but before listing its *axioms* we'll define some [useful concepts](#useful-definitions) that will allow us to express the [axioms](#axioms) in a shorter way.

# useful-definitions

We say that a *set* $x$ is **empty** if it has no *elements*, i.e. $\forall y: \neg(y\in x)$, and that is **non-empty** if it has at least one *element*, i.e. $\exists y: y\in x$. If it has exactly one *element* ($\exists! y: y\in x$) is called a **singleton**, if it has exactly two *elements* is called a **pair**, and if has exactly three *elements* a **triplet**. An **ordered-pair** of *sets* denoted $(a,b)$ and constructed from the *set* $\{a,b\}$ is the *set* $\{\{a\}, \{a,b\}\}$ where we can differentiate the order of each *element*. A **triple** is an ordered *triple*, i.e. $(a, b, c):=\{\{a\},\{\{b\},\{b, c\}\}\}$ and a tuple a generalization of this concept of an ordered *set* of any number of *elements*. Often *ordered-pairs* and *triples* are called 2-*tuples*, and 3-*tuples* respectively. 

## binary-relations

A *binary* *predicate* $R(x,y)$ is historically known as a **binary-relation**, and also historically is represented as $xRy$ instead of $R(x,y)$ in what is known as the **infix-notation**. 
A **reflexive** *binary-relation* satisfy $\forall x:xRx$ (i.e. $\forall x:R(x,x)$), an **irreflexive** if $\forall x:\neg (xRx)$, a **symmetric** $\forall x,y:xRy \Leftrightarrow yRx$, an **asymmetric** $\forall x,y:xRy \Rightarrow \neg (yRx)$, an **antisymmetric** $\forall x,y: xRy \wedge yRx \Rightarrow x=y$, a **total** $\forall x,y: xRy \vee yRx$, a **transitive** $\forall x,y,z: xRy \wedge yRz \Rightarrow xRz$, and finally, an **antitransitive** $\forall x,y,z: xRy \wedge yRz \Rightarrow \neg(xRz)$. 
A *transitive* *binary-relation* is called a **preorder** (R) if it's *reflexive*, and a **strict-preorder** (I) if it's *irreflexive*. A *total* *preorder* is called a **total-preorder** (RT), and a *symmetric* *preorder* an **equivalence** (RS).  An *antisymmetric* *total-preorder* is a **total-order** (RTA), an *antisymmetric* *equivalence* is an **equality** (RSA), and an *antisymmetric* *preorder* is called a **partial-order** (RA). A *symmetric* *total* *preorder* (RTS), or equivalently, a total equivalence (RST) is known as a **universal-relation**.
Note that *total* implies *reflexive*, and since a *strict-preorder* is by definition *irreflexive* we need a word for a *binary-relation* that is "*total* but not *reflexive*" (i.e. the *total* condition $\forall x,y: xRy \vee yRx$ does not hold for $x=y$), and that word is **comparable**. So a **strict-total-order** (IC) is a *strict-preorder* that is *comparable*. If the *strict-preorder* is not *comparable*, but the *elements* that are not *comparable* are *equivalent*, then it's called a **strict-partial-order**.

> Note that a *total-order* is also a *total* *partial-order* (RAT), an *equality* is also a *symmetric* *partial-order* (RAS), and a *universal-relation* is also a *total* *equivalence*.

> A *transitive* *binary-relation* is *asymmetric* *iff* it's *irreflexive*. So in the definition of *strict-preorder* we could've used *asymmetric* instead.

> A *strict-total-order* is *vacuously* *antisymmetric* (the *comparable* and *transitive* properties make impossible to have $xRy \wedge yRx$) so is an *irreflexive* *total-order*. (In letters, an IC (*strict-total-order*) is necessarily an ICA. So to make a *total-order* (RTA) *irreflexive*, is to change the R for an I, and the T becomes a C (*total* but *irreflexive* is *comparable*) obtaining an ICA (*strict-total-order*)).

Some useful *binary-relations* (in *infix-notation*) are:
* $x \notin y:\Leftrightarrow \neg (x\in y)$ read as "the *set* $y$ does **not contain** the *set* $x$", or "the *set* $x$ is **not an element** of the *set* $y$"
* $x \subseteq y :\Leftrightarrow \forall z(z \in x \rightarrow z \in y)$ read as "the *set* $x$ is a **subset** of the *set* $y$"
* $x \subset y:\Leftrightarrow (x\subseteq y) \wedge \neg(y \subseteq x)$, or equivalently $\subset (x,y) :\Leftrightarrow (x\subseteq y) \wedge \neg(x=y)$ read as "the *set* $x$ is a **proper-subset** of the *set* $y$"
* $x=y :\Leftrightarrow (x \subseteq y) \wedge(y \subseteq x)$ read as "the *set* $x$ is a **equal** of the *set* $y$" (note that this is in fact an [equality-binary-relation](../published/math/m1-formal-language.md#binary-relations)).

## maps

A **map** is a *binary-relation* $\phi$ between the *elements* of two *sets* $A,B$ s.t. $\forall a \in A: \ \exists! b \in B: \phi(a, b)$. Since $b$ is unique we can write $b=\phi(a)$. The *elements* $a,b$ are known as **input** and **output** respectively, and the *sets* $A,B$ are known as the **domain** and **codomain** of $\phi$ respectively. Given a *subset* $V\subseteq B$, the *set* of all the *inputs* whose *output* is in $V$, i.e. $\{a \in A \mid \phi(a) \in V\}$ is called the **preimage of $V$ under $\phi$** and denoted $\text{preim}_\phi(V)$. Note that $\text{preim}_\phi(V) \subseteq A$. Given a *subset* $U\subseteq A$, the *set* of all the *outputs* we obtain by applying $\phi$ to $U$, i.e. $\{b\in B \mid \exists a\in U: \phi(a)=b\}$ is called the **image of $U$** **under** $\phi$ and denoted $\text{im}_\phi(U)$. If the *subset* is directly the whole *domain* is called just the **image of $\phi$** and denoted $\text{im}_\phi:=\text{im}_\phi(A) =\{b\in B \mid \exists a\in A: \phi(a)=b\}$. Note that the *image* of any *subset* $U\subseteq A$ is a *subset* of the *codomain* $B$. If the image of $\phi$ is the whole codomain $\text{im}_\phi(A)=B$, i.e. every $b\in B$ is an *output* of some $a\in A$, we say that the map $\phi$ is **surjective**. If there are no two different *outputs* with the same *input* (i.e. $\forall a_{1}, a_{2} \in A: \phi\left(a_{1}\right)=\phi\left(a_{2}\right) \Rightarrow a_{1}=a_{2}$) we say that the *map* $\phi$ is **injective**. Note that if $\phi$ is *surjective* and *injective*, then every *element* of the *codomain* is the *output* of a unique *element* of the *domain*, i.e. $\forall b \in B ,\exists! a \in A:b=\phi(a)$, in this case $\phi$ is a one-to-one mapping of the *domain* and the *codomain* and we say that $\phi$ is **bijective**. In some cases, instead of saying that the *map* $\phi$ is *injective*, *surjective* or *bijective*, we say that $\phi$ is an **injection**, a **surjection**, or a **bijection**. A *bijection* from a *set* $A$ to itself is a **permutation**. The more standard example of a *permutation* is the **identity-map**, that maps every *element* $a\in A$ to itself, i.e. $\text{id}_{A}:  A \rightarrow A \mid  \ a \mapsto a$. The *set* of all the *bijection*s from a *set* $A$ to itself (*permutations*) receives the name of the **symmetric-set** of $A$ and is denoted as $\Phi_A$. If there exists a *bijection* between to any pair of *sets* $A$ and $B$, we say that they are **isomorphic-sets**, denoted $A \cong_{\text{set}} B$. Given 2 *maps* $\phi:A \to B$ and $\psi: B \to C$, the *map* $\psi \circ \phi: A  \rightarrow C \mid a  \mapsto \psi(\phi(a))$ read as "$\psi$ after $\phi$" is known as the **composition** of $\phi$ and $\psi$. We saw that a *bijection* $\phi$ is a one-to-one mapping of the *domain* and the *codomain*, having each $b\in B$ a unique corresponding $a\in A$ s.t. $\phi(a)=b$. We could then have a *map* that returns for each $b\in B$ that unique $a\in A$, such *map* is known as the **inverse-map** of $\phi$, denoted $\phi^{-1}$ and is completely defined by $\phi^{-1} \circ \phi = \text{id}_A \  \wedge \ \phi \circ \phi^{-1} = \text{id}_B$ (where $\circ$ is *composition* and $\text{id}_X$ the *identity-map*). If a *map* has a *inverse-map*, we say that it is **invertible**. A *permutation* $\phi:A \to A$ that is its own *inverse-map* is known as an **involution**.

![](../assets/images/bijection.png)

**cartesian product**
**disjoint**
**union**

Given a *set* $X$, a **partition** $P(X)$ is a collection of *non-empty*, and pairwise *disjoint* *subsets* $A_i\subseteq X$
whose *union* is the whole *set*, i.e. $\bigcup_i A_i =X$.

# axioms

Axiom-of-extensionality (E): Two sets with the same elements are the same set.
Axiom-of-pairing (P): If $a$ and $b$ are sets, then $\{a,b\}$ is also a set.


[TOC of Theorem List - Metamath Proof Explorer](https://us.metamath.org/mpeuni/mmtheorems.html#dtl:2)

* Axiom-of-extensionality: 
	* A set is only defined by its elements. 2 sets with the same elements are the same set.
	* $\forall z(z \in x \leftrightarrow z \in y) \rightarrow x=y$
* Axiom-of-replacement:
	* The image of any set under any map is also a set.
	* $(\forall w \exists y \forall z(\forall y \varphi \rightarrow z=y) \rightarrow \exists y \forall z(z \in y \leftrightarrow \exists w(w \in x \wedge \forall y \varphi)))$
* Axiom-of-union:
	* Given a set $x$, the collection of the elements of its elements is a set.
	* $\exists y \forall z(\exists w(z \in w \wedge w \in x) \rightarrow z \in y)$
	* The set y formed by the elements (z) of the elements (y) of x, is called the union-set of x.
* Axiom-of-regularity:
	* every nonempty set contains a set disjoint from itself. One consequence is that it denies the existence of a set containing itself
	* $(\exists y y \in x \rightarrow \exists y(y \in x \wedge \forall z(z \in y \rightarrow \neg z \in x)))$
# equivalence-class

Given an *equivalence-relation* $\sim$ over a *set* $M$ and an *element* $m\in M$, the *set* $[m]_{\sim}:=\{n \in M \mid m \sim n\}$ is called the **equivalence-class** of $m$ and $m$ is known as the **representative** of the *equivalence-class*. In general $[m]_\sim$ is just denoted $[m]$. The *set* of all the *equivalence-classes* of $M$ (removing duplicates) is known as the **quotient-set** and denoted $M_\sim$. The *surjective* *map* $\pi:M \to M_\sim \mid m \mapsto [m]_\sim$ that sends each *element* $m\in M$ to its *equivalence-class* $[m]_\sim \in M_\sim$ is known as the **quotient-map**, and a **choice-of-representatives** is an *injective* *map* $c:M_\sim \to M$ that sends every *equivalence-class* to a *representative*. 

> Note that the *map-composition* $\pi \circ c$ is the *identity-map* over $M_\sim$. 

Properties:
* Any $n\in [m]$ can be a *representative*, i.e. $n \in[m] \Rightarrow[n]=[m]$.
* Different *equivalence-classes* are *disjoint*, i.e. $([m] \cap[n]=\varnothing) \vee ([m]=[n])$.
* Every *equivalence-relation* $\sim$ induces a *partition* of $M$ denoted (the *quotient-set*), and conversely, every *partition* of $M$ defines an *equivalence-relation* ($m\sim n$ if they are in the same *subset* of the *partition*).

# number-sets

**natural-numbers**
**integer-numbers**

> Well definition on a *quotient-set*: Care must be taken when defining *maps* whose *domain* is a quotient-set if one uses a *choice-of-representatives*. In order for it to be **well-defined** one needs to show that the *map* is the same under any *choice-of-representatives*.

**rational-numbers**