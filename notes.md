CPSC 8400 - Design and Analysis of Algorithms
===
Dr. Brian Dean
Spring 2018

(Ja&#0304;s Eckard)

---
Lecture 1, Jan 11
---

- &rarr; Probability theory
- &rarr; Amortized analysis
- &rarr; Recurrances
- &rarr; ( n )  "n choose 2" (binomial coefficient)
         ( 2 )
  - "n choose k" = n! / k!(n-k)! &rarr; number of combinations of
  _k_-sets of _n_ elements
- &rarr; algorithmsexplained.com
- &rarr; Dr. Dean's papers
- &rarr; log<sub>2</sub>1 billion = 30
- &rarr; "Big O Notation"

__algorithms__ - heart and soul of computing
- math theory meets practice

programming != algorithmic problem solving

Dijkstra - "CS : computers :: astronomy : telescopes"

homework:  typeset, PDF @ handin.cs.clemson.edu
- due before class
- 35% of final grade

quizzes:
- 2 of
- 2 * 20%

final:
- 25%

collaborators should be listed
- individual write up

Proofs:  must be convincing
- level of detail is __undefined__

Don't look up solutions from previous semesters

### A Good Algorithm
- always terminates
- __correct__ output
- "close enough" sometimes fine
- randomized alg fail, small probability

- __efficient__
  - fast (time)  &larr; most
  - memory
  - bandwidth
  - power/head used

- __simple__:  "elegant" to describe, understand, analyze
  - debug

"step" -N - what is it?
  operation

### Empirical Performance Testing
Just run it

"average case" or "worst case"?

scalability

how get inputs?  &larr; may not actually be rep of what's in real
world

"sloppy"

### Asymptotic Analysis
CS usually concerned w/ "worst case" & scalability

O(f(n)) - ("&leq;")
  - "upper-bounded by constant times f(N) as N grows large"
  - 17N<sup>2</sup> - 3N + 5 &rarr; O(N<sup>2</sup>)  "Order N squared"
  - but loses information
  - "high hidden constant"

&omega;(N) - ("&greq;")
  - asymptotic lower bound:  "at least N"

&theta;(N) - ("=")
  - both lower and upper
