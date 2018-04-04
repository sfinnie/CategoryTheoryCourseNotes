Another attempt to summarise things with pictures and informal description.  This time: Partitions.

Partitions are covered in section 1.2.1 of [the book](https://arxiv.org/pdf/1803.05316.pdf).  They're also covered in [Exercise 3](https://forum.azimuthproject.org/discussion/1876/exercise-3-chapter-1#latest).

## What is a Partition?

John describes it as follows in [this comment](https://forum.azimuthproject.org/discussion/comment/16368/#Comment_16368):

> A partition of a set is a way of writing it as a disjoint union of nonempty subsets.

That's pretty accessible, even for non-mathematicians like me.  No harm in illustrating with an example.  Let's take a set of colleagues in some fictitious workplace:

![set of people](https://raw.githubusercontent.com/sfinnie/CategoryTheoryCourseNotes/master/partitions/img/people.png)

And create a partition based on their roles:

![set of people partitioned by role](https://raw.githubusercontent.com/sfinnie/CategoryTheoryCourseNotes/master/partitions/img/people-roles.png)

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

> If \\(A\\) is a set, a *partition* of \\(A\\) consists of a set \\(P\\) and, for each \\(p \in P\\), a non-empty subset $A_p \subset A\\), such that:

$$ A=\bigcup_{p\in P}A_p \qquad\text{and}\qquad  \text{if }p\neq q\text{ then }A_P\cap A_Q=\emptyset $$

There's a bit more in there, so let's break it down.  First, it introduces a new set \\(P\\) with members (\\p\\).  This just describes the partition itself, where each subgroup (or *part*) is a member of P.  In our example above, P is the set of roles, as follows:

![roles](https://raw.githubusercontent.com/sfinnie/CategoryTheoryCourseNotes/master/partitions/img/roles.png)

We now have the set \\(A\\) being partitioned, and the set \\(P\\) defining the parts.  Picking up the next part of the definition:

> for each \\(p \in P\\), a non-empty subset \\(A_p \subset A\\)

So: each \\(p\\) - each *part* - maps to a non-empty subset of \\(A\\).  That's just what we drew in the partition diagram above.  Here's a slightly different way of drawing it, such that \\(A\\) and \\(P\\) are both shown consistently as sets:

![Mapping of people to roles](https://raw.githubusercontent.com/sfinnie/CategoryTheoryCourseNotes/master/partitions/img/people-roles-sets.png)

We can now enumerate the subsets \\(A_p \subset A\\):

* \((A_ProductManagers = {Sidd}\))
* \((A_Mathematicians = {Fiona, Aruna, Malcolm}\))
* \((A_Engineers = {Guillaume, Wendy}\))

Back to the definition:

$$ A=\bigcup_{p\in P}A_p $$

Reading this in natural language, it says \\((A\\)) is the union \\(\bigcup\\) of all subsets \\(A_p\\) for each \\(p\in P \\).  So \\(A = A_ProductManagers + A_Mathematicians + A_Engineers\\).

And so the final component of the definition:

$$\text{if }p\neq q\text{ then }A_P\cap A_Q=\emptyset$$

This is the 'disjoint', or non-overlapping clause. Translating that literally into words:

> If p isn't equal to q, then the intersection of subsets \\(A_P\\) and \\(A_Q\\) is the empty set.  

Less prosaically, \\(A_P\\) and \\(A_Q\\) don't share any members unless \\(p = q\\) (in which case \\(p\\) and \\(q\\) represent the same element).

We're back to where we started now.  \\(P\\) is a partition of \\(A\\) because:

1. \\(P\\) comprises one or more parts 
2. Each part of \\P\\) contains at least one element of \\(A\\)
3. Each element of \\(A\\) is contained in exactly one part of \\(P\\)

## Comparing Partitions

So far we've only looked at one partition of our People set.  Here's another:

![Mapping of people to roles](https://raw.githubusercontent.com/sfinnie/CategoryTheoryCourseNotes/master/partitions/img/people-locations.png)

This partitions based on location as opposed to role.  It only has 2 parts where the role-based partition had 3.  We can compare the two partions as follows:

* The Role partition is ***finer*** than the Location partition
* The Location partition is ***courser*** than the Role partition

These statements are inverses.  Formally, a partition \\(P_1\\) is finer than \\(P_2\\) if:

1. \\(P_1\\) and \\(P_2\\) partition the same set, and
2. Every part of \\(P_2\\) is a union of blocks in \\(P_1\\)

Relating that to the Location and Role Partitions:

1. *Auckland* is the union of *Engineers* and *Product Managers*
2. *Edinburgh* is the same as *Mathematicians*.

But wait: surely Edinburgh isn't a union of Location parts?  Technically it is: *Edinburgh* is the union of *Mathematicians* and the empty set \\(\emptyset\\).  THe empty set is a subset of every set by definition.

### A counter example

It's perhaps tempting to define the finer/courser relation as simply:

* A finer partition has more parts

However, that doesn't work.  Suppose Guillaume moved from Auckland to Edinburgh:

![Mapping of people to roles](https://raw.githubusercontent.com/sfinnie/CategoryTheoryCourseNotes/master/partitions/img/people-locations2.png)

We can't now relate the revised Location partition with the Role-based alternative.  There's no way to combine the *Product Manager*, *Engineer* and *Mathematician*, using the union operator, to produce the *Edinburgh* and *Auckland* parts.





