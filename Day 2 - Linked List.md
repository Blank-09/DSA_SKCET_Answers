# **Day 2 - Linked List Answers**

## **Question 1**

Write a program to inset a node at the beginning of the doubly linked list.

### **Answer**

```cpp
#include <iostream>
using namespace std;

struct Node {
    int val;
    Node *prev;
    Node *next;
    Node(int val) { this->val = val; }
} *head = NULL;


void insertBefore(int val) {
    Node *newNode = new Node(val);

    if (head) {
        head->prev = newNode;
        newNode->next = head;
    }

    head = newNode;
}


void display() {
    Node *temp = head;
    
    while (temp) {
        cout << temp->val << " ";
        temp = temp->next;
    }
}

int main() {
    int n, t;
    cin >> n;
    
    for (int i = 0; i < n; i++) {
        cin >> t;
        insertBefore(t);
    }
    
    display();
}
```

---

## **Question 2**

Write a C++ program to add a node to the beginning of a circular linked list with user input

### **Answer**

```cpp
#include <iostream>
using namespace std;

struct Node {
    int val;
    Node *next;
    Node(int val) { this->val = val; }
} *head = NULL, *tail = NULL;


void insertBefore(int val) {
    Node *newNode = new Node(val);

    if (!head) {
        tail = head = newNode;
        tail->next = head;
    }
    
    else {
        tail->next = newNode;
        newNode->next = head;
        head = newNode;
    }
}


void display() {
    Node *temp = head;
    
    while (temp->next != head) {
        cout << temp->val << " ";
        temp = temp->next;
    }
    cout << temp->val << endl; 
}

int main() {
    int n, t;
    cin >> n;
    
    for (int i = 0; i < n; i++) {
        cin >> t;
        insertBefore(t);
    }
    
    display();
    
    cin >> t;
    insertBefore(t);
    display();
}
```

---

## **Question 3**

Write a program to delete a node from the end of a doubly linked list.

### **Answer**

```cpp
#include <iostream>
using namespace std;

struct Node {
    int val;
    Node *prev;
    Node *next;
    Node(int val) { this->val = val; }
} *head = NULL, *tail = NULL;


void insertBack(int val) {
    Node *newNode = new Node(val);

    if (!head) {
        head = tail = newNode;
        return;
    }

    newNode->prev = tail;
    tail->next = newNode;
    tail = newNode;
}

void display() {
    Node *temp = head;
    
    while (temp) {
        cout << temp->val << " ";
        temp = temp->next;
    }
    cout << endl;
}

void deleteLastNode() {
    Node *temp = tail->prev;
    temp->next = NULL;
    tail->prev = NULL;
    tail = temp;
}

int main() {
    int n, t;
    cin >> n;
    
    while (n--) {
        cin >> t;
        insertBack(t);
    }
    display();
    
    cin >> n;
    while (n--) {
        deleteLastNode();
    }
    display();
    
    return 0;
}
```

---

## **Question 4**

Write a program to insert the node at the end of the doubly inked list.

### **Answer**

```cpp
#include <iostream>
using namespace std;

struct Node {
    int val;
    Node *prev;
    Node *next;
    Node(int val) { this->val = val; }
} *head = NULL, *tail = NULL;


void insertBack(int val) {
    Node *newNode = new Node(val);

    if (!head) {
        head = tail = newNode;
        return;
    }

    newNode->prev = tail;
    tail->next = newNode;
    tail = newNode;
}

void display() {
    Node *temp = head;
    
    while (temp) {
        cout << temp->val << " ";
        temp = temp->next;
    }
    cout << endl;
}

int main() {
    int n, t;
    cin >> n;
    
    while (n--) {
        cin >> t;
        insertBack(t);
    }
    display();
    
    return 0;
}
```

---

## **Question 5**

Write a program to implement a doubly linked list and display both direction.

### **Answer**

```cpp
#include <iostream>
using namespace std;

struct Node {
    int val;
    Node *prev;
    Node *next;
    Node(int val) { this->val = val; }
} *head = NULL, *tail = NULL;


void insertBefore(int val) {
    Node *newNode = new Node(val);

    if (!head) {
        tail = head = newNode;
        return;
    }
    
    head->prev = newNode;
    newNode->next = head;
    head = newNode;
}


void displayForward() {
    Node *temp = head;
    
    cout << "Doubly linked list forwards: ";
    while (temp) {
        cout << temp->val << " ";
        temp = temp->next;
    }
    cout << endl;
}

void displayBackward() {
    Node *temp = tail;
    
    cout << "Doubly linked list backwards: ";
    while (temp) {
        cout << temp->val << " ";
        temp = temp->prev;
    }
}

int main() {
    int n, t;
    cin >> n;
    
    for (int i = 0; i < n; i++) {
        cin >> t;
        insertBefore(t);
    }
    
    displayForward();
    displayBackward();
}
```
