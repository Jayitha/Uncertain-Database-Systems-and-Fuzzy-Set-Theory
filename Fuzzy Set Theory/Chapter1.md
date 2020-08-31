---
marp: true
theme: gaia
class: invert
backgroundColor: black
---

## PART ONE: THEORY

### CHAPTER 1
#### FROM ORDINARY (CRISP) SETS TO FUZZY SETS: A GRAND PARADIGM SHIFT

---

## References

Primarily 

*George J. Klir and Bo Yuan. 1994. Fuzzy sets and fuzzy logic: theory and applications. Prentice-Hall, Inc., USA.*


---

#### Traditional View

Uncertainity is undesirable in science and should be avoided by all possible means

#### Alternate or Modern View

uncertainity is unavoidable and posseses some utility

---

### Crisp Set

The characteristic function($\chi_{A}$) of a crisp set($A$) maps all members of the universal set($X$) to $\{0, 1\}$

$$
\Chi_A: X \rightarrow \{0, 1\}
$$

$$
\Chi_A(x) = \begin{cases}
1 \; \forall x \in A\\
0 \; \forall x \not\in A\\
\end{cases}
$$

---

### Fundamental Properties of Crisp Set Operations

$$A, B, C \in P(X)$$

#### Involution
$$
\overline{\overline{A}} = A
$$

#### Commutaivity
$$
A \cap B = B \cap A\\
A \cup B = B \cup A
$$

---

#### Associativity
$$
A \cap (B \cap C) = (A \cap B) \cap C\\
A \cup (B \cup C) = (A \cup B) \cup C\\
$$

#### Distributivity
$$
A \cup (B \cap C) = (A \cup B) \cap (A \cup C)\\
A \cap (B \cup C) = (A \cap B) \cup (A \cap C)\\
$$

#### Idempotence

$$
A \cup A = A\\
A \cap A = A
$$

---

#### Absorption by $X$ and $\phi$

$$
A \cup X = X\\
A \cap \phi = \phi
$$

#### Identity

$$
A \cup \phi = A\\
A \cap X = A 
$$

#### Law of Contradiction

$$
A \cap \overline{A} = \phi
$$

---

#### Law of Excluded Middle

$$
A \cup \overline{A} = X
$$

#### De Morgan's Laws

$$
\overline{A \cap B} = \overline{A} \cup \overline{B}\\
\overline{A \cup B} = \overline{A} \cap \overline{B}
$$

---

### Boolean Lattice

- Elements of $P(X)$ can be partially ordered using set inclusion $\subseteq$

- This lattice is distributive and complemented

---

### Partitions

A family of pairwise disjoin subsets of $A$ is called a parition on A if the union of these subsets yeilds the original set A.

$$
\pi(A) = \{A_i | i \in I, A_i \subseteq A\}\\
$$
$$
\forall i A_i \neq \phi\\
$$
$$
\forall i, j A_i \cap A_j = \phi\\
$$
$$
\bigcup_{i \in I} A_i = A
$$

---

All $A_i$ are called blocks of the partition.

$\pi_1(A)$ is a _refinement_ of $\pi_2(A)$ iff

$$
\forall A_i \in \pi_1(A) \; \exists A_j \in \pi_2(A) \; \; A_i \subseteq A_j
$$

This refinement relation ($\leq$) forms a partial ordering over the set of all partitions of $A$ ($\prod(A)$)

The pair ($\langle \prod(A), \leq \rangle$) is called the **partition lattice of $A$**

---

### Nested Family

Let $\mathcal{A} = \{A_1, ..., A_n\}$ be a family such that $A_i \subseteq A_j \forall i = 1, 2, ..., n-1$

- $\mathcal{A}$ is called a nested family
- $A_1$ is called the innermost set
- $A_n$ is called the outermost set

---

### Supremum and Infimum

Let $R \subseteq \mathcal{R}$

