---
title: "To Type or Not to Type: Quantifying Detectable Bugs in Javascript"
date: 2017-11-08T21:48:27-06:00
slug: 'do-type-or-not-to-type-quantifying-detectable-bugs-in-javascript'
tags: ["Javascript", "Papers"]
---

Tonight I read an interesting paper entitled
[To Type or Not to Type: Quantifying Detectable Bugs in Javascript](http://ttendency.cs.ucl.ac.uk/projects/type_study/documents/type_study.pdf).
It attempts to measure the effectiveness of static typing in Javascript by
analyzing randomly selected
[issues of open-source projects](http://ttendency.cs.ucl.ac.uk/projects/type_study/data/bugs.json)
on GitHub and checking which ones could have been prevented if a static type
checker such as Flow or TypeScript had been used. The most important conclusion
is that *15% of the bugs* could have been prevented with type annotations.

This is a significant number and is a strong argument for type checking.
However, there's never a free lunch and static typing comes at a cost during
development time. Indeed, the developer has to reason about the types while
coding and type the type annotations. To measure this, the authors of the paper
counted the number of tokens they had to type to fix a particular bug. I didn't
find the results of this part very solid because this method doesn't take into
account the "reasoning" time. However, they did come to the valid conclusion
that Flow has an advantage over TypeScript here as its stronger inference system
requires less type annotations to detect typing bugs.

I have no practical experience with either type checker yet. However, I have
worked in statically typed compiled languages before and I always felt a certain
comfort in having the compiler detect some errors early on. Therefore, on the
"static typing vs dynamic typing" debate I am more on the side of static typing.
This is also why I am somewhat happy with the main result of the paper as it
provdes scientific evidence for my gut feeling. It is definitely an incentive to
start introducing Flow or TypeScript in the [Sutori](https://www.sutori.com)
codebase (an Ember.js single-page application).

The [website](http://ttendency.cs.ucl.ac.uk/projects/type_study/index.html) has
more information about the research. What I would have found interesting is the
list of bugs that were preventable with a static type checker. Unfortunately, I
couldn't find any such list. I would have liked to go through and see what
classes of bugs are typically caught, mainly to gain more intuition and apply
this knowledge on the codebase that I work on.
