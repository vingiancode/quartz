We saw in the [previous entry](m1-formal-language), that a collection of *formation-rules* (the *formal-grammar*) indicate which *formulas* are *well-formed* and form a *formal-language*. Now we will go a step further by marking some of the *wffs* of a given *formal-language* $\mathcal L$ as **theorems**. This is done again by a collection of rules, known as **inference-rules**. The collection of *inference-rules* that we decide to use is known as an **inference-system**. Unlike a *formal-grammar*, an *inference-system* requires a starting point. This is, it marks *wffs* as *theorems* using previous *theorems* (action that is known as "to **infer** a theorem"). To avoid this recursion, a collection of *wffs* (known as **axiomatic-system**) is chosen to be arbitrarily marked as *theorems* in order to start the process. Each of the *wffs* of the *axiomatic-system* is called an **axiom**. All *wffs* that can be marked as *theorems* depend on the *formal-language* ($\mathcal L$), the *inference-system* ($\mathcal I$), and the *axiomatic-system* ($\mathcal S$). The *formal-language* ($\mathcal L$) defines all the *wffs* that can be marked as *theorems*, the *inference-system* ($\mathcal I$) specifies the rules for marking them, and the *axiomatic-system* ($\mathcal S$) provides the initial *theorems* to begin the process. This triplet is then very important as a whole and that is why it receives a name, i.e. a **formal-system** ($\mathcal F=(\mathcal L, \mathcal I, \mathcal S)$). Once we choose a *formal-system* $(\mathcal F)$, the collection of *wffs* of $\mathcal L$ that will be *theorems* is automatically defined. This collection is known as the **theory**.

![](../assets/images/formal-system.png)
In the [previous entry](m1-formal-language), we saw that the *formal-language* $\mathcal L$ is formed by all the *formulas* that can be created as combinations of *symbols* of the *formal-alphabet* $\mathcal A$, and are marked as *well-formed-formulas* (*wffs*) by the *formation-rules* of the *formal-grammar*. In the image above, the *formal-language* $\mathcal L$ (defined by $(\mathcal A, \mathcal G)$) is formed by all the *formulas* (in purple) that are inside the green area, i.e. all the *formulas* that are marked as *well-formed* using the *formal-grammar* $\mathcal G$ (all the *wffs*) are the 10 *formulas* $aaa, aab, aac, abb, abc, acc, bbb, bbc, bcc, ccc$ (check the example in [m1-formal-language](m1-formal-language)). Then we if we choose an *axiomatic-system* $\mathcal S$ (i.e. we chose some of these *wffs* (e.g. $abb$ and $ccc$) to be marked as *theorems*), and an *inference-system* $\mathcal I$, we have defined the *formal-system* $\mathcal F=(\mathcal L, \mathcal I, \mathcal S)$. All the *wffs* that can also be marked as *theorems* using this *formal-system* $\mathcal F$ (i.e. all the *wffs* that can also be marked as *theorems* by the *inference-rules* of $\mathcal I$ starting from the *axioms* $abb$ and $ccc$ of $\mathcal S$) form the *theory* $\mathcal T$. In the image above, we suppose that all the *wffs* that can be marked as *theorems* starting from $\mathcal S=\{abb,ccc\}$ and using $\mathcal I$ are $bcc$ and $aac$, so the *theory* $\mathcal T$ defined by the *formal-system* $\mathcal F=(\mathcal L, \mathcal I, \mathcal S)$ is formed by the four *theorems* $\{abb, ccc, bcc, aac\}$ (the blue area of the image).

> Notation note: It is common when talking about *formal-systems* to refer to the action of marking a *wff* as a *theorem* $t$ following $\mathcal I$ and $\mathcal A$, as to **prove** the *theorem* $t$. So we often hear of a *theory* as "the collection of all the *wffs* that can be *proven* from the *formal-system* $\mathcal F$". 

# zeroth-order-formal-system

Any *formal-system* $\mathcal F=(\mathcal L, \mathcal I, \mathcal S)$ that uses as its *formal-language* $\mathcal L$ the *propositional-formal-language* is called a **zeroth-order-formal-system**. As we saw, in a *formal-language* a *wff* is a *proposition*. In a *zeroth-order-formal-system* a *theorem* will be a *True* *proposition*, and to *prove* a *theorem* will be to *infer* that it is *True*.

## inference-rules

