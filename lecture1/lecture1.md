## Lecture notes

What is a stocastic process?

- informally, it models random/uncertainq uantities that evolve/change over time
- e.g. weather, stock price
  at each specific time, this is modeled as a random variable
- together, across timestamps it forms a sequence of random variables, that we call stocastic
  processes
- in this course, we will learn how to define and mathematically argue about some of the most
  fundamental stochastic processes
- Rough plan:
  - for the first two lectures: review
  - markov chains ("memoryless" stochastic process)
  - markov random fields (hidden markov chains)
  - martingales ("fair" stochastic process)
  - brownian motion abd diffusions ("continuous" stoch processes)
- note: we do not assume measure theory
  - pros: simples:
  - cons: some theorems near the end will have "high level" proof
- Review of basic probability theory
  - Probability Axioms
  - informally, "probability" of an event is a way to assign a number in [0,1] quantifying how
    "uncertain" you are about the event happening
  - Formamly, exists A, P(A) \exists [0,1]
  - P:{events = subsets of state space} -> [0,1]
  - one property is P(\omega) = 1
    For any infinite sequence of events, A_1, A_2, ..., A_n, ...
    s.t. A(i) \cap A(j) = \emptyset for i \neq j
  - P(\cup*{i=1}^{\infty} A_i) = \sum*{i=1}^{\infty} P(A_i)
    E.x. coin flip:
    \omega = {H,T}
    Fair, P({H}) = 1/2 and P({T}) = 1/2
    P({H,T}) = P({H}\cup {T}) = P({H}) + P({T}) = 1/2 + 1/2 = 1
    P(\emptyset) = 0
    Conditional probability
  - informally, conditional probability is the prob. of an event if we know that another event
    happens
  - formally, given, A,B \subset \omega, then P(A|B) = P(A\cap B) / P(B)
  - notion of independence
    - def: two events, A, B are independet if P(A|B) = P(A)
- Theorem: Bayes Rule
  - P(A|B) = P(B|A)P(A) / P(B)
- if I partition \omega (the state space) in B_1, ..., B_k, (\omega = \cup B_i, B_i \cap B_j =
  \emptyset \forall i != j)
- \forall A \subset \omega, A = (A\cap B_1) \cup (A\cap B_2)...\cup (A\cap B_k) -> P(A) =
  \sum{i=1}{k}P(A\capB_i)
  Law of total prob (LTP):
- P(A) = \sum{i=1}{k}P(B_i)P(A|B_i)
- Bayes rule + LTP:
  - P(B|A) = \frac{P(A|B)P(B)}{P(B)P(A|B)+P(B^c)P(A|B^c)}
    Expectation and variance
- X: \omega -> Real numbers (random variable)
- E[X] = {\sum{x}xP(X=x), X is discrete or integralxf_x(x)dx is X is continuous}
  where P(X=x), PMF (probability mass function, f_x(x) is PDF (probability density function)
- CDF, F_x(c) = P(X=x)
- satisfies:

1. linearity of expectation

- \forall X, Y, r.v's, \lambda \elem R,
  E[X+\lambda Y] = E[X] + \lambda E[Y]

2. moments E[X^k], k = 1, 2, ...
3. variance: Var(x) = E[X^2] = E[X]^2 = E[(X-E[X])^2])] > 0

- E[X^2] \geq E[X]

Basic prob inequalities:

1. Markov's ineq:

- \forall X r.v. t > 0, P(|X| \geq t) \leq E[|X|]\t

2. chebyshev's ineq
   P(X-E[X])\geq t\sqrt(Var(X)) \leq 1\(t^2)

X, Y, \omega -> R
Joint CDF, F\_(X,Y)(x,y) = P(X\leq x, Y \leq y)
Case 1: X,Y are discrete

- Joint PMF: P*(X,Y)(x,y) = P(X=x, Y=y)
  Marginal PMF: P_X(x)=\sum_y (P*(X,Y)(x,y))
  Conditional PMF P\_(X|Y)(x|y)-P(X=x|Y=y)=\frac{}{}

Case 2: X, Y are continuous
Joint PDF f*(X,Y)(x,y)
Joint CDF: F*(X,Y)(x,y)=\integral (\-infinite,x) \integral (\-infinity, y) f\_(X,Y)()

- finish this with picture
  Conditional PDF:
  f*{X,Y}(x|y) = f*{X,Y}(x,y) / f_Y(y)

independence
