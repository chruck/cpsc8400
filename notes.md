CPSC 8400 - Design and Analysis of Algorithms
===
Dr. Brian Dean
Spring 2018

(Ja&#x0304;s Eckard)

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
- __correct__ output
  - always terminates
  - "close enough" sometimes fine
  - randomized alg fail, small probability

- __efficient__ use of resources
  - fast (time)  &larr; most
  - memory
  - bandwidth
  - power/heat used

- __simple__:  "elegant" to describe, understand, analyze
  - debug

"step" - what is it?
  - operation
  - instruction on chipset?

linear search - N steps
binary search - log<sub>2</sub>N steps

### Empirical Performance Testing
Just run it

"average case" or "worst case"?

scalability

how get inputs?  &larr; may not actually be rep of what's in real
world

"sloppy"

### Asymptotic Analysis
CS usually concerned w/ "worst case" & scalability

O(f(n)) - ("&le;")
  - "upper-bounded by constant times f(N) as N grows large"
  - 17N<sup>2</sup> - 3N + 5 &rarr; O(N<sup>2</sup>)  "Order N squared"
  - but loses information
  - "high hidden constant"

&Omega;(N) - ("&ge;")
  - asymptotic lower bound:  "at least N"

&Theta;(N) - ("=")
  - both lower and upper

---
Lecture 2, Jan 16
---
### Intro Concepts *cont*
asymptotic notation
- O() is upper bound
- &Theta;() is upper and lower bound (&larr; preferred)
- &Omega;() is lower bounds &rarr; eg for mem

O() often used as placeholder in math

- constant:  O(1)
- log:  O(log n)  &larr; use log lots, but base doesn't matter &rarr;
usually log<sub>2</sub>
- linear:  O(n)  &larr; usually can't get better
- polynomial:  O(n log(n)), O(n<sup>2</sup>), ...  O(n<sup>100</sup>)...
- exponential:  O(
