# Algorithm
A sequence of precise and unambiguous(clean) instruction designed in such a way that if they are executed in specified sequence the desired result is obtained within a finite number of steps.

# Algorithm Analysis
Analysis of algorithms is the determination of the <mark class="hltr-yellow">amount of time and space resources required to execute it</mark>.

## Why it is important?
- Behaviour prediction without implementation.
- The idea is to measure order of growth.
- More importantly, by analysing different algorithms, we can compare them to determine the best one for our purpose.

# Asymptotic Analysis
In asymptotic analysis, we evaluate the performance of an algorithm in terms of input size(we don't measure the actual running time).
- We calculate how the time(or space) taken by an algorithm increases with the input size.

# Order of Growth
A function $f(n)$ is said to be growing faster than $g(n)$ if
$$lim_{n \to \infty}\frac{g(n)}{f(n)} = 0$$
OR 
$$lim_{n \to \infty}\frac{f(n)}{g(n)} = \infty$$

- $f(n)$ and $g(n)$ represents time taken by the algorithm.
- $n, \ f(n), \ g(n)$ $\geq$ 0.
- function having higher order of growth is a bad algorithm.
## Direct way to Find and Compare Growths
1.  Ignore Lower Order Terms.
2. Ignore leading Term Constant
Example:
$f(n)  = 2n^2 + n + 6$,    Order of Growth : $n^2$ Quadratic
$g(n) = 100n +3$         Order of Growth : $n$ Linear.
#### How do we compare terms?

$$C < \log\log n < \log n < n^\frac 1 3 < n^\frac 1 2 < n < n^2 < n^3 < 2^n < n^n$$

# Case scenarios of Algorithm
1.  Best case : Constant
2.  Average case : Linear(<mark class="hltr-orange">Under the assumption that different input cases are equally likely</mark>)
3.  Worst case : Linear
