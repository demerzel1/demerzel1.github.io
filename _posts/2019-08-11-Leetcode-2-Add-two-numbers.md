---
layout:     post
title:      LeetCode 2 Add two numbers
subtitle:    "LeetCode 2 题解"
date:       2019-08-11
author:     demerzel
header-img: img/post-bg-2015.jpg
catalog: true
tags:
    - LeetCode
    - C++
---

# LeetCode 2 Add Two Numbers
## Problem
You are given two**non-empty**linked lists representing two non-negative integers. The digits are stored in**reverse order**and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.
You may assume the two numbers do not contain any leading zero, except the number 0 itself.

**Example:**

**Input:** (2 -> 4 -> 3) + (5 -> 6 -> 4)

**Output:** 7 -> 0 -> 8

**Explanation:** 342 + 465 = 807.


## Solution
简单链表
```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        int up = 0;
        ListNode* head = new ListNode(0);
        ListNode* now = head;
        while(l1!=NULL || l2!=NULL){
            int v1=0,v2=0;
            if(l1!=NULL)
                v1 = l1->val;
            if(l2!=NULL)
                v2 = l2->val;
            int sum = v1 + v2 + up;
            now->next = new ListNode(sum%10);
            up = sum/10;
            now = now->next;
            if(l1!=NULL)
                l1 = l1->next;
            if(l2!=NULL)
                l2 = l2->next;
        }
        if(up)
            now->next = new ListNode(1);
        return head->next;
    }
};
```
