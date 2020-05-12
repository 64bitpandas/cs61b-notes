# Minimax Algorithm

## Game Trees

The Minimax algorithm is often used for making AI's for turn-based games. It relies on the use of a type of **game tree,** which maps out all of the possible moves that players can make.

\*\*\*\*

## **Alpha-Beta Pruning** 

## A Story of Minimax Nodes: An Intuitive Understanding

Minimax is quite difficult to understand just by studying its rules. In order to really know what's going on, we need to know why we have all of these rules and what everything represents. Here's how I think about it:

![](../.gitbook/assets/image%20%2879%29.png)

![](../.gitbook/assets/image%20%2845%29.png)

![](../.gitbook/assets/image%20%288%29.png)

![](../.gitbook/assets/image%20%2876%29.png)

![](../.gitbook/assets/image%20%2844%29.png)

![](../.gitbook/assets/image%20%2830%29.png)

![](../.gitbook/assets/image%20%2822%29.png)

![](../.gitbook/assets/image%20%2818%29.png)

## Practice Problems

{% tabs %}
{% tab title="Question 1" %}
Here's a tree. Figure out:

* What values each of the nodes report
* Which branches are pruned
* The alpha and beta values at each visited node

![](../.gitbook/assets/image%20%2881%29.png)
{% endtab %}

{% tab title="Q1 Answer" %}
Here's my answer! The green arrows denote the order in which the nodes are visited. Note that the branches are pruned every time **alpha is greater than beta.** 

![](../.gitbook/assets/image%20%2894%29.png)
{% endtab %}
{% endtabs %}

This was just an ordinary problem and **might not be enough to ensure that you fully understand minimax trees**! Here are some checks you can do to ensure that your understanding is strong:

* Figure out what the tree returns and prunes intuitively _without_ finding any alpha or beta values.
* Make your own minimax tree problem like the one above and solve it. Are you confident in your answer \(since no answer key exists\)?
* Make a minimax tree that's missing some values, and try to find all possible values that fit in there such that the branch will become pruned.
* Implement the minimax algorithm in Java.

