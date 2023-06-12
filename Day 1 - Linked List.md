# **Day 1 - Linked List Answers**

## **Question 1**

Write the program to delete the node at the end of the singly linked list.

### **Answer**

```cpp
#include <iostream>
using namespace std;

struct Node {
    int val;
    struct Node *next;
    Node(int val) { this->val = val; };
} *head = NULL;

void insertBefore(int val) {
    Node *newNode = new Node(val);

    if (!head) {
        head = newNode;
    }

    else {
        newNode->next = head;
        head = newNode;
    }
}

void display(Node *head) {
    Node *temp = head;
    while (temp) {
        cout << temp->val << " ";
        temp = temp->next;
    }
    cout << endl;
}

void deleteNode(Node *head, int n) {
    Node *temp = head;
    while (n--) {
        temp = temp->next;
    }

    Node *prev = head;
    while (temp->next) {
        prev = prev->next;
        temp = temp->next;
    }
    prev->next = NULL;
}

int main() {
    int n, t;
    cin >> n;

    for (int i = 0; i < n; i++) {
        cin >> t;
        insertBefore(t);
    }
    cin >> t;

    display(head);
    deleteNode(head, t);
    display(head);
}
```

---

## **Question 2**

Write a program to create a singly linked list and display the added elements.

> Note : Insert the elements in the end of the list.

### **Answer**

```cpp
#include <iostream>
using namespace std;

struct Node {
    int val;
    struct Node *next;
    Node(int val) { this->val = val; };
} *head = NULL;

void insert(int val) {
    Node *newNode = new Node(val);

    if (!head) {
        head = newNode;
    }

    else {
        Node *temp = head;
        while (temp->next) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
}

void display(Node *head) {
    Node *temp = head;
    while (temp) {
        cout << temp->val << " ";
        temp = temp->next;
    }
}

int main() {
    int n,t;
    cin >> n;

    for (int i = 0; i < n; i++) {
        cin >> t;
        insert(t);
    }

    display(head);
}
```

---

## **Question 3**

Write a program to create a singly linked list and display the added elements.

> Note : Insert the elements in the beginning of the list.

### **Answer**

```cpp
#include <iostream>
using namespace std;

struct Node {
    int val;
    struct Node *next;
    Node(int val) { this->val = val; };
} *head = NULL;

void insertBefore(int val) {
    Node *newNode = new Node(val);

    if (!head) {
        head = newNode;
    }

    else {
        newNode->next = head;
        head = newNode;
    }
}

void display(Node *head) {
    Node *temp = head;
    while (temp) {
        cout << temp->val << " ";
        temp = temp->next;
    }
}

int main() {
    int n,t;
    cin >> n;

    for (int i = 0; i < n; i++) {
        cin >> t;
        insertBefore(t);
    }

    display(head);
}
```

---

## **Question 4**

Write the code to inserting the elements at the beginning and display the singly linked list elements.

### **Answer**

```cpp
#include <iostream>
using namespace std;

struct Node {
    int val;
    struct Node *next;
    Node(int val) { this->val = val; };
} *head = NULL;

void insert(int val) {
    Node *newNode = new Node(val);

    if (!head) {
        head = newNode;
    }

    else {
        newNode->next = head;
        head = newNode;
    }
}

void display(Node *head) {
    Node *temp = head;
    while (temp) {
        cout << temp->val << " ";
        temp = temp->next;
    }
}

int main() {
    int n,t;
    cin >> n;

    for (int i = 0; i < n; i++) {
        cin >> t;
        insert(t);
    }

    display(head);
}
```

---

## **Question 5**

Write a program to reverse all the values in the linked list and swap the nodes a and b of linked list rather than swapping the field from the nodes.

### **Answer**

```cpp
#include <iostream>
using namespace std;

struct Node {
    int val;
    struct Node *next;
    Node(int val) { this->val = val; };
} *head = NULL;

void insertBefore(int val) {
    Node *newNode = new Node(val);

    if (!head) {
        head = newNode;
    }

    else {
        newNode->next = head;
        head = newNode;
    }
}

void display(Node *head) {
    Node *temp = head;
    while (temp) {
        cout << temp->val << " ";
        temp = temp->next;
    }
}

void swap(Node *head, int a, int b) {
    Node *temp = head;
    while (temp) {
        if (temp->val == a)
            temp->val = b;
        else if (temp->val == b)
            temp->val = a;

        temp = temp->next;
    }
}

int main() {
    int n,t;
    cin >> n;

    for (int i = 0; i < n; i++) {
        cin >> t;
        insertBefore(t);
    }

    int a, b;
    cin >> a >> b;

    swap(head, a, b);
    display(head);
}
```