A *zeroth-order-formal-system* deals with *propositions*, and their *truth-values*, then the things to be inferred will be *truth-values* of *propositions*. For example, suppose we are told that the *proposition* $p AND q$ is a *theorem* (i.e. a *True* *proposition*). If we look at the [definition](m1-formal-language#logical-connectives), the only combination of truth-values of $p$ and $q$ for which it is True is both $p=T$ and $q=T$, so, if we are told that $p AND q$ is *theorem*, then we know that both $p$ and $q$ are theorems too (*True* propositions). This is an **inference**. We are told that $p AND q$ is a theorem (i.e. that is True), and nothing about the truth-values of the propositions $p$ and $q$, but this information is implicit in the *logical-connective* definition itself. This is, this information is not directly given to us, we are just told that $pANDq$ is a theorem, but we can "*infer*" that they are theorems too since the only combination of truth-values of $p$ and $q$ for which $pANDq$ is True is when both $p$ and $q$ are True. 
![[truth-values-and.png]]
If we are told that a given collection of propositions $\mathcal P$ (known as **premises**) are theorems, and if for all cases for which these propositions are True, some proposition $p$ (called the **conclusion**) is also True, we say that we can infer from $\mathcal P$ (being theorems) that $p$ is also True. This is nothing more than what we have called an inference-rule and is symbolically represented as $\mathcal P \models p$. For the case of $pANDq$ this rule is called **simplification** and is represented as $pANDq \models p$. Note that we can also use simplification to infer $q$, i.e., $pANDq \models q$. Conversely, (and as an example of an inference-rule of more than one premise) we can be told that the two propositions $p$ and $q$ are premises (therefore theorems, therefore both True) and from that infer that $pANDq$ is True (note that again the for the only row where both $p=T$ and $q=T$, we have $pANDq=T$). This inference-rule represented as $p,q\models pANDq$ is called **conjunction**.

Note, however, that not from every theorem (or collection of them) we can infer something. For example, $pORq\models p$ is not an inference-rule, since if we are told that $pORq$ is a theorem, we have three possible combinations of values of $p$ and $q$ that makes it True, and in two $p$ is True, but in the other $p$ is False. If from a rule $\mathcal P \models p$ we can actually infer the *conclusion* $p$, we say that the rule **valid**, if not (as in the case of $pORq\models p$) we called it a **fallacy**. 
![[valid-inference-rule.png]]
However, if we add the the premise $\neg q$, the only combination where both are True is $q=F$ and $p=T$ so we then can actually infer $p$ as a theorem. Then $pORq\models p$ is a fallacy, but $p OR q,\neg p \models q$ is an inference-rule, called **disjunctive-syllogism**. Note that we can also use the *disjunctive-syllogism* to infer $p$ by adding $\neg q$ as a premise (i.e. $p OR q,\neg q \models p$).

Other very commonly used inference-rule in a *zeroth-order-formal-system* is $p\to q, p \models q$, known as **modus-ponens**. We can again, looking at the definitions, that for all cases for which the premises are True (just one in this case), $q$ is True. 
![[modus-ponens 1.png]]
Suppose we are given $p\to q$ and $\neg q$ as premises. Using the *contrapositive-law* $p \rightarrow q \iff (\neg q) \rightarrow (\neg p)$ (that we introduce in the [previous-entry](m1-formal-language#equivalent-propositions)) we have that $\neg q \to \neg p$ is a theorem. And from it and $\neg q$ we can infer $\neg p$ using modus-ponens ($\neg q \to \neg p, \neg q \models \neg p$). This inference-rule, represented as $p\to q, \neg q \models \neg p$, is called **modus-tollens** and is a variance of the modus-ponens using the contrapositive-law.

> Note: Since if we are given two premises $p$,$q$ we can infer (using *conjunction*) that $pANDq$ is a theorem, and conversely, if we are given $pANDq$ as a single premise we can infer (via simplification) $p,q$ as two different premises. For this reason, in the collection of premises, $p,q$ or $pANDq$ are used interchangeably to state that both $p$ and $q$ are premises. For example, in some texts you can find the *disjunctive-syllogism* rule written as $(p OR q)AND(\neg p) \models q$, the *modus-ponens* rule written as $(p\to q)AND p \models q$, the *modus-tollens* rule as $(p\to q)AND \neg q \models \neg p$, etc.

As a final example, and as an example of an inference-rule with three different atomic-propositions we'll present the case of the inference-rule $p\to q, q\to r\models p\to r$ known as **hypothetical-syllogism**. Again, if you look in the next table, you'll see that for all cases for which both $p\to q$ and $q\to r$ are True, the proposition $p\to r$ is also True. Therefore, from the propositions $p\to q$ and $q\to r$ we can actually infer $p\to r$, making the *hypothetical-syllogism* a *valid* inference-rule.

![[hypothetical-syllogism.png]]
### fallacies

As we saw, a rule from which we cannot actually infer the conclusion is called a fallacy. F.e., we saw that, unlike the *disjunctive-syllogism* $p OR q,\neg p \models q$ that is a *valid* *inference-rule*, the rule $p OR q \models q$ is a fallacy since there are cases of which $pORq$ is True that $q$ is False. Many fallacies receive a name, f.e. $p OR q \models q$ is called the **affirming-a-disjunct-fallacy**. Unlike the *modus-ponens* ($p\to q,p \models q$), the rule $p\to q,q \models p$ is a *fallacy* (called the **affirming-the-consequent-fallacy**), since (as you can check in the following table) when $p\to q$ and $q$ are both True, $p$ could be False. 

![[fallacy.png]]

Other common *fallacy* is $p\to q, \neg p \models \neg q$, known as the **denying-the-antecedent-fallacy**. Note that $p \to q$ is *True* when $\neg p$ is *True* (i.e., $p$ is *False*) for both values of $q$ (and therefore both values of $\neg q$).
## examples

vimos que a *zeroth-order-formal-system* a *formal-system* $\mathcal F=(\mathcal L, \mathcal I, \mathcal S)$ that uses as its *formal-language* $\mathcal L$ the *propositional-formal-language*. Así que los distintos tipos que podemos tener quedan definidos por las combinaciones de $\mathcal I$, y $\mathcal S$. Ahora que vimos algunas common infenrence-rules of a a *zeroth-order-formal-system*, podemos listar algunos ejemplos de este tipo de formal-system. 

**simple-axiom-system** (or $P_2$) tiene como inference-system a formado solo por la inference-rule modus-ponens, y como axiomatic-system al formado por 3 axiomas, conocidos como Łukasiewicz-axioms y son: 
- $p \rightarrow(q \rightarrow p)$
- $(p \rightarrow(q \rightarrow r)) \rightarrow((p \rightarrow q) \rightarrow(p \rightarrow r))$
- $(\neg p \rightarrow \neg q) \rightarrow(q \rightarrow p)$
Font: https://en.wikipedia.org/wiki/Propositional_calculus#%C5%81ukasiewicz's_P2

meredith-axiom-system usa también solo modus-ponens, y baja la cantidad de axiomas increíblemente a uno: el axioma meredith 
Font: https://us.metamath.org/mpeuni/meredith.html

Hay también un conocido como natural-deduction-system that consists of no axioms, but uses an inference-system of 11 inference-rules 
https://en.wikipedia.org/wiki/Propositional_calculus#Inference_rules

## examples

We saw that a **zeroth-order formal system** is a **formal system** *$\mathcal F = (\mathcal L, \mathcal I, \mathcal S)$* that uses the **propositional formal language** as its **formal language** *$\mathcal L$*. Thus, the different types of **zeroth-order formal systems** are defined by the combinations of the **inference system** (*$\mathcal I$*) and the **axiomatic system** (*$\mathcal S$*). Now that we’ve explored some common **inference rules** of a **zeroth-order formal system**, let’s examine a few concrete examples to illustrate how these systems are constructed and applied.

## Simple Axiom System (P₂)
The **simple axiom system**, also known as P₂, is a classic **zeroth-order formal system** that relies on a minimal yet powerful structure. Its **inference system** consists solely of the **modus ponens** rule (*$p \to q, p \models q$*), which allows us to infer a conclusion *$q$* when a conditional *$p \to q$* and its antecedent *$p$* are both theorems. The **axiomatic system** comprises three axioms, known as the Łukasiewicz axioms, which serve as the starting points for proofs:
- *$p \to (q \to p)$* (If *$p$* is true, then *$q \to p$* is true, reflecting a basic implication property).
- *$(p \to (q \to r)) \to ((p \to q) \to (p \to r))$* (A complex nesting of implications that ensures transitivity in certain contexts).
- *$(\neg p \to \neg q) \to (q \to p)$* (The contrapositive relationship between negations and implications, linking to the **contrapositive law** from [m1-formal-language](#equivalent-propositions)).

These axioms, combined with **modus ponens**, allow the system to derive a wide range of propositional tautologies, making P₂ a foundational model in logic.  
*Source:* https://en.wikipedia.org/wiki/Propositional_calculus#%C5%81ukasiewicz's_P2

## Meredith Axiom System
The **Meredith axiom system** takes the concept of minimalism in **axiomatic systems** to an impressive extreme. Like P₂, it uses **modus ponens** as its sole **inference rule**, but it reduces the number of axioms to a single statement, known as the Meredith axiom. This axiom is:
- *(((p → q) → (r → s)) → t) → (((t → p) → r) → (s → p))*

At first glance, this single axiom might seem daunting due to its nested implications, but its brilliance lies in its ability to generate all tautologies of propositional logic when paired with **modus ponens**. Discovered by E.J. Meredith in 1953, this axiom demonstrates that a single, carefully crafted statement can encode the entire expressive power of propositional logic, provided we have a mechanism like **modus ponens** to expand it. The Meredith axiom works by embedding the logical relationships of implication, negation, and conjunction within its structure. For example, by repeatedly applying **modus ponens** and substituting specific propositions, one can derive basic tautologies such as *$p \to p$* or more complex ones like *$(p \to q) \to ((q \to r) \to (p \to r))$* (hypothetical syllogism). This reduction to a single axiom is a landmark in logic, showcasing how economy in axioms does not sacrifice completeness, as long as the **inference system** is sufficiently robust.  
*Source:* https://us.metamath.org/mpeuni/meredith.html

## Natural Deduction System
Another notable **zeroth-order formal system** is the **natural deduction system**, which takes a different approach by eliminating axioms entirely. Instead, it relies on a rich **inference system** consisting of 11 **inference rules**, designed to mimic the natural reasoning processes of mathematicians. These rules include familiar ones like **modus ponens**, **disjunctive syllogism**, and **conjunction**, as well as introduction and elimination rules for connectives (e.g., introducing *$\land$* with *$p, q \models p \land q$* or eliminating *$\to$* with **modus ponens**). By starting without axioms and building proofs step-by-step using these rules, the system provides a flexible framework for constructing proofs that feel intuitive. This approach contrasts with axiomatic systems like P₂ or Meredith, emphasizing process over initial assumptions.  
*Source:* https://en.wikipedia.org/wiki/Propositional_calculus#Inference_rules
# first-order-formal-system

Any *formal-system* $\mathcal F=(\mathcal L, \mathcal I, \mathcal S)$ that uses as its *formal-language* $\mathcal L$ the *predicative-formal-language* is called a **first-order-formal-system**.

## inference-rules

**universal-instantation**
# properties-of-formal-systems

A *formal-system* is **consistent** if it cannot derive both a *wff* $\phi$ and its *negation* $\neg \phi$ as *theorems*. In other words, a *consistent* *formal-system* does not contain contradictions.

> Example: If a *formal-system* for arithmetic derives both "2 + 2 = 4" and "2 + 2 $\neq$ 4" as *theorems*, it is inconsistent, which would undermine its usefulness.

A *formal-system* is **complete** if every *wff* in its *formal-language* is either a *theorem* or its *negation* is a *theorem*. That is, a *complete* *formal-system* can prove or disprove every statement expressible in its *formal-language*.

> Example: A simple *formal-system* for propositional logic with a single *proposition* $p$ might be *complete* if it can prove either $p$ or $\neg p$. However, as we’ll see in a later entry, many interesting *formal-systems*, such as those for arithmetic, are not *complete* (a result known as Gödel’s Incompleteness Theorem).

A *formal-system* is **decidable** if there exists an algorithm that can determine, for any *wff* in its *formal-language*, whether it is a *theorem*. In other words, a *decidable* *formal-system* has a mechanical procedure to check the provability of any statement.

> Example: Some simple *formal-systems*, like certain propositional logics, are *decidable* because we can systematically check all possible proofs. However, many *formal-systems* involving *predicates* and *quantifiers* (like our *predicative-formal-language*) are not *decidable*, as we’ll explore later.

These properties—*consistency*, *completeness*, and *decidability*—are fundamental to understanding the power and limitations of *formal-systems*, and they will play a crucial role in our study of mathematics.
