# EXP 51 - Doubly Linked List: Insert Elements at the End of a Doubly Linked List

This Python program demonstrates the creation and manipulation of a **Doubly Linked List** where elements can be inserted at the **end** of the list. The program also provides a method to traverse the list and display the elements.



##  Aim

To write a Python program that:
- Implements a **Doubly Linked List**.
- Allows insertion of elements at the end of the list.
- Provides functionality to traverse the list and display its elements.



##  Algorithm

1. **Step 1:** Define a class `Node` to represent each node in the doubly linked list with attributes:
   - `item` for storing the data of the node.
   - `next` for storing the reference to the next node.
   - `prev` for storing the reference to the previous node.

2. **Step 2:** Define a class `DoublyLinkedList` with:
   - `head` to point to the first node of the list.

3. **Step 3:** Define methods in the `DoublyLinkedList` class:
   - `insert_in_emptylist(data)` to insert an element when the list is empty.
   - `insert_at_end(data)` to insert elements at the end of the list.
   - `traverse_list()` to traverse the list and print the elements.

4. **Step 4:** Create an instance of `DoublyLinkedList` and use the `insert_at_end()` method to insert elements into the list.

5. **Step 5:** Use the `traverse_list()` method to print the elements of the list.



## Program
```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None

class DoublyLinkedList:
    def __init__(self):
        self.head = None
        
    def insert_in_emptylist(self, new_data):
        new_node = Node(new_data) 
        new_node.next = self.head 
        if self.head != None: 
            self.head.prev = new_node 
            self.head = new_node 
            new_node.prev = None
        else: 
            self.head = new_node
            self.tail = new_node
            new_node.prev = None 
    
      
    def insert_end(self, data):
        new_node = Node(data)
        if self.head is None:
            self.head = new_node
            return
        temp = self.head
        while temp.next:
            temp = temp.next
        temp.next = new_node
        new_node.prev = temp
        return

    def display_list(self, node):
        while node:
            print(node.data, end="->")
            last = node
            node = node.next

d_linked_list = DoublyLinkedList()

d_linked_list.insert_in_emptylist(6)
d_linked_list.insert_end(11)
d_linked_list.insert_end(15)
d_linked_list.insert_end(1)
d_linked_list.insert_end(5)
d_linked_list.insert_end(9)

d_linked_list.display_list(d_linked_list.head)
```
## Sample Output
![image](https://github.com/user-attachments/assets/65d22136-37fe-4fe1-af9a-34988e69513b)

## Result
Thus, the program is verified successfully.
