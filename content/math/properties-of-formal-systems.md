A *formal-system* is **consistent** if it cannot derive both a *wff* $\phi$ and its *negation* $\neg \phi$ as *theorems*. In other words, a *consistent* *formal-system* does not contain contradictions.

> Example: If a *formal-system* for arithmetic derives both "2 + 2 = 4" and "2 + 2 $\neq$ 4" as *theorems*, it is inconsistent, which would undermine its usefulness.

A *formal-system* is **complete** if every *wff* in its *formal-language* is either a *theorem* or its *negation* is a *theorem*. That is, a *complete* *formal-system* can prove or disprove every statement expressible in its *formal-language*.

> Example: A simple *formal-system* for propositional logic with a single *proposition* $p$ might be *complete* if it can prove either $p$ or $\neg p$. However, as we’ll see in a later entry, many interesting *formal-systems*, such as those for arithmetic, are not *complete* (a result known as Gödel’s Incompleteness Theorem).

A *formal-system* is **decidable** if there exists an algorithm that can determine, for any *wff* in its *formal-language*, whether it is a *theorem*. In other words, a *decidable* *formal-system* has a mechanical procedure to check the provability of any statement.

> Example: Some simple *formal-systems*, like certain propositional logics, are *decidable* because we can systematically check all possible proofs. However, many *formal-systems* involving *predicates* and *quantifiers* (like our *predicative-formal-language*) are not *decidable*, as we’ll explore later.

These properties—*consistency*, *completeness*, and *decidability*—are fundamental to understanding the power and limitations of *formal-systems*, and they will play a crucial role in our study of mathematics.