- If $\exists r \; \forall x \in R \; x \leq r \rightarrow upper\_bound(R) = r$
- If $\exists s \; \forall x \in R \; x \geq s \rightarrow lower\_bound(R) = s$
- Upper bound $r$ is the supremum iff no other upperbound is less than $r = sup R$ 
- Lower bound $s$ is the infimum iff no other lowerbound is greater than $s = inf R$

---

## Fuzzy Sets: Basic Types

The charracteristic function can be generalized such that values assigned can fall within a specified range(usually $[0, 1]$) indicating membership grades of the elements in the set in question.

The membership function of a fuzzy set $A$ can be denoted by $A$ itself or $\mu_A$. We use the former.

$$
A: X \rightarrow [0, 1]
$$

$X$ is always a crisp set

---

- Fuzzy sets allow us to describe vague concepts expressed in natural language. Although these are often dependent on concepts.


- Even for similar concepts, fuzzy sets may vary considerably while being similar in a few key features.

- Fuzzy sets usually represent linguistic concepts such as low, medium and high and are used to define states of variables called _fuzzy variables_

- [Paradox] Data based on fuzzy variables provide us with more accurate evidence about real world phenomena than data based on crisp variables

--- 

### Ordinary Fuzzy Sets

Given universal set $X$, an ordinary fuzzy set $A$ is defined by a membership funtion of the form

$$
A: X \rightarrow [0, 1]
$$

- also called type 1 and level 1 sets

---

## Interval-valued Fuzzy Sets

If suppose you cannot pick between a definite real value to express the membership grade of an element, and you're only able to identify lower and upper bounds of the membership grade, we have two options

- Discard the uncertainity, pick the middle maybe to be the grade

- **Accept the uncertainity and include it in the definition of the membership function**

---

$$
A: X \rightarrow \xi([0, 1])
$$
where

where $\xi([0, 1])$ denotes the family of all closed intervals of real numbers in $[0, 1]$
$$
\xi([0, 1]) \subset P([0,1])
$$

- They allow you to express uncertainity in choosing the membership function
- Computationally more demanding

---

## Fuzzy sets of Type 2

Upon further generelization, intervals can also be fuzzy sets (ordinary)

$$
A: X \rightarrow \mathcal{F}([0, 1])
$$

Where

$\mathcal{F}([0, 1]) =$ set of all ordinary fuzzy sets that can be defined within $[0,1$ - _fuzzy power set of $[0, 1]$_

- Have still greater expressive power, but are still more computationally demanding

---

## Fyzzy Set of Type 3

When the membership grades assigned by type 2 fuzzy sets, are type 2 fuzzy sets themselves.

And so on...

---

## L-Fuzzy Sets

Whem membership grades are represented by symbols of arbitriary set $L$ that is at least partially ordered 

$$
A: X \rightarrow L
$$

Usually L is a lattice and L-fuzzy sets capture all other fuzzy sets so far

---

## Level 2 Fuzzy Sets

Fuzzy set defined within a universal set whose elements are ordinary fuzzy sets

$$
A: \mathcal{F}(X) \rightarrow [0, 1]
$$

- used when elements of $X$ cannot be specified precisely

---

## Level 3 Fuzzy Sets

- Universal set consists of Level 2 Fuzzy Sets

and so on ...

## Combinations

Type 2 + Level 2

$$
A: \mathcal{F}(X) \rightarrow \mathcal{F}([0, 1])
$$

and many more ...

---

## FUZZY SETS: BASIC CONCEPTS

---

## $\alpha$-Cuts and Strong $\alpha$-Cuts

Given fuzzy set $A$ defined on $X$ and any number $\alpha \in [0,1]$

$$
\alpha\text{-Cut} = {}^{\alpha}A = \{x|A(x) \geq \alpha\}
$$

$$
\text{strong } \alpha\text{-Cut} = {}^{\alpha+}A = \{x|A(x) > \alpha\}
$$

---

## Level Set of A

The set of all $\alpha \in [0,1]$ that represent distinct $\alpha$-cuts of a $A$

$$
\Lambda(A) = [\alpha|\exists x \; A(x) = \alpha]
$$

---

_Total Ordering of $\alpha$s is inversely preserved by the set inclusion of the corresponding $\alpha$-cuts and strong $\alpha$-cuts_

$$
\forall \alpha_1, \alpha_2 \in [0,1], \; \; \alpha_1 > \alpha_2
$$
$$
{}^{\alpha_1}A \subseteq {}^{\alpha_2}A 
$$
$$
{}^{\alpha_1+}A \subseteq {}^{\alpha_2+}A
$$

- both cuts form families of nested crisp sets

---

Support - $S(A)$ or $supp(A) = {}^{0+}A$

Core - $core(A) = {}^{1}A$

Height - $h(A) = \sup_{x \in X} A(x)$

Normal - If $h(A) = 1$, $A$ is normal

Subnormal - If $h(A) < 1$

---

## Convexity

_$\alpha$-cuts of a convex fuzzy set must be convex for all $\alpha \in (0, 1]$ in the classical sense_

note: ${}^{0}A$ is convex since it is $R^n$

---

Doubt: Membership functions of convex fuzzy sets are not convex, but concave according to standard definitions

---

## Theorm 1.1 

A fuzzy set $A$ on $\mathcal{R}$ is convex iff 

$$
\forall x_1, x_2 \in \mathcal{R} \; \forall \lambda \in [0,1]
$$
$$
A(\lambda x_1 + (1 - \lambda)x_2) \geq min[A(x_1), A(x_2)]
$$ 

---

## Cutworthy and Strong Cutworthy Property 

Any property generelized from classical set theory into the domain of fuzzy set theory that is preserved in all $\alpha$-cuts for $\alpha \in (0, 1]$ in the classical sense is called a _cutworthy property_

If it is preserved in all strong $\alpha$-cuts for $\alpha \in [0, 1]$ then it is called _strong cutworthy property)_

