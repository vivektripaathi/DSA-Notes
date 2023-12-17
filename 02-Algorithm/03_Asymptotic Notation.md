# Asymptotic Notation :
Asymptotic notations are mathematical tools to represent the time complexity of algorithms for asymptotic analysis. The following 3 asymptotic notations are mostly used to represent the time complexity of algorithms:
## Big-oh(O) Notation:
The function $f(n) = O(g(n)) \ iff\ \exists$ +ve constants C and $n_0$ such that $f(n) \leq C * g(n) \ \forall \ n \geq n_0$.
- TheBig-oh(O) notation is the formal way to express the <mark class="hltr-orange">upper bound of an algorithm's running time</mark>.
- It measures the **worst case time complexity** or the longest amount of time an algorithm can possibly take to complete.

![Big Oh Graph](https://media.geeksforgeeks.org/wp-content/uploads/AlgoAnalysis-2.png)


## Omega($\Omega$) Notation:
The function $f(n) = O(g(n)) \ iff\ \exists$ +ve constants C and $n_0$ such that $f(n) \geq C * g(n) \ \forall \ n \geq n_0$.
- The notation Ω(n) is the formal way to express the <mark class="hltr-orange">lower bound of an algorithm's running time</mark>.
- It measures the **best case time complexity** or the best amount of time an algorithm can possibly take to complete.

![Big Omega Graph](https://media.geeksforgeeks.org/wp-content/uploads/AlgoAnalysis-3.png)

## Theta($\theta$) Notation:
The function $f(n) = O(g(n)) \ iff\ \exists$ +ve constants $C_1, C_2$ and $n_0$ such that $C_1*g(n)\leq f(n) \leq C_2 * g(n) \ \forall \ n \geq n_0$.
-  The notation $\theta(n)$ is the formal way to express the <mark class="hltr-orange">average bound of the algorithm' s running time</mark>.
- It measures the **average case time complexity** or the average amount of time an algorithm can possibly take to complete.

![Big Theta Graph](https://media.geeksforgeeks.org/wp-content/uploads/AlgoAnalysis-1.png)

## Asymptotic Notation Examples

> [!Example] Example 1: $f(n) = 2n^2 + 3n + 4$
> $\Rightarrow 2n^2 + 3n + 4 \leq 2n^2 + 3n^2 + 4n^2$
>$\Rightarrow 2n^2 + 3n + 4 \leq 9n^2$
>$\Rightarrow f(n) = f(g(n)) = O(n^2)$
>
>$\Rightarrow 2n^2 + 3n + 4 \geq 1*n^2$
>$\Rightarrow \Omega(n^2)$
>
>$\Rightarrow 1*n^2 \leq 2n^2 + 3n + 4 \leq 9n^2$
>$\Rightarrow \theta(n^2)$

> [!Example] Example 2: $f(n) = n^2\log n + n$
$\Rightarrow 1*n^2\log n \leq n^2\log n + n \leq 10n^2\log n$
$\Rightarrow O(n^2\log n)$
$\Rightarrow \Omega(n^2\log n)$
$\Rightarrow \theta(n^2\log n)$

> [!Example] Example 3: $f(n) = n!$
$f(n) = n! = n*(n-1)*(n-2)*......*2*1$
$\Rightarrow 1*1*1....1*1 \leq 1*2*3*.....*n\leq n*n*n*.....*n$
$\Rightarrow 1 \leq 1*2*3*.....*n\leq n^n$
$\Rightarrow O(n^n)$
$\Rightarrow \Omega(1)$
$\Rightarrow \theta\to$Can't be found

> [!Example] Example 4: $f(n) = \log n!$
$\Rightarrow \log(1*1*1....1*1) \leq \log(1*2*3*.....*n)\leq \log(n*n*n*.....*n)$
$\Rightarrow 1 \leq log(1*2*3*.....*n)\leq \log n^n$
$\Rightarrow O(n\log n)$  $[\because \log n^n = n\log n]$
$\Rightarrow \Omega(1)$
