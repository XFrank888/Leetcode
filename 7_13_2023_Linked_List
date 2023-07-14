# Leetcode 203 Remove Linked List Elements

```
class Solution {
public:
    ListNode* removeElements(ListNode* head, int val) {
        ListNode* dummy = new ListNode(0);
        dummy->next = head;
        ListNode* curr = dummy;
        while(curr->next != NULL){
            if(curr->next->val == val){
                ListNode* temp = curr -> next;
                curr->next = curr->next->next;
                delete temp;
            } else{
                curr = curr->next;
            }
        }
        head = dummy->next;
        delete dummy;
        return head;
    }
};
```

# Leetcode 707. Design Linked List

```
class MyLinkedList {
public:
    struct LinkedList{
        int val;
        LinkedList* next;
        LinkedList(int val): val(val), next(nullptr){}
    };

    MyLinkedList() {
        dummy = new LinkedList(0);
        size = 0;
    }
    
    int get(int index) {
        if(index > size-1 || index < 0){
            return -1;
        }
        LinkedList* curr = dummy->next;
        while(index--){
            curr = curr->next;
        }
        return curr->val;
    }
    
    void addAtHead(int val) {
        LinkedList* newNode = new LinkedList(val);
        newNode->next = dummy->next;
        dummy->next = newNode;
        size++;
    }
    
    void addAtTail(int val) {
        LinkedList* newNode = new LinkedList(val);
        LinkedList* curr = dummy;
        while(curr->next != nullptr){
            curr = curr -> next;
        }
        curr->next = newNode;
        size++;
    }
    
    void addAtIndex(int index, int val) {
        if(index > size) return;
        if(index < 0) index = 0;
        LinkedList* newNode = new LinkedList(val);
        LinkedList* curr = dummy;
        while(index--){
            curr = curr->next;
        }
        newNode->next = curr->next;
        curr->next = newNode;
        size++;
    }
    
    void deleteAtIndex(int index) {
        if(index >= size || index < 0){
            return;
        }
        LinkedList* curr = dummy;
        while(index--){
            curr = curr->next;
        }
        LinkedList* temp = curr->next;
        curr->next = curr->next->next;
        delete temp;
        temp = nullptr;
        size--;
    }

private: 
    int size;
    LinkedList* dummy;
};
```

# Leetcode 206. Reverse Linked List

```
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode* curr = head;
        ListNode* prev = NULL;
        ListNode* temp = NULL;
        while(curr != NULL){
            temp = curr->next;
            curr->next = prev;
            prev = curr;
            curr = temp;
        }
        return prev;
    }
};
```

```
class Solution {
public:
    ListNode* reverse(ListNode* prev, ListNode* curr){
        if(curr == NULL){
            return prev;
        }
        ListNode* temp = curr->next;
        curr->next = prev;
        return reverse(curr, temp);
    }

    ListNode* reverseList(ListNode* head) {
        return reverse(NULL, head);
    }
};
```