Convexity is both cutworthy and strong cutworthy

---

## Standard Fuzzy Set Operations

#### Standard Complement

$$
\forall x \in X \; \; \overline{A}(x) =  1 - A(x)
$$

- Equilibrium points - $x$ where $\overline{A}(x) = A(x)$

#### Standard Intersection and Union

$$
(A \cap B)(x) = min[A(x), B(x)]
$$
$$
(A \cup B)(x) = max[A(x), B(x)]
$$

---

## Set Inclusion

Given $A, B \in \mathcal{F}(X)$ 
$$
A \subseteq B \Leftrightarrow \forall x \in X \; \; A(x) \leq B(x)
$$

---

## De Morgan Lattice

- A Fuzzy powerset can be viewed as a lattice with standard fuzzy intersection and union playing the roles of meet and join respectively. 

- The lattice is distributed and complemented under the standard operations. 

- It satisfies all Boolean lattice properties except the law of contradiction and the law of excluded middle

- $\langle \mathcal{F}(X), \subseteq \rangle$ 

---

#### Scalar Cardinality (or Sigma Count)

$$
|A| = \sum_{x \in X} A(x)
$$

#### Degree of Subsethood

$$
S(A, B) = \frac{1}{|A|}\left (|A| - \sum_{x \in X}max[0, A(x) - B(x)] \right ) = \frac{|A \cap B|}{|A|}
$$

---

## Alternate Representation

* only with finite support

$$
A = a_1/x_1 + a_2/x_2 + ... + a_n/x_n
$$

Where $x_i \in {}^{0+}A$ and $a_i = A(x_i)$

When $X$ is countable $A = \sum_{i=1}^n a_i/x_i$ or $A = \sum_{i=1}^\infty a_i/x_i$

else when $X$ is an interval of real numbers $A = \int_x A(x)/x$

---

Interpret fuzzy set of $X$ with $n$ elements as an $n$-dimensional unit cube

- Whole cube represents $\mathcal{F}(X)$
- Vertices represent $\mathcal{P}(X)$

Distance between Fuzzy Sets $A$ and $B$ could be

$$
d(A, B) = \sum_{x \in X} |A(x) - B(x)|
$$

Probability distributions are fuzzy sets whose cardinality is 1 |
---| 

---

