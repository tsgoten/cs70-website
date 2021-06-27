---
layout: page
title: Homework Guidelines
latex: true
permalink: /resources/homework-guidelines/
sidebar: true
---

## Formatting Homework

You can write your homework in one of the following ways:

1.  Typeset your answers using LaTeX. We strongly recommend doing this.
    See the [Latex Guide]({% link resources/latex.md %}) for help using LaTeX.
2.  Type your answers using a mainstream word processor.
3.  Neatly handwrite, then use a flatbed scanner or smartphone app (such as CamScanner) to produce a PDF. **Do not simply take a photo and dump it into a PDF.**

The readers work hard to grade your homeworks in a timely manner, and with useful feedback. Given the size of the course, we require a certain format of all homeworks: **each problem must start on a new page, and clearly display the problem number; if a problem has multiple parts, make sure that each part fits on a page.**
You must also select the pages for each problem when you submit to Gradescope, if you do not do this, **you may not get points on that problem**.

**List your collaborators on the first page of your submission.** If you have no collaborators, you must explicitly write "none".

## Three-Part Algorithm Format

Oftentimes, a problem will ask you to "give/design/devise/formulate/create/etc. an algorithm" or to "show how" to solve some computational task. In this case, write your solution in the 3-part algorithm format:

1. **Algorithm description**. This can come in terms of pseudocode, or a description in English. It must be unambiguous, as short as possible (but no shorter), and precise.
    - Your pseudocode does not need to be executable. You should use notation such as "add _X_ to set _S_" or "for each edge in graph G". Remember you are writing your pseudocode to be read by a human, not a computer.
    - See DPV for examples of pseudocode.
2. **Proof of correctness**. Give a formal proof (as in CS 70) of the correctness of your algorithm. Intuitive arguments are not enough.
    - Again, see DPV for examples of proofs of correctness.
3. **Runtime analysis**. You should use big-O notation for your algorithm's runtime, and justify this runtime with a runtime analysis. This may involve a recurrence relation, or simply counting the complexity and number of operations your algorithm performs.

## Solo Problems

Some problems on the homework may be labelled as **solo problems**. These problems are written to be easier than "standard" homework problems, but you are not allowed to collaborate with other students on these problems. You are still allowed to consult staff, e.g, at office hours for help on these problems, and staff can still answer questions about these problems to groups of people at office hours (though you should avoid discussing them at office hours while waiting for staff to get to you). The goal of these problems is to give yourself a benchmark for how well you would do if a similar problem appeared on an exam. 

## FAQ

__When I have to write an algorithm, how should I format my answer?__

We will do our best to specify what we expect you to write in each question, but when in doubt, default to a "3-part" solution, which is discussed [here](/policies/#responding-to-algorithm-problems).

__How efficient does my algorithm need to be?__

Do your best. We may or may not give a running time requirement up-front (sometimes that would give a strong hint on how to do the problem). Some baseline considerations: Most problems have a natural naive/brute-force algorithm (e.g. "try all possibilities") or other trivial approaches (e.g. "apply [suboptimal known algorithm] without any modification or thought"). These usually receive no credit. Exponential-time algorithms usually get no credit. We often award partial credit to algorithms that are slower than our official solutions.

__Can I cite theorems and algorithms from the textbook or lecture without proof?__

Yes.

__Can I use theorems and algorithms from other sources?__

As detailed in the syllabus, you should not look up problem solutions using the internet/other sources. If you do run into a useful theorem/algorithm that aids in your solution, (a) you must prove it in your solution and (b) make sure to cite the source you got it from.

__Is my interpretation of the problem correct? What about such-and-such case?__

Piazza is not a good forum to figure out what a problem is asking / ask for hints or confirmation. Even something as innocuous as, "So on x input we would return y solution, correct?" can reveal a lot about a problem, which hurts other students' understanding. Please first try asking fellow students and coming to office hours. If after doing this you still believe the problem is poorly worded and genuinely ambiguous, please go ahead and explain the ambiguity, but we will tend to avoid answering such questions when the problem is not unclear. Much of the challenge of the problem sets is precisely understanding the nuances of the problem, and asking to be given all the details defeats that purpose.

__Do we give our algorithm's worst-case running time, or average running time?__

Most algorithms in this course are deterministic ones, for which we are always concerned with the worst case. For randomized algorithms, the expected running time is acceptable. Note that this may receive less credit if a superior deterministic algorithm is known.

__Do I have to give Θ(⋅) running times for my algorithms, or only O(⋅)?__

If it is possible to provide a $$\Theta(\cdot)$$ bound in a simple manner, then you should do so. If it is not, then give the tightest $$\mathcal{O}$$ bound possible.

__What's the deal with Θ(⋅) vs O(⋅) notation anyways?__

We try to stick with the actual definitions, which means to use $$\Theta(\cdot)$$ notation when you're describing the exact asymptotic runtime. However, the textbook often uses $$\mathcal{O}(\cdot)$$ notation even when giving tight bounds; if in the above example you wrote $$\mathcal{O}(n)$$ for the runtime, we would still give you full credit because the runtime was correct, even though it's better practice to use $$\Theta(\cdot)$$ notation.

__Can I make reasonable assumptions about the computational model?__

Yes. If you think the assumption is not totally obvious, feel free to explain it as you perform the runtime analysis (eg "Because indexing into arrays takes constant time, ...")

__Can I make [some additional assumption] about [some homework problem] that was not given in the problem?__

No. For example, don't assume numbers in a list are distinct, don't assume a graph is connected, etc.

__Do I need to provide a justification for my answer?__

Yes, unless the problem explicitly states that justification is not required.

__How rigorous does my explanation need to be?__

Rigorous enough for any average CS170 student to understand it completely.

__Can I use things shown in discussion/lecture/textbook without proof?__

General response to this is: you are free to use things shown to you in lecture/textbook/discussion without proof, within bounds. The "within bounds" means that be reasonable with us --- if we ask you to show that $$ \sum_{k=1}^n k = \Theta(n^2)$$, don't say "This was shown in discussion so it is true." Don't take away the heart of a problem and claim it was done in X, that's being too clever for your own good and won't fare well. We expect students to be able to reason about what "within bounds" means. So feel free within bounds. And if in doubt about anything --- **ask.**

__How will homework be graded?__

Homework will be graded as a mix of coarsely and finely graded parts. (Some problems may be graded on a 100%, 50%, 0% scale, while others may be graded more carefully and finely.) An unannounced, not necessarily strict, subset of problems will be graded each week. Points will be assigned to problems _after_ students have submitted the homework.
