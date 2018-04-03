Another attempt to summarise things with pictures and informal description.  This time: Partitions.

Partitions are covered in section 1.2.1 of [the book](https://arxiv.org/pdf/1803.05316.pdf).  They're also covered in [Exercise 3](https://forum.azimuthproject.org/discussion/1876/exercise-3-chapter-1#latest).

## What is a Partition?

John describes it as follows in [this comment](https://forum.azimuthproject.org/discussion/comment/16368/#Comment_16368):

> A partition of a set is a way of writing it as a disjoint union of nonempty subsets.

That's pretty accessible, even for non-mathematicians like me.  No harm in illustrating with an example.  Let's take a set of colleagues in some fictitious workplace:

![set of people](img/people.png)

And create a partition based on their roles:

![set of people partitioned by role](img/people-roles.png)

What makes that a partition?  Let's go back to the definition:

> a disjoint union of non-empty subsets

* Each of Product Managers, Engineers and Mathematicians has at least one person in it.  So there are no non-empty subsets.
* Each person fits in exactly one subset.  That means:
    * Thee subsets aren't overlapping, they're *disjoint*.
    * the original People set can be constructed by joining together the three subsets.  In set theory, "union" just means "join together".

Here's a slightly different way of defining a partition, drawing on some of the language above.

> A partition of a set splits the members into separate subgroups such that:

> 1. Every member of the set is contained in exactly one subgroup, and
> 1. Every subgroup contains at least one member

### What about the definition in the book?

Partitions are introduced in definition 1.8 in the book:

> If \\(A\\) is a set, a *partition* of \\(A\\) consists of a set \\(P\\) and, for each \\(p \in P\\), a non-empty subset \\(A_p \ss A\\), such that:

$$ A=\bigcup_{p\in P}A_p \qquad\text{and}\qquad  \text{if }p\neq q\text{ then }A_P\cap A_Q=\emptyset $$

There's a bit more in there, so let's break it down.  First, it introduces a new set \\(P\\) with members (\\p\\).  This just describes the partition itself, where each subgroup (or *part*) is a member of P.  In our example above, P is the set of roles, as follows:

![roles](img/roles.png)

So now we have the set \\(A\\) being partitioned, and the set \\(P\\) defining the parts.  Picking up the next part of the definition:

> for each \\(p \in P\\), a non-empty subset \\(A_p \ss A\\)

So: each \\(p\\) - each *part* - maps to a non-empty subset of \\(A\\).  That's just what we drew in the partition diagram above.  Here's a slightly different way of drawing it, such that \\(A\\) and \\(P\\) are both shown consistently as sets:

![Mapping of people to roles](img/people-roles-sets.png)

We can now enumerate the subsets \\(A_p \ss A\\):

* \((A_ProductManagers = {Sidd}\))
* \((A_Mathematicians = {Fiona, Aruna, Malcolm}\))
* \((A_Engineers = {Guillaume, Wendy}\))

Back to the definition:

$$ A=\bigcup_{p\in P}A_p $$

This says \\((A\\)) is the union \\(\bigcup\\) of all subsets \\(A_p\\) for each \\(p\in P \\).  So \\(A = A_ProductManagers + A_Mathematicians + A_Engineers\\).

And so the final component of the definition:

$$\text{if }p\neq q\text{ then }A_P\cap A_Q=\emptyset$$

This is the 'disjoint', or non-overlapping clause. Translating that literally into words:

> If p isn't equal to q, then the intersection of subsets \\(A_P\\) and \\(A_Q\\) is the empty set.  

Less prosaically, \\(A_P\\) and \\(A_Q\\) don't share any members unless \\(p = q\\) (in which case \\(p\\) and \\(q\\) represent the same element).

