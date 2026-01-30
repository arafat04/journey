# Time Hierarchy Therorem

Abbreviations: 

Turing Machine $\to$ TM

It is about in terms computation of algorithms, there is a hierarchy among time complexities.

For any time constructible Function $f : \mathbb{N} \to \mathbb{N}$ there exists a language $\mathbb{A}$ that is decidable by a TM in $\mathbb{O}(f(n))$ time but not in $o(\frac{f(n)}{\log_2 f(n)})$ time. 

### Total Function:

A function $f : \mathbb{N} \to \mathbb{N}$ (it is read $f$ is a function from natural natural to natural number, that is f is a function that takes a natural number as input and returns a natural number as output.) is total  function if for every input x, a Turing Machine (TM) halts on x and decide it. So for every input x, the function is decidable meaning it will halt on every input and either accept or reject it.

$ \mathbb{O}(f(n))$ is the set of languages which can be decided by a TM in $ \mathbb{O}(f(n)) time.

**Why this is important for Time hierarchy theorem:**

In order to show there is a hierarchical relation among various time complexities, the TM must able to decide on every input for a language. In this theorem it will only work with the inputs which it can decide, the inputs that are not decidable by the TM, it will be rejected automatically. So the TM does not have to deal with those inputs.

### Time Constructibility:

