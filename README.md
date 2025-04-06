# Asymptotic Equivalences

In the lectures, we said that logarithms with different bases don't affect the
asymptotic complexity of an algorithm. Prove that $O(\log_{2} n)$ is the same as
$O(\log_{5} n)$. Use the mathematical definition of $O$ -- do a formal proof,
not just the intuition.

I have started with the formal definition of $O$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$T(n) \in O(f(n)) \iff \exists c, n_0: T(n) \leq c \cdot f(n) \forall n \geq n_0$

---

## Answer:

### Part 1
(If the base doesn't matter and $T(n) \in O(\log_2(n))$, then it should follow that $T(n) \in O(\log_5(n))$. The converse should also hold.)

$T(n) \in O(\log_2(n)) \iff \exists c, n_0 : T(n) \le c \cdot \log_2(n) \forall n \ge n_0$

($\log_2(n)$ can be rewritten as $\frac{\log_5(n)}{\log_5(2)}$; rewrite above expression)

$T(n) \in O(\log_2(n)) \iff \exists n_0 : T(n) \le c \cdot \frac{\log_5(n)}{\log_5(2)} \forall n \ge n_0$

Let $c = \log_5(2)$. That results in:

$T(n) \in O(\log_2(n)) \iff \exists n_0 : T(n) \le \log_5(2) \cdot \frac{\log_5(n)}{\log_5(2)} \forall n \ge n_0$

(Cancel out numerator and denominator):

$T(n) \in O(\log_2(n)) \iff \exists n_0 : T(n) \le \log_5(n) \forall n \ge n_0$

### Part 2 (Show the other way)

$T(n) \in O(\log_5(n)) \iff \exists c, n_0 : T(n) \le c \cdot \log_5(n) \forall n \ge n_0$

($\log_5(n)$ can be rewritten as $\frac{\log_2(n)}{\log_2(5)}$; rewrite above expression)

$T(n) \in O(\log_5(n)) \iff \exists n_0 : T(n) \le c \cdot \frac{\log_2(n)}{\log_2(5)} \forall n \ge n_0$

Let $c = \log_2(5)$. That results in:

$T(n) \in O(\log_5(n)) \iff \exists n_0 : T(n) \le \log_2(5) \cdot \frac{\log_2(n)}{\log_2(5)} \forall n \ge n_0$

(Cancel out numerator and denominator):

$T(n) \in O(\log_5(n)) \iff \exists n_0 : T(n) \le \log_2(n) \forall n \ge n_0$

### Conclusion

Using the change of log formula, a logarithm can be written as some constant times the log of the same number in a different base (i.e. two logarithms with different bases differ only by constant factor and constant factors don't matter). Therefore, we can say that $O(\log_a(n))$ and $O(\log_b(n))$ are asymptotically the same.