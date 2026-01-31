# Time Hierarchy Therorem

### Important Notations and Definitions: 

Turing Machine $\to$ TM

$\mathcal{O}(f(n))$ : the function grows at most as fast as $f(n)$ or it does not grow faster than $f(n)$ (upper bound - read as Big O of f of n).

$o(f(n))$ : the function grows strictly slower than $f(n)$ (small o of f of n).

$\Omega (f(n))$ : the function $f(n)$ grows at least as fast as $f(n)$, this is the lower bound (Big omega of f of n), the function can grow much faster than this.

$\Theta (f(n))$ : grows at the same rate (tighter or both bounds - read as Big theta of f of n).

**These notations describes growth rate, not what "always happens."**

They compare how two functions behave as $n \to \infty$. They do not mean "the algorithm uses exactly this much time."

**For example:** $f(n) = n^2$

**Big-O: Upper bound - this is the ceiling of the function (asymptotically).**

$$
  T(n) \in \mathcal{O}(n^2)
$$

  meaning:
  
  `For sufficiently large n, the running time is at most proportional to` $n^2$

  Formally:

$$
\exists c>0, n_0>0 \text{ such that }  T(n) \le c \cdot n^2 \text{for all } n \ge n_0.
$$

  So the algorithm can run in:

  * $n$ time
  * $n log n$ time
  * $5n^2$ time
  * but not in $n^3$ time as this asymptotically grows much faster than $n^2$.

Note: It does not mean the algorithm uses always $n^2$ time, this is the ceiling on which theh algorithm can run.

**Big-Omega: Lower Bound / Floor - it can not grow slower than** $n^2$

$$
T(n) \in \Omega(n^2)
$$

meaning:

`for sufficiently large n the running time is at least proportional to` $n^2$.

Formally:

$$
\exists c>0, n_0>0 \text{ such that} T(n) \ge c \cdot n^2 \text{ for all } n \ge n_0.
$$

**So the algorithm might run in:**

* $n^3$ time
* $10n^2$ time
* $n^2 log n$ time
* but not in $n log n$ time as this is asymptotically slower than $n^2$.

So the function can not grow slower than $n^2$ (asymptotically).

**Big-theta: Tighter bound:**

$$
T(n) \in \Theta(n^2)
$$

This means both:
$$T(n) \in \mathcal{O}(n^2)$$ and $$T(n) \in \Omega(n^2)$$

So it grows on the order of $$n^2$$, neither asymptotically smaller nor larger.

So the algorithm might run in:

* $$5n^2$$
* $$5n^2 \add n
* but not in $$nlogn$$ or $$n^3$$.

So,

**“Algorithm A is $O(n^2)$”**
It means a **worst-case upper bound** (usually).

And:

**“Problem P requires $\Omega(n^2)$ time”**
It means **any algorithm solving it must take at least that long** (a lower bound on the problem).

We can think of growth rates as **speed limits**:

| Notation      | Meaning                         | Analogy                     |
| ------------- | ------------------------------- | --------------------------- |
| $O(n^2)$      | grows no faster than $n^2$      | speed limit ≤ 100 km/h      |
| $\Omega(n^2)$ | grows at least as fast as $n^2$ | speed is ≥ 100 km/h         |
| $\Theta(n^2)$ | grows exactly like $n^2$        | speed stays around 100 km/h |


**What does $f(n) \in \mathbb{\Omega}(g(n))$ means:**

$A \in B \to$  A is an element of or A is an member of B. It is used for set membership. 
For $\mathcal{T}(n) \in \mathcal{O}(n^2)$: The function $\mathcal{T}(n)$ is a member of the set of functions that grow at most as fast as $n^2$.

$$
\mathcal{O}(n^2) =  f(n) \mid \exists c>0, n_0>0 \text{ such that } f(n) \le c \cdot n^2 \text{ for all } n \ge n_0 
$$


It reads: “Big-O of $n^2$ is the set of functions $f$ of n such that there exist constants c and $n_0$ where $f(n)$ is less than or equal to c times $n^2$ for all n greater than or equal to $n_0$.”

The vertical bar `|` means **“such that.”** It separates the description of the set from the condition elements must satisfy. So everything to the right of `|` is the property a function must meet to be included in the set $\mathbb{O}(n^2)$.

$$
f(n) \in \mathbb{\Omega}(g(n)) \iff \exists c > 0, n_0 \text{ such that } f(n) \ge c \cdot g(n) \text{ for all } n \ge n_0
$$



Example:
$f(n)$ : $n \log n$.

So for $\mathbb{O}(f(n))$, the function will grow at most as $f(n) : n \log n$, and for $o(f(n))$, the function will grow strictly slower than $f(n)$. All the functions that grow strictly slower than $\mathbb{O}(f(n))$ are in the set of $o(f(n))$. 

$n \in o\big(n \log n\big), \quad
n \log n \notin o(n)$

**Time Hierarchy Theorem:**

It is about in terms computation of algorithms, there is a hierarchy among time complexities.

For any time constructible Function $f : \mathbb{N} \to \mathbb{N}$ there exists a language $\mathbb{A}$ that is decidable by a TM in $\mathcal{O}(f(n))$ time but not in $o(\frac{f(n)}{\log_2 f(n)})$ time. 


$$
o( \frac{f(n)}{\log_2 f(n)} )
$$

This means:

Any function that grows **strictly slower than**

$$
\frac{f(n)}{\log_2 f(n)}
$$


So the theorem says:

There exists a language that:
Can be solved in time $\mathbb{O}(f(n))$ but cannot be solved in any time that is asymptotically smaller than $\frac{f(n)}{\log_2 f(n)}$.

For any reasonable time bound $f(n)$:

There is always some problem that can be solved in time $f(n)$ but cannot be solved significantly faster — specifically, not in time smaller than 

$$
\frac{f(n)}{\log_2 f(n)}.
$$

So more time really does buy more computational power.

### Total Function:

A function $f : \mathbb{N} \to \mathbb{N}$ (it is read $f$ is a function from natural natural to natural number, that is f is a function that takes a natural number as input and returns a natural number as output.) is total  function if for every input x of length $|x|$ = n, a deterministic Turing Machine (TM) halts on x and decide it in $f(n)$ steps. So for every input x, the function is decidable meaning it will halt on every input and either accept or reject it.

$\mathcal{TIME}(f(n))$ is the class of languages which can be decided by a TM in $\mathbb{O}(f(n))$ time.

$\mathcal{TIME}(f(n))$ = {L ∣ L is decidable by a deterministic TM in $\mathbb{O}(f(n))$ time}


**Why this is important for Time hierarchy theorem:**

In order to show there is a hierarchical relation among various time complexities, the TM must able to decide on every input for a language. In this theorem it will only work with the inputs which it can decide, the inputs that are not decidable by the TM, it will be rejected automatically. So the TM does not have to deal with those inputs.

### Time Constructibility:

Time constructible means if we say a function uses $f(n)$ steps to complete the work it is  
