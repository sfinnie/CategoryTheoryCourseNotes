Posting this as someone who learns best from concrete examples and geometric representations, on the basis that trying to explain something is a good way to test one's understanding.  If it's inappropriate for the forum please just say.  I ask forbearance from those with more natural mathematical ability.  Corrections or comments gratefully received.

The examples below all consider the subject matter of completing tasks.  Assume order means "must be completed before": so \\(x \le y\\) means "task \\(x\\) must be completed before task \\(y\\)".  Note I've used 'arrow' in the geometric sense, not the categorical one.

## The Landscape

First, a picture:

![order Venn Diagram](https://raw.githubusercontent.com/sfinnie/CategoryTheoryCourseNotes/master/posets/img/orderVennDiagram.gif)

This says:

 * Sets are either ordered or unordered
 * All Orders are also Posets
 * All Posets are also Preorders

Why the subset relations among Preorders, Posets and Orders?  Because of the rules that they must obey.  We'll look at that below; but first, let's cover off sets without any order.

## No Order

Consider cleaning the house.  Let's assume there are 3 rooms: bathroom, bedroom and kitchen.  To clean the house, we need to clean all three rooms.  It doesn't matter what order they're cleaned in: there's no dependence.

![unordered tasks](https://raw.githubusercontent.com/sfinnie/CategoryTheoryCourseNotes/master/posets/img/unordered.png)
 
## Preorders

Preorders must obey 2 rules:

1. **reflexivity**: \\(x \le x\\)

2. **transitivity** \\(x \le y\\) and \\(y \le z\\) imply \\(x \le z\\).

As an example, consider a (very simplified) iterative approach to writing software:

![Preorder Example](https://raw.githubusercontent.com/sfinnie/CategoryTheoryCourseNotes/master/posets/img/preorder.png)

The arrows are straightforward: we must `Define Requirements` before `Write Code`, and `Write Code` before `Test Solution`. We can also combine those according to rule (2) - so `Define Requirements` before `Test Solution`.  

What about the loop?  That's OK according to rule 1.  It says any task must be "less than or equal to" itself.  `Define Requirements` equals itself, so it satisfies rule 1 (as do all the others in the loop, for the same reason).  

Note also there's no arrow connecting `Write Code` and `Write Tests`.  Again, that's fine: there's nothing in the rules to say *every* task must be related to every other.  

## Posets

Posets obey both rules for Preorders, and add a third:

1. **antisymmetry**: if \\(x \le y\\) and \\(y \le x\\) then \\(x = y\\)

Our iterative process above fails this rule.  Why?  Substitute `Define Requirements` for \\(x\\) and `Test Solution` for \\(y\\) in the antisymmetry rule.  `Define Requirements` does come before `Test Solution` so \\(x \le y\\).  `Test Solution` also comes before `Define Requirements`.  So \\(y \le x\\).  But `Define Requirements` is a different task to `Test Solution`.  So \\(x = y\\) is not true.  So the iterative process isn't antisymmetric: it's not a poset.  We can make it so by removing the loop, and creating a [waterfall process](https://en.wikipedia.org/wiki/Waterfall_model):

![Poset Example](https://raw.githubusercontent.com/sfinnie/CategoryTheoryCourseNotes/master/posets/img/poset.png)


## Orders

Orders obey all the rules for Posets, and add yet another:

1. **trichotomy**: for all \\(x,y\\) we either have \\(x\le y\\) or \\(y \le x\\).

Antisymmetry removed loops in our task ordering.  Trichotomy removes parallel paths.  Why?  Let \\(x\\) be `Write Code` and \\(y\\) be `Write Tests`.  There's no arrow, or sequence of arrows, that connect the two.  So we don't have \\(x \le y\\), nor do we have \\(y \le x\\). Trichotomy fails.

We can resolve that by linearising the process.  Let's follow [Test-Driven Development](https://en.wikipedia.org/wiki/Test-driven_development) and write tests before the code:

![Order Example](https://raw.githubusercontent.com/sfinnie/CategoryTheoryCourseNotes/master/posets/img/sequence.png)




