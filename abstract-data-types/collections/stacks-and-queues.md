# Stacks and Queues

Stacks and queues are two very common data structures used for a variety of applications from [CPU processes](https://www.tutorialspoint.com/operating_system/os_processes.htm) to [finding shortest paths using Dijkstra's Algorithm](../../algorithms/shortest-paths/dijkstras-algorithm.md). Fundamentally, they are very similar in structure and **only differ by the order in which items are popped from them**.

## Pushing and Popping

### Pushing

Adding an item to a stack or queue is called **pushing**. This will either put the item on the **top** of a stack or in the **back** of a queue.

You can think of a stack like a pile of pizza boxes- the one on the top is the first one you have to take off if you need one!

![](../../.gitbook/assets/image%20%286%29.png)

On the other hand, you can think of a queue like lining up for a ride at Disneyland. The first person who gets in line will get to go first, and the last person who gets in will go last. \(Of course, we all know people cut and stuff- see [Priority Queues](stacks-and-queues.md#priority-queues) to see how this is better handled.\)

![those lines tho](../../.gitbook/assets/image%20%283%29.png)

### Popping

Taking an item out of a stack or queue is called **popping.**

Stacks are **last in, first out \(LIFO\).** That means the last item that you put in will be the first item that gets popped.

Queues are **first in, first out \(FIFO\).** That means that the first item that you put in will be the first item that gets popped.

## Priority Queues

Let's say you bought a VIP pass and get to cut to the front of the line for your favorite Disneyland ride! Well, a normal Queue won't be able to model this behavior since it puts everything in the back by default.

A priority queue will solve this design need by introducing a new **priority** **tracking system** for each item in the queue! **If an item has a lower priority number, it will get to go first.** 

![gotta grab those fastpasses yEEt &#x1F39F;](../../.gitbook/assets/image%20%2857%29.png)

