# EXP 52 - Doubly Linked List: Search an Element

This Python program demonstrates the implementation of a **Doubly Linked List** where you can insert elements at both the beginning and the end of the list. Additionally, it allows you to search for a specific element in the list.

---

##  Aim

To write a Python program that:
- Implements a **Doubly Linked List** with functions to insert elements at the beginning and the end of the list.
- Implements a search function to check if a given element exists in the list.


##  Algorithm

1. **Step 1:** Define a class `Nodeq` with:
   - `data` to store the node's value.
   - `next` to store the reference to the next node.
   - `prev` to store the reference to the previous node.

2. **Step 2:** Define a class `DoublyLinkedList` with:
   - `head` to point to the first node.

3. **Step 3:** In the `DoublyLinkedList` class, define methods:
   - `insert_beginning(data)` to insert a node at the beginning.
   - `insert_end(data)` to insert a node at the end.
   - `search(data)` to search for an element in the list.

4. **Step 4:** Create an instance of `DoublyLinkedList`.
   - Insert elements at the beginning and end.
   - Search for specific elements.



##  Program
```
class Nodeq: 
    def __init__(self, data): 
        self.data = data 
        self.next = None
        self.prev = None

class DoublyLinkedList: 

    def __init__(self): 
        self.head = None
    def insert_beginning(self,data):
        new_node = Nodeq(data)  
        if(self.head == None): 
            self.head = new_node     
            return    
        self.head.prev = new_node   
        new_node.next = self.head   
        self.head = new_node    

    def insert_end(self, new_data): 
        new_node = Nodeq(new_data) 
        if self.head is None: 
            new_node.prev = None
            self.head = new_node 
            return 
        last = self.head 
        while last.next: 
            last = last.next
        last.next = new_node 
        new_node.prev = last 
    def search(self,data):
        n=self.head
        while n is not None:
            if n.data == data:
                break
            n=n.next
        if n == None:
            print("The given data doesnot exist:")
            return False
        return True
        

Dllist = DoublyLinkedList() 
Dllist.insert_beginning(2)
Dllist.insert_end(0)
Dllist.insert_end(1)
print(Dllist.search(0)) 
print(Dllist.search(3))
```
## Sample Output
![image](https://github.com/user-attachments/assets/77fe03f9-f5e7-47a6-8412-193310c97c35)

## Result
Thus, the program is verified successfully.
