en [m3-set-theory](m3-set-theory.md) definimos en basiquísimo concepto de set, y en el [capitulo anterior](m4-algebraic-spaces.md) vimos cómo agregarle the structure necesaria para realizar operaciones algebraicas con sus miembros. En esta entrega nos centraremos en las estructuras que nos permiten hablar formalmente del concepto de distancia entre sus miembros.

Empezaremos por definir el concepto de distancia más básico.

## topology

Given a *set* $X$, a **topology** is a set $\mathcal O$ of *subsets* of $X$ that *contains* $\emptyset$ and $X$, and is *closed-under* *unions* and *intersections*. Any *set* $O \in \mathcal O$ is called **open**, and any *subset* $C\subseteq X$ is called **closed** if its *complement* is *open*. A *set* that is both *open* and *closed*, is called **clopen** (e.g. $\emptyset$ and $M$). If we have two *topologies* $\mathcal O_1$ and $\mathcal O_2$ s.t. $\mathcal O_1 \subseteq \mathcal O_2$ we say that $\mathcal O_2$ is a **finer** *topology* than $\mathcal O_1$ and that $\mathcal O_1$ is **coarser** than $\mathcal O_2$, and if $\mathcal O_1$ is a *proper-subset* (i.e. $\mathcal O_1 \subseteq \mathcal O_2$) we add the word "strict", i.e., we say that $\mathcal O_2$ and $\mathcal O_1$ are, respectively, a **strict-finer** and a **strict-coarser** *topology* than the other. 

> Examples

> Note: Number of topologies given the cardinality of $X$.

> Note: $\subseteq$ defines a *partial-order* over the *topologies* of $X$. #todo ver si agrego y explico esto acá o más adelante.

## metric

## norm
