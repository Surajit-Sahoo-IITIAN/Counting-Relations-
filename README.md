# Counting Relations — Interactive Explorer

An interactive visualization for understanding the **counting of relations on a finite set** using both **matrix representation** and **roster form**.

The visualization is designed to show *why* the standard counting formulas for relations arise, rather than asking students to simply memorize them.

---

## 🎯 Purpose

For a finite set

\[
A = \{a_1,a_2,\ldots,a_n\},
\]

a relation on \(A\) is a subset of

\[
A \times A.
\]

Since \(A \times A\) contains \(n^2\) ordered pairs, the relation can be represented naturally by an \(n\times n\) matrix.

This visualization allows students to interact with those matrix entries and observe how different properties of relations change the number of independent choices.

---

## 📚 Topics Covered

### 1. All Relations

There are \(n^2\) possible ordered pairs in \(A\times A\).

Every matrix entry can independently be either:

- `0` → the ordered pair is not in \(R\)
- `1` → the ordered pair is in \(R\)

Therefore,

\[
\boxed{2^{n^2}}
\]

relations are possible.

---

### 2. Reflexive Relations

A relation \(R\) is reflexive if

\[
(a,a)\in R
\]

for every \(a\in A\).

Therefore, every diagonal entry of the relation matrix is **compulsory**.

There are:

\[
n
\]

compulsory diagonal entries and

\[
n(n-1)
\]

remaining off-diagonal entries.

Each off-diagonal entry has two choices.

Hence,

\[
\boxed{2^{n(n-1)}}
\]

reflexive relations are possible.

---

### 3. Symmetric Relations

A relation \(R\) is symmetric if

\[
(a,b)\in R
\iff
(b,a)\in R.
\]

Therefore, the two matrix entries

\[
(a,b)
\quad\text{and}\quad
(b,a)
\]

must always behave as a **single decision**.

#### Independent decisions

There are:

- \(n\) diagonal cells
- \(\binom{n}{2}\) mirror-pairs

Therefore,

\[
n+\binom{n}{2}
=
n+\frac{n(n-1)}{2}
=
\frac{n(n+1)}{2}.
\]

Each independent decision has two choices.

Hence,

\[
\boxed{
2^{n(n+1)/2}
}
\]

symmetric relations are possible.

For example, when \(n=3\):

\[
3+\binom{3}{2}=3+3=6
\]

independent decisions exist.

Therefore,

\[
\boxed{2^6=64}
\]

symmetric relations are possible.

The visualization makes this process interactive by grouping

\[
(a,b)\leftrightarrow(b,a)
\]

into one decision block.

---

### 4. Antisymmetric Relations

A relation \(R\) is antisymmetric if

\[
(a,b)\in R
\text{ and }
(b,a)\in R
\implies a=b.
\]

For every diagonal entry \((a,a)\), there are two choices:

- include it
- exclude it

Therefore, the diagonal contributes

\[
2^n.
\]

For every unordered pair

\[
\{a,b\},\qquad a\neq b,
\]

there are exactly three possibilities:

1. Neither \((a,b)\) nor \((b,a)\)
2. \((a,b)\) only
3. \((b,a)\) only

There are

\[
\binom{n}{2}
\]

such unordered pairs.

Hence,

\[
\boxed{
2^n\,3^{\binom n2}
}
\]

or equivalently,

\[
\boxed{
2^n3^{n(n-1)/2}
}
\]

antisymmetric relations are possible.

---

## 🖥️ Interactive Features

The visualization includes:

- Set sizes \(n=2,3,4,5\)
- Interactive relation matrix
- Synchronized roster representation
- All possible ordered pairs represented by matrix cells
- Clickable matrix entries
- Reflexive relations with a compulsory diagonal
- Symmetric relations with coupled mirror cells
- Antisymmetric relations with three-choice blocks
- Live independent-choice counting
- Formula displayed for each type of relation
- Random valid relation generator
- Reset functionality
- Step-by-step progression through the four types of relations

---

## 🔄 Matrix and Roster Form

The visualization keeps the two representations synchronized.

For example, if

\[
R=\{(a,b),(b,a),(c,c)\},
\]

the corresponding matrix contains `1` in exactly those positions.

When a matrix entry changes from `0` to `1`, the corresponding ordered pair automatically appears in the roster form.

Similarly, when a symmetric pair is selected, both

\[
(a,b)
\]

and

\[
(b,a)
\]

appear automatically.

---

## 🧠 Main Learning Idea

The most important goal of the visualization is to demonstrate that the counting formulas come from identifying **independent choices**.

For example, for symmetric relations:

```text
n² matrix cells
       ↓
diagonal cells + mirror pairs
       ↓
n + C(n,2) independent decisions
       ↓
n(n+1)/2 independent decisions
       ↓
2^(n(n+1)/2) symmetric relations
