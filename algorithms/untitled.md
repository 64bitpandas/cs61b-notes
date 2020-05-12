# Minimax Algorithm

## Game Trees

The Minimax algorithm is often used for making AI's for turn-based games. It relies on the use of a type of **game tree,** which maps out all of the possible moves that players can make.

In the tree, there are two types of nodes: **maximizing nodes** and **minimizing nodes.** The max-nodes represent **you**- you want to make your position as advantageous as possible \(maximizing your score\). The min-nodes represent **your opponent-** they want to make you do as poorly as possible \(minimizing your score\).

The scores themselves are generated using a **heuristic function** that assesses the current game state and returns a number based on which player has an advantage, and to what extent. **This heuristic is totally up to you to figure out and has very few constraints.** There are a couple rules, however:

* Heuristic functions must return **positive values** if you're doing better than your opponent, and **negative values** if your opponent is doing better.
* Heuristic functions must return the **maximum value** for a state in which you won, and the **minimum value** for a state in which your opponent won.

In most games, you and your opponent will take turns, so each layer will alternate node type, like this:

![](../.gitbook/assets/image%20%2836%29.png)

In most games, this tree will spiral out of control because there are far too many nodes to possibly analyze \(maybe even an infinite number\)! Therefore, we need to set a **depth** to stop searching and compute a heuristic. For example, if the depth is **3**, it'll look something like this:

![](../.gitbook/assets/image%20%2866%29.png)

Now that the tree has bottomed out at the heuristic layer, we can start going back up to figure out which move we should make! The rules are simple: **min-nodes take the smallest of the values** while **max-nodes take the largest of the values.** Here's the first layer, for example:

![](../.gitbook/assets/image%20%2844%29.png)

Here's the entire tree filled out:

![](../.gitbook/assets/image%20%2841%29.png)

## **Alpha-Beta Pruning** 

We can make our tree **even more efficient** by simply ignoring all of the branches that will lead to results that will **never be chosen.** Here, we'll assume that **both players play optimally** \(choose the best move for their particular node\).

In the example above, we can see that the 7 on the right will **never need to be visited** because we **already know that 5 will be chosen.** 

In order to do this, we'll introduce two additional parameters, **alpha** and **beta.** Here are the rules:

* **Alpha** starts out as **negative infinity** and is set by **max nodes** to their current value.
* **Beta** starts out as **positive infinity** and is set by **min nodes** to their current value.
* A node **passes its alpha and beta values** onto its children.
* If **alpha is greater than beta,** the branch will be **pruned** \(no longer visited\).

This is a pretty tough concept to grasp, and that's why I've illustrated how it works below. Read on!

## A Story of Minimax Nodes: An Intuitive Understanding

Minimax is quite difficult to understand just by studying its rules. In order to really know what's going on, we need to know why we have all of these rules and what everything represents. Here's how I think about it:

![](../.gitbook/assets/image%20%2888%29.png)

![](../.gitbook/assets/image%20%2852%29.png)

![](../.gitbook/assets/image%20%289%29.png)

![](../.gitbook/assets/image%20%2885%29.png)

![](../.gitbook/assets/image%20%2851%29.png)

![](../.gitbook/assets/image%20%2831%29.png)

![](../.gitbook/assets/image%20%2823%29.png)

![](../.gitbook/assets/image%20%2819%29.png)

## Practice Problems

{% tabs %}
{% tab title="Question 1" %}
Here's a tree. Figure out:

* What values each of the nodes report
* Which branches are pruned
* The alpha and beta values at each visited node

![](../.gitbook/assets/image%20%2890%29.png)
{% endtab %}

{% tab title="Q1 Answer" %}
Here's my answer! The green arrows denote the order in which the nodes are visited. Note that the branches are pruned every time **alpha is greater than beta.** 

![](../.gitbook/assets/image%20%28106%29.png)
{% endtab %}
{% endtabs %}

This was just an ordinary problem and **might not be enough to ensure that you fully understand minimax trees**! Here are some checks you can do to ensure that your understanding is strong:

* Figure out what the tree returns and prunes intuitively _without_ finding any alpha or beta values.
* Make your own minimax tree problem like the one above and solve it. Are you confident in your answer \(since no answer key exists\)?
* Make a minimax tree that's missing some values, and try to find all possible values that fit in there such that the branch will become pruned.
* Implement the minimax algorithm in Java.

