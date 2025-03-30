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

(Want to show that each function is $\in O(\text{the other})$)
#### Step 1: Show that $\log_2(n) \in O(\log_5(n))$

Substitute $\log_2(n)$ for $T(n)$ and $\log_5(n)$ for $f(n)$

$\log_2(n) \in O(\log_5(n)) \iff \exists c,n_0: \log_2(n) \le c \cdot \log_5(n) \forall n \ge n_0$

Introduce change of base for logarithms

$\log_2(n) = \frac{\log_5(n)}{\log_5(2)}$

Let $c_1 = \frac{1}{\log_5(2)}$

So, $\log_2(n) = c_1\log_5(n)$

Substitute into formula

$\log_2(n) \in O(\log_5(n)) \iff \exists c,n_0: c_1\log_5(n) \le c \cdot \log_5(n) \forall n \ge n_0$

Cancel out logarithms

$\log_2(n) \in O(\log_5(n)) \iff \exists c,n_0: c_1 \le c \forall n \ge n_0$

Bring in value for $c_1$ and let $c = 10$ (arbitrarily)

$\log_2(n) \in O(\log_5(n)) \iff \exists n_0: \frac{1}{\log_5(2)} \le 10 \forall n \ge n_0$

The right side always holds true, so the left side must be true

#### Step 2: Show that $\log_5(n) \in O(\log_2(n))$

(Same process)

Substitute  $\log_5(n)$ for $T(n)$ and $\log_2(n)$ for $f(n)$

$\log_5(n) \in O(\log_2(n)) \iff \exists c, n_0: \log_5(n) \le c \cdot \log_2(n) \forall n \ge n_0$

Introduce change of base for logarithms

$\log_5(n) = \frac{\log_2(n)}{\log_2(5)}$

Let $c_1 = \frac{1}{\log_2(5)}$

So, $\log_5(n) = c_1\log_2(n)$

Substitute into formula

$\log_5(n) \in O(\log_2(n)) \iff \exists c,n_0: c_1\log_2(n) \le c \cdot \log_2(n) \forall n \ge n_0$

Cancel out logarithms

$\log_5(n) \in O(\log_2(n)) \iff \exists c,n_0: c_1 \le c \forall n \ge n_0$

Bring in value for $c_1$ and let $c = 10$ (arbitrarily)

$\log_2(n) \in O(\log_5(n)) \iff \exists n_0: \frac{1}{\log_2(5)} \le 10 \forall n \ge n_0$

The right side always holds true, so the left side must be true

Since both $\log_5(n) \in O(\log_2(n))$ and $\log_2(n) \in O(\log_5(n))$, we can say that $O(\log_2(n))$ and $O(\log_5(n))$ are the same.

---

**I certify that I have listed all sources used to complete this exercise, including the use
of any Large Language Models. All of the work is my own, except where stated
otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is
suspected, charges may be filed against me without prior notice.**