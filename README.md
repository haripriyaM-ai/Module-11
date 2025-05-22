## MODULE - 11
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

---

# EXP 52 - Doubly Linked List: Search an Element

This Python program demonstrates the implementation of a **Doubly Linked List** where you can insert elements at both the beginning and the end of the list. Additionally, it allows you to search for a specific element in the list.


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

---

# EXP 53 - Singly Linked List : Find the Middle Node of a Singly Linked List Using Recursion

This Python program demonstrates how to find the middle node of a singly linked list using recursion. The program calculates the middle element by utilizing two pointers, with one pointer moving one step at a time (slow) and the other moving two steps at a time (fast). When the fast pointer reaches the end of the list, the slow pointer will be at the middle node.


##  Aim

To write a Python program that:
- Creates a singly linked list.
- Uses recursion to find the middle node of the list.
- In case of an even number of nodes, it returns the second middle element.

##  Algorithm

1. **Node Class**: 
   - Define a `Node` class to represent each node in the singly linked list. Each node has two attributes: `data` and `next`.
   
2. **LinkedList Class**:
   - Define a `LinkedList` class that manages the linked list with methods to:
     - `append(data)`: Add a new node to the end of the list.
     - `get_middle_recursive(slow, fast)`: A recursive helper function to find the middle node using two pointers (slow and fast).
     - `find_middle()`: A method to call the recursive function and return the middle node's data.

3. **Input**:
   - First, the program reads an integer `n`, representing the number of elements in the linked list.
   - Then, it reads `n` space-separated integers to form the linked list.

4. **Recursive Middle Finding**:
   - The `get_middle_recursive` method uses two pointers to traverse the list:
     - The `slow` pointer moves one step at a time.
     - The `fast` pointer moves two steps at a time.
   - When the `fast` pointer reaches the end, the `slow` pointer will be at the middle node.

5. **Output**:
   - The program prints the middle element. If the list has an even number of nodes, it returns the second middle element.



## Program
```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        temp = self.head
        while temp.next:
            temp = temp.next
        temp.next = new_node

    def get_middle_recursive(self, slow, fast):
        if fast is None or fast.next is None:
            return slow
        return self.get_middle_recursive(slow.next, fast.next.next)

    def find_middle(self):
        if not self.head:
            return None
        middle_node = self.get_middle_recursive(self.head, self.head)
        return middle_node.data

n = int(input())
values = list(map(int, input().split()))

ll = LinkedList()
for val in values:
    ll.append(val)

print(ll.find_middle())
```
## Sample Input & Output
![image](https://github.com/user-attachments/assets/139e9c65-552f-494a-8acb-ab764b6f271b)

![image](https://github.com/user-attachments/assets/3753d1d1-cf65-43e3-a173-b5da992eae19)


## Result
Thus, the program is verified successfully.

---

#  EXP 54 : Singly Linked List-To Search an Element in a Linked List

This project contains a simple implementation of a **singly linked list** in Python, allowing insertion and searching of elements.


##  Aim

To write a Python program to search for a given element in a singly linked list using object-oriented programming principles.


##  Algorithm

1. **Define a Node class** with `data` and `next` attributes.
2. **Define a LinkedList class** with:
   - A `head` pointer initialized to `None`.
   - A `push()` method to add elements at the beginning.
   - A `search()` method to check whether a given value exists.
3. Create a `LinkedList` instance.
4. Insert the elements **10, 30, 11, 21, 14** using `push()` (which results in reverse order).
5. Read an integer input from the user.
6. Use `search()` to check if the element exists in the list.
7. Output **"Yes"** if found, else **"No"**.


##  Program
```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
 
class LinkedList:
    def __init__(self):
        self.head = None
 
    def push(self, new_data):
        new_node = Node(new_data)
        new_node.next = self.head
        self.head = new_node
 
    def search(self, x):
        current = self.head
        while current != None:
            if current.data == x:
                return True
             
            current = current.next
        return False
 
llist = LinkedList()
 
llist.push(10);
llist.push(30);
llist.push(11);
llist.push(21);
llist.push(14);

data = int(input())
if llist.search(data):
    print("Yes")
else:
    print("No")
```

## Sample Output
![image](https://github.com/user-attachments/assets/6e172e13-1d98-4e85-9b65-0f583ef5d48a)

## Result
Thus, the program is verified successfully.

---

# EXP 55 - Singly Linked List: Add Element at the Start

This Python program demonstrates the implementation of a **Singly Linked List** where a new element can be added at the **start** of the list.


## Aim

To write a Python program that adds a **new element** at the **start** of a singly linked list. The program implements a `push_front` method that inserts an element at the front of the list, followed by a method to print the list.



##  Algorithm

1. **Step 1:** Define a class `Node` with:
   - `data` to store the node's value.
   - `next` to store the reference to the next node.
   
2. **Step 2:** Define a class `LinkedList` with:
   - `head` to point to the first node.
   
3. **Step 3:** In the `LinkedList` class, define a method `push_front(newElement)`:
   - Create a new node with `newElement`.
   - Set the new node's next pointer to the current head node.
   - Set the head to the new node.

4. **Step 4:** Define a method `PrintList()` to display the list:
   - Print the elements of the list or display "The list is empty." if the list is empty.

5. **Step 5:** Instantiate a `LinkedList` object, `MyList`, and add elements at the start using the `push_front()` method.

6. **Step 6:** Call the `PrintList()` method to display the list.


## Program
```
class Node:
  def __init__(self, data):
    self.data = data
    self.next = None

class LinkedList:
  def __init__(self):
    self.head = None

  def push_front(self, newElement):
    newNode = Node(newElement)
    newNode.next = self.head 
    self.head = newNode   

  def PrintList(self):
    temp = self.head
    if(temp != None):
      print("The list contains:", end=" ")
      while (temp != None):
        print(temp.data, end=" ")
        temp = temp.next
      print()
    else:
      print("The list is empty.")

MyList = LinkedList()

MyList.push_front(10)
MyList.push_front(20)
MyList.push_front(30)
MyList.PrintList()
```

## Sample Output
![image](https://github.com/user-attachments/assets/bf14cf59-dbbf-4c2d-9c16-e7c8f88394c3)

## Result
Thus, the program is verified successfully.
