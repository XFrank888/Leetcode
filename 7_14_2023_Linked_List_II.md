# 24. Swap Nodes in Pairs

```
class Solution {
public:
    ListNode* swapPairs(ListNode* head) {
        ListNode* dummy = new ListNode(0);
        dummy->next = head;
        ListNode* cur = dummy;
        while(cur->next != nullptr && cur->next->next != nullptr){
            ListNode* tmp = cur->next;
            ListNode* tmp1 = cur->next->next->next;

            cur->next = cur->next->next;
            cur->next->next = tmp;
            cur->next->next->next = tmp1;

            cur = cur->next->next;
        }
        return dummy->next;
    }
};

```

# 19. Remove Nth Node From End of List

```
class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        ListNode* dummy = new ListNode(0);
        dummy->next = head;
        ListNode* slow = dummy;
        ListNode* fast = dummy;
        while(n-- && fast != NULL){
            fast = fast->next;
        }
        fast = fast->next; //n+1
        while(fast != NULL){
            fast = fast->next;
            slow = slow->next;
        }
        slow->next = slow->next->next;

        return dummy->next;
    }

};

```

# 160. Intersection of Two Linked Lists

```
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        ListNode* curA = headA;
        ListNode* curB = headB;
        int lenA = 0, lenB = 0;
        while(curA != NULL){
            lenA++;
            curA = curA->next;
        }
        while(curB != NULL){
            lenB++;
            curB = curB->next;
        }
        curA = headA;
        curB = headB;
        if (lenB > lenA) {
            swap (lenA, lenB);
            swap (curA, curB);
        }
        int diff = lenA - lenB;
        while (diff--) {
            curA = curA->next;
        }
        while (curA != NULL) {
            if (curA == curB) {
                return curA;
            }
            curA = curA->next;
            curB = curB->next;
        }
        return NULL;
    }
};
```

# 142. Linked List Cycle II
