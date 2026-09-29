# Leetcode_Day59
# Day 59 — Intersection of Two Linked Lists

## 🧩 Problem

Given the heads of two singly linked lists, find the node where the two linked lists intersect.

If the two linked lists do not intersect, return `null`.

The important point is that intersection means both lists point to the **same node**, not just nodes containing the same value.

---

## 💡 Approach

For this problem, I used two stacks:

1. Traverse Linked List A and push every node into Stack 1.
2. Traverse Linked List B and push every node into Stack 2.
3. Compare the nodes from the top of both stacks.
4. If both top nodes refer to the same node, pop them and continue.
5. Keep updating the intersection node.
6. When the nodes are different, stop.
7. Return the last common node found.

Since the common part of two intersecting linked lists is a shared suffix, comparing nodes from the end helps us find the first intersection point.

### Important

We compare **node references**, not node values.

Two different nodes can contain the same value, but they are not an intersection.

---

## 🔍 Example

```text
List A:  a1 → a2 ──→ c1 → c2 → c3
                     ↑
List B:  b1 → b2 → b3

The intersection starts at c1.

Both lists eventually point to the exact same nodes:

c1 → c2 → c3

So the answer is c1.

⏱️ Complexity
Time Complexity: O(n + m)
Space Complexity: O(n + m)

Where n and m are the lengths of the two linked lists.

🧠 What I Learned

Today's problem helped me understand the difference between comparing values and comparing references.

In linked lists, two nodes having the same value does not mean they are the same node.

For intersection problems, the actual node reference matters.

I also learned how stacks can be used to work backwards through a linked list even though a singly linked list normally only allows forward traversal.

🎯 Takeaway

Sometimes the easiest way to solve a problem is to change the direction in which you look at it.

Instead of trying to find the intersection from the beginning, I used a stack to compare the lists from the end.

Small changes in perspective can make a confusing problem much easier.
