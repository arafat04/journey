# Time Hierarchy Therorem

### Important Notations and Definitions: 

Turing Machine $\to$ TM

$\mathbb{O}(f(n))$ : the function grows at most as fast as $f(n)$ or it does not grow faster than $f(n)$ (upper bound).

$o(f(n))$ : the function grows strictly slower than $f(n)$

$\mathbb{\Omega}f(n)$ : the function $f(n)$ grows at least as fast as $f(n)$, this is the lower bound, the function can grow much faster than this.

$\mathbb{\Theta}f(n)$ : grows at the same rate (tighter or both bounds).

**What does $f(n) \in \mathbb{\Omega}(g(n))$ means:**

$A \in B \to$  A is an element of or A is an member of B. It is used for set membership. For $\mathbb{T}(n) \in \mathbb{O}(n^2)$: The function $\mathbb{T}(n)$ is a member of the set of functions that grow at most as fast as $n^2$.

$$
\mathcal{O}(n^2) = \{ f(n) \mid \exists c>0, n_0>0 \text{ such that } f(n) \le c \cdot n^2 \text{ for all } n \ge n_0 }
$$

It reads: “Big-O of $n^2$ is the set of functions $f$ of n such that there exist constants c and $n_0$ where $f(n)$ is less than or equal to c times n squared for all n greater than or equal to $n_0$.”

The vertical bar `|` means **“such that.”** It separates the description of the set from the condition elements must satisfy. So everything to the right of `|` is the property a function must meet to be included in the set $\mathbb{O}(n^2)$.

$$
f(n) \in \mathbb{\Omega}(g(n)) \iff \exists c > 0, n_0 \text{ such that } f(n) \ge c \cdot g(n) \text{ for all } n \ge n_0
$$



Example:
$f(n)$ : $n \log n$.

So for $\mathbb{O}(f(n))$, the function will grow at most as $f(n) : n \log n$, and for $o(f(n))$, the function will grow strictly slower than $f(n)$. All the functions that grow strictly slower than $\mathbb{O}(f(n))$ are in the set of $o(f(n))$. 

$n \in o\big(n \log n\big), \quad
n \log n \notin o(n)$

It is about in terms computation of algorithms, there is a hierarchy among time complexities.

For any time constructible Function $f : \mathbb{N} \to \mathbb{N}$ there exists a language $\mathbb{A}$ that is decidable by a TM in $\mathbb{O}(f(n))$ time but not in $o(\frac{f(n)}{\log_2 f(n)})$ time. 


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

$\mathbb{TIME}(f(n))$ is the class of languages which can be decided by a TM in $\mathbb{O}(f(n))$ time.

$\mathbb{TIME}(f(n))$ = {L ∣ L is decidable by a deterministic TM in $\mathbb{O}(f(n))$ time}


**Why this is important for Time hierarchy theorem:**

In order to show there is a hierarchical relation among various time complexities, the TM must able to decide on every input for a language. In this theorem it will only work with the inputs which it can decide, the inputs that are not decidable by the TM, it will be rejected automatically. So the TM does not have to deal with those inputs.

### Time Constructibility:

Time constructible means if we say a function uses $f(n)$ steps to complete the work it is  
