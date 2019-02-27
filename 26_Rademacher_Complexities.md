---
title: "Chapter 26: Rademacher Complexities"
---

In chapter 4 it has been shown that the property of uniform convergence implies learnability and that the ERM-rule is $/epsilon$-consistent.
In this chapter Rademacher Complexity is introduced which measures the rate of uniform convergence.

## Notation:

At first some notation is defined

F := l o H := {

given f in F

L_D
L_S

F o S

## Definitions:

**Representativeness of S with respect to F**

Rep_D(F,S) :=

The representativeness of S measures the biggest difference between the losses measured in the sample S and over the whole set.

In general it is not possible to calculate the loss of an hypothesis over the whole domain and the representativeness is estimated by splitting up the sample S in some training and validation set.

FOTO

The **Rademacher Complexity** does exactly this, by splitting up S in all possible combination of training and validation set.

R(F o S) := 1/m

where $\sigma$ i.i.d. with P[] = 1/2

## Lemmas and Theorems:

The first Lemma that is shown bounds the expected value of representativeness of S by twice the expected Rademacher Complexity.

LEMMA

Theorem 26.3 give some easy bounds on the expected estimation error of the loss by applying the Lemma.

THEOREM

In general, we want a better dependence on the confidence parameter \delta.
This is achieved by applying the McDiarmid's Inequality. Theorem 26.5 gives three different bound that mainly says that if the Rademacher Complexity R(l o H o S) is small the ERM-rule can be used.
Also the second and third bound depend on the chosen training sample S, which is called a data-dependent bound and in comparison to other bounds, the third bound can be calculated!

THEOREM

## Rademacher Calculus:

Four Properties where proven for the Rademacher Calculus which can be applied to bound the Rademacher Complexity R(l o H o S) for specific cases.

A in R^m
1. Affine transformation: c in R, a_o in R^m
2. The Rademacher Complexity if the complex hull of A is equal to the Rademacher Complexity of R
3. Massart: The Rademacher Complexity of a finite set grows logarithmically with its size.
4. Contraction Lemma:

## Rademacher Complexity of Linear Classes:

The following two linear and bounded hypothesis classes will be analyzed:
H_1
H_2

The hypothesis class H_2 can be bounded by the maximum l2-norm of a sample from Hilbert space S devided by the square root of m, the size of S. Notice that the dimension of the Hilbert space S does not influence the Rademacher complexity, which is usefull when analyzing kernel methods.

A similar bound can be proven for H_1, but the dimension of S does appear in the numerator of the bound.

The two Lemmata imply two generalization bounds.


# A Formal Learning Model and Learning via Uniform Convergence

### Questions:

**Q:** On the page 376 the very first line $\sigma$ is introduced. Should the distribution of 
-1 and +1 be equal?

**A:** Yes, since we further assume that the sizes of two disjoint sets are equal. 

___

**Q:** Page 378. Formula on the top of the page. Would it suffice if $h^*$ **(???)** is Lipschitz continuous?

**A:** Yes, but we have to bound something. (for Lipschitz - domain). 

___

**Observation:** Theorem 26.5 - 3. is a remarkable result: if we learn our S, 
we have learnt the overall distribution pretty much.


___

**Q:** Lemma 26.8 - why do they use maximum of differences between estimated and actual $a$?

**A:** They use the geometric idea of difference between mean and center, where center is an actual $a$.


___

**Q:** Lemma 26.10 - why does not hold for $\mathcal{H}_1$?

**A:** The $\mathcal{v}$ can be bounded by whatever.


___

**Q:** Can we use $\mathcal{l}_1$-norm for kernel methods?

**A:** **No** there is dimension under the square root. 


___

**Q:** Theorem 26.13 bounds probability of misclassification. 
Why do they use $\mathcal{R}$-value in statement and not in the proof?

**A:** Value $\mathcal{c}$ which was used previously (for example in Theorem 26.12) 
in front of the square root is bounded by this $\mathcal{R}$-value.