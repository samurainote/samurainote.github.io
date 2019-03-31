---
title:  "Data Structures: Linked-Lists"
date:   2019-3-25
layout: single
author_profile: true
comments: true
tags:
---

![](/pics/keras/ll.jpeg)

**Type of Data Manipulation**

Linked-Listsは、Data Structureのうち反復的（Iterative）構造をもつ.

1. Iterative　反復的
2. Recursive　再帰的

**Data Manipulation Speed Comparison**

| Query |Linked list |Array normal |Array sorted|BST         |
|-------|:-----------|:---------- -|:-----------|:-----------|
|SEARCH |O(n)        |O(n)         |O(logn)     |O(logn)     |
|INSERT |O(1)        |O(1)         |O(n)        |O(logn)     |
|REMOVE |O(n)        |O(n)         |O(n)        |O(logn)     |

**Queries of Linked-Lists**

- Queries
  1. 追加 insert()
  2. 削除 remove()
  3. 検索 search()
  4. 更新 update()

**Pros/Cons of Linked-Lists**

- When to use:
  - Frequent insert / delete operations on elements in the array without requiring random access to the elements in the array

- Pros
  -	Insertions and deletions are easier than for contiguous (array) lists
  -	Scalability: Overflow can never occur unless the memory is actually full
  -	With large records, moving pointers is easier and faster than moving the items themselves

- Cons
  -	Linked lists do not allow random access
  -	Time must be spent traversing and changing the pointers
  -	The pointers require extra space

**Components of Linked-Lists**

- Each Node has:
  1. Data
  2. Pointer

- Each List has:
  1. Head
  2. Tail

**Types of Linked-Lists**

![](/pics/keras/pp.jpg)

- Singly-linked list
- Circularly-linked list
- Doubly-linked list

**Code for Linked-Lists**

以下二つのクラスを用意する.

1. 連結リストにおけるノードの構造を表現するクラス
2. 連結リストの構造や処理を表現するクラス

3. 実際にクエリを投げる

## 1. Node: 連結リストにおけるノードの構造を表現するクラス

```python
class linkedListNode(object):

    def __init__(self, d, n = None):
        self.data = d
        self.next_node = n

    def get_next(self):
        return self.next_node

    def set_next(self, n):
        self.next_node = n

    def get_data(self):
        return self.data

    def set_data(self, d):
        self.data = d
```

## 2. 連結リストの構造や処理を表現するクラス

```python
class SinglyLinkedList(object):
    # Two instance variable: root&size
    def __init__(self, r = None):
        self.root = r
        self.size = 0

    def get_size(self):
        return self.size

    def add(self, d):
        new_node = Node (d, self.root)
        self.root = new_node
        self.size += 1

    def remove(self, d):
        this_node = self.root
        prev_node = None

        while this_node:
            if this_node.get_data() == d:
                if prev_node:
                    prev_node.set_next(this_node.get_next())
                else:
                    self.root = this_node.get_next()
                self.size -= 1
                return True		# data removed
            else:
                prev_node = this_node
                this_node = this_node.get_next()
        return False  # data not found

    def find(self, d):
        this_node = self.root
        while this_node:
            if this_node.get_data() == d:
                return d
            else:
                this_node = this_node.get_next()
        return None
```

### 3. 実際にクエリを投げる

- get_size()
- find(data)
- add(data)
- remove(data)

```python

# ノードの作成
node1 = linkedListNode("10")
node2 = linkedListNode("6")
node3 = linkedListNode("3")
# 連結
node1.set_next(node2)
node2.set_next(node3)



```

## References

- [Tutorialspoint](https://www.tutorialspoint.com/python/python_linked_lists.htm)
- [Implementing a Singly Linked List in Python](https://www.codefellows.org/blog/implementing-a-singly-linked-list-in-python/)
- [Python interview question guide: how to code a linked list](https://medium.freecodecamp.org/python-interview-question-guide-how-to-code-a-linked-list-fd77cbbd367d)
