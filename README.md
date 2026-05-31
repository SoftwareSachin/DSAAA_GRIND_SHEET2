# 🎯 DSA MCQ Practice Bank — Part 2: Output Prediction & Code Tracing (100 Problems)

> **Exam-pattern code tracing for Rajasthan Senior Computer Instructor exam**
> Step-by-step trace included for hardest problems

---

# 📚 SECTION A: STACK OUTPUT PREDICTION (Q1-20)

---

**Q1.** Stack operations: push(1), push(2), push(3), pop(), push(4), pop(). What's on top?
(A) 1  (B) 2  (C) 3  (D) 4

**Trace:**
```
push(1): [1]           top=1
push(2): [1,2]         top=2
push(3): [1,2,3]       top=3
pop():   [1,2]         top=2, popped 3
push(4): [1,2,4]       top=4
pop():   [1,2]         top=2, popped 4
```
**Ans: B**

---

**Q2.** Stack after: push(5), push(3), push(7), pop(), peek():
(A) 5  (B) 3  (C) 7  (D) Stack empty

**Trace:**
```
push(5): [5]
push(3): [5,3]
push(7): [5,3,7]
pop():   [5,3] (popped 7)
peek():  returns 3 (no modification)
```
**Ans: B**

---

**Q3.** Evaluate postfix: `5 6 2 + * 12 4 / -`
(A) 37  (B) 38  (C) 36  (D) 35

**Trace:**
```
5  → [5]
6  → [5,6]
2  → [5,6,2]
+  → pop 2,6: 6+2=8 → [5,8]
*  → pop 8,5: 5*8=40 → [40]
12 → [40,12]
4  → [40,12,4]
/  → pop 4,12: 12/4=3 → [40,3]
-  → pop 3,40: 40-3=37 → [37]
```
**Ans: A**

---

**Q4.** Evaluate prefix: `+ * 2 3 4`
(A) 10  (B) 14  (C) 20  (D) 24

**Trace (scan right to left):**
```
4  → [4]
3  → [4,3]
2  → [4,3,2]
*  → pop 2,3: 2*3=6 → [4,6]
+  → pop 6,4: 6+4=10 → [10]
```
**Ans: A**

---

**Q5.** Convert `A+B*(C-D)` to postfix:
(A) AB+CD-*  (B) ABCD-*+  (C) AB*C-D+  (D) A+BC*-D

**Trace:**
```
A     → output: A
+     → stack: [+]
B     → output: AB
*     → stack: [+,*]
(     → stack: [+,*,(]
C     → output: ABC
-     → stack: [+,*,(,-]
D     → output: ABCD
)     → pop until (: output ABCD-, stack: [+,*]
End   → pop all: output ABCD-*+
```
**Ans: B**

---

**Q6.** Convert `A*B+C/D` to prefix:
(A) +*AB/CD  (B) *AB+/CD  (C) +AB*CD/  (D) *+AB/CD

**Trace:**
```
* applies to A,B → *AB
/ applies to C,D → /CD
+ applies to *AB and /CD → +*AB/CD
```
**Ans: A**

---

**Q7.** Stack array of size 10 (top=-1). After 7 pushes and 3 pops, top equals:
(A) 4  (B) 3  (C) 7  (D) 10

**Trace:** Net items = 7 - 3 = 4. Top = 4 - 1 = 3.
**Ans: B**

---

**Q8.** Evaluate postfix: `3 4 * 5 +`
(A) 17  (B) 27  (C) 12  (D) 15

**Trace:**
```
3   → [3]
4   → [3,4]
*   → 3*4=12 → [12]
5   → [12,5]
+   → 12+5=17 → [17]
```
**Ans: A**

---

**Q9.** Postfix of `(A+B)*(C+D)`:
(A) AB+CD+*  (B) AB+CD*+  (C) ABCD++*  (D) AB*CD+

**Trace:**
- (A+B) → AB+
- (C+D) → CD+
- multiply → AB+CD+*
**Ans: A**

---

**Q10.** Stack contents after: push(A), push(B), pop(), push(C), pop(), push(D):
(A) [A,D]  (B) [A,B,D]  (C) [D]  (D) [A,C,D]

**Trace:**
```
push(A): [A]
push(B): [A,B]
pop():   [A]
push(C): [A,C]
pop():   [A]
push(D): [A,D]
```
**Ans: A**

---

**Q11.** Evaluate postfix: `10 2 8 + * 3 -`
(A) 97  (B) 27  (C) 17  (D) 100

**Trace:**
```
10  → [10]
2   → [10,2]
8   → [10,2,8]
+   → 2+8=10 → [10,10]
*   → 10*10=100 → [100]
3   → [100,3]
-   → 100-3=97 → [97]
```
**Ans: A**

---

**Q12.** Maximum number of operands stack can hold during postfix evaluation of `a b + c * d -`:
(A) 1  (B) 2  (C) 3  (D) 4

**Trace:**
```
a → [a]         size 1
b → [a,b]       size 2
+ → [r1]        size 1
c → [r1,c]      size 2
* → [r2]        size 1
d → [r2,d]      size 2
- → [r3]        size 1
```
Max = 2.
**Ans: B**

---

**Q13.** Convert `((A+B)*C-(D-E))/F` to postfix:
(A) AB+C*DE--F/  (B) AB+C*DE-/-F  (C) AB+CDE-*F-/  (D) AB+C*DE-F-/

**Trace step-by-step:**
- (A+B) → AB+
- (A+B)*C → AB+C*
- (D-E) → DE-
- (A+B)*C - (D-E) → AB+C*DE--
- divide by F → AB+C*DE--F/
**Ans: A**

---

**Q14.** Stack supports push/pop. Sequence of pushes: 1,2,3,4,5. Which output is NOT possible?
(A) 5,4,3,2,1  (B) 1,2,3,4,5  (C) 4,3,5,1,2  (D) 3,2,1,5,4

**Analysis:** Option C: 4 out first means 1,2,3 still in stack with 4 popped after. Then 3 popped, then 5 pushed and popped. But 1 cannot come before 2 if both are below... actually 1,2 are at bottom, so popping order should be 2 then 1. Option C says 1 then 2, which is impossible.
**Ans: C**

---

**Q15.** Convert prefix `*+AB-CD` to infix:
(A) A+B*C-D  (B) (A+B)*(C-D)  (C) A*B+C-D  (D) (A+B)*(C+D)

**Trace:** * applies to (+AB) and (-CD) → (A+B)*(C-D)
**Ans: B**

---

**Q16.** Stack of size 5. Operations: 6 pushes attempted. What happens at 6th push?
(A) Success  (B) Overflow  (C) Underflow  (D) Element replaces top

**Ans: B** — Stack of size 5 holds max 5 elements; 6th push overflows.

---

**Q17.** Evaluate postfix: `2 3 + 5 4 - *`
(A) 5  (B) 10  (C) 25  (D) 1

**Trace:**
```
2 3 + → 5
5 4 - → 1
5 1 * → 5
```
**Ans: A**

---

**Q18.** Stack used to reverse string "HELLO". After all pushes and pops, output is:
(A) HELLO  (B) OLLEH  (C) HOLLE  (D) LLEHO

**Trace:** Push H,E,L,L,O. Pop gives O,L,L,E,H.
**Ans: B**

---

**Q19.** What does this evaluate to in postfix: `6 2 / 3 - 4 +`?
(A) 4  (B) 7  (C) 6  (D) 8

**Trace:**
```
6 2 / → 3
3 3 - → 0
0 4 + → 4
```
**Ans: A**

---

**Q20.** Prefix to postfix: `+*AB-CD` becomes:
(A) AB*CD-+  (B) AB+CD-*  (C) AB*-CD+  (D) ABCD-+*

**Trace:** +*AB-CD = (A*B) + (C-D) = AB* + CD- = AB*CD-+
**Ans: A**

---

# 📚 SECTION B: QUEUE OUTPUT PREDICTION (Q21-35)

---

**Q21.** Queue operations: enqueue(1), enqueue(2), enqueue(3), dequeue(), enqueue(4). Front element:
(A) 1  (B) 2  (C) 3  (D) 4

**Trace:**
```
enqueue(1): [1]            front=1
enqueue(2): [1,2]          front=1
enqueue(3): [1,2,3]        front=1
dequeue():  [2,3]          front=2 (removed 1)
enqueue(4): [2,3,4]        front=2
```
**Ans: B**

---

**Q22.** Circular queue size 5. Initial: empty. Operations: enq(A,B,C,D), deq(), deq(), enq(E,F). State:
(A) C,D,E,F  (B) A,B,E,F  (C) E,F,C,D  (D) F,E,D,C

**Trace:**
```
enq(A,B,C,D): [A,B,C,D,_]    front=0, rear=3
deq(): [_,B,C,D,_]            front=1
deq(): [_,_,C,D,_]            front=2
enq(E): [_,_,C,D,E]           rear=4
enq(F): [F,_,C,D,E]           rear=0 (wrap)
Elements: C,D,E,F (in queue order)
```
**Ans: A**

---

**Q23.** Circular queue size 4. After enq(1,2,3,4), full condition (rear+1)%4 == front?
(A) Yes  (B) No  (C) Depends  (D) Cannot determine

**Trace:** After 4 enqueues with size 4, queue is full. front=0, rear=3. (3+1)%4 = 0 = front. **Yes!**
**Ans: A**

---

**Q24.** Priority queue with elements (priority, value): (3,A), (1,B), (2,C). Highest priority dequeued first. Order:
(A) A,B,C  (B) B,C,A  (C) A,C,B  (D) C,B,A

**Note:** Lower number = higher priority typically. Or higher number = higher priority. Assume MAX priority:
- Order: A(3), C(2), B(1)
**Ans: C**

---

**Q25.** BFS uses queue. For tree with root A, children B,C, and B's children D,E. BFS order:
(A) A,B,C,D,E  (B) A,D,E,B,C  (C) A,B,D,E,C  (D) A,C,B,E,D

**Trace:**
```
Q: [A]
Visit A, enqueue B,C → Q: [B,C]
Visit B, enqueue D,E → Q: [C,D,E]
Visit C → Q: [D,E]
Visit D → Q: [E]
Visit E → Q: []
Order: A,B,C,D,E
```
**Ans: A**

---

**Q26.** Queue of size 5. Operations: 7 enqueues + 2 dequeues. What happens?
(A) Success  (B) Overflow at 6th enqueue  (C) Underflow  (D) Success at 7th

**Trace:** Queue holds max 5. At 6th enqueue (before any dequeue), overflow occurs.
**Ans: B**

---

**Q27.** Two stacks implementing a queue. Push 1,2,3. Pop. What's returned?
(A) 1  (B) 2  (C) 3  (D) Error

**Logic:** Two-stack queue: enqueue on stack1, dequeue transfers to stack2 then pops.
- Push 1,2,3 on stack1: [1,2,3]
- Dequeue: transfer to stack2 (reverses) → stack2: [3,2,1], pop top = 1
**Ans: A**

---

**Q28.** Deque operations: addFront(1), addRear(2), addFront(3), removeRear(). Front element:
(A) 1  (B) 2  (C) 3  (D) Empty

**Trace:**
```
addFront(1):  [1]
addRear(2):   [1,2]
addFront(3):  [3,1,2]
removeRear(): [3,1]    (removed 2)
Front = 3
```
**Ans: C**

---

**Q29.** Linear queue size 5. Operations: enq 4 times, deq 2 times, enq 3 times. Any error?
(A) No error  (B) Overflow  (C) Underflow  (D) Both

**Trace:** Linear queue rear keeps moving:
- 4 enq: rear=3
- 2 deq: front=2
- 3 more enq: rear=6 — OVERFLOW in linear (even though space exists)
**Ans: B**

---

**Q30.** Round Robin scheduling with quantum 2. Processes (burst): P1(5), P2(3), P3(2). Order of execution:
(A) P1,P2,P3,P1,P2,P3,P1  (B) P1,P2,P3,P1,P2,P1  (C) P1,P1,P2,P2,P3,P3  (D) P1,P2,P3,P1,P1,P2

**Trace:**
```
Time 0-2:  P1 runs (burst becomes 3)
Time 2-4:  P2 runs (burst becomes 1)
Time 4-6:  P3 runs (burst becomes 0, done)
Time 6-8:  P1 runs (burst becomes 1)
Time 8-9:  P2 runs (burst becomes 0, done)
Time 9-10: P1 runs (done)
Order: P1,P2,P3,P1,P2,P1
```
**Ans: B**

---

**Q31.** Queue with operations: enq(A), enq(B), deq(), enq(C), enq(D), deq(). Queue now:
(A) [A,B]  (B) [C,D]  (C) [B,C]  (D) [A,D]

**Trace:**
```
enq(A): [A]
enq(B): [A,B]
deq():  [B]    (removed A)
enq(C): [B,C]
enq(D): [B,C,D]
deq():  [C,D]  (removed B)
```
**Ans: B**

---

**Q32.** Print queue: jobs of size 5,3,8,2,4 KB arrive. FIFO order, what's processed third?
(A) 5KB  (B) 3KB  (C) 8KB  (D) 2KB

**Trace:** FIFO order = arrival order. Third = 8KB.
**Ans: C**

---

**Q33.** Circular queue size 6, front=2, rear=4. Number of elements:
(A) 2  (B) 3  (C) 4  (D) 6

**Trace:** rear - front + 1 = 4 - 2 + 1 = 3.
**Ans: B**

---

**Q34.** Empty queue check: front == -1. After enq(5), what changes?
(A) front=0, rear=0  (B) front=-1, rear=0  (C) front=0, rear=-1  (D) front=1, rear=1

**Trace:** First enqueue sets both front and rear to 0.
**Ans: A**

---

**Q35.** A queue is implemented using a singly linked list. Enqueue complexity (with tail pointer):
(A) O(1)  (B) O(log n)  (C) O(n)  (D) Depends

**Ans: A** — Tail pointer allows O(1) insertion.

---

# 📚 SECTION C: TREE OUTPUT PREDICTION (Q36-65)

---

**Q36.** Binary tree:
```
        A
       / \
      B   C
     /   / \
    D   E   F
```
Preorder traversal:
(A) D B A E C F  (B) A B D C E F  (C) A B D E C F  (D) D B E A F C

**Trace (Pre: Root,L,R):**
```
A → visit B → visit D (leaf) → back to B (no right)
→ back to A → visit C → visit E (leaf) → visit F (leaf)
Output: A B D C E F
```
**Ans: B**

---

**Q37.** Same tree as Q36. Inorder traversal:
(A) D B A E C F  (B) A B D C E F  (C) D B A C E F  (D) D B A E F C

**Trace (In: L,Root,R):**
- B's subtree: D, B (D has no right; B has no right)
- A
- C's subtree: E, C, F
- Output: D B A E C F
**Ans: A**

---

**Q38.** Same tree. Postorder traversal:
(A) D B E F C A  (B) D B A E C F  (C) D E F B C A  (D) D B F E C A

**Trace (Post: L,R,Root):**
- D (leaf, B's left)
- B (no right child)
- E (leaf, C's left)
- F (leaf, C's right)
- C
- A
Output: D B E F C A
**Ans: A**

---

**Q39.** BST inserting 50, 30, 70, 20, 40, 60, 80 in order. Inorder traversal:
(A) 50,30,70,20,40,60,80  (B) 20,30,40,50,60,70,80  (C) 80,70,60,50,40,30,20  (D) 20,40,30,60,80,70,50

**Trace:** Inorder of BST = sorted ascending.
**Ans: B**

---

**Q40.** Build tree from: Preorder ABCDE, Inorder BADCE. Postorder:
(A) BDECA  (B) ABCDE  (C) BCDEA  (D) BCEDA

**Trace:**
- Root = A (first preorder)
- Inorder split: B | A | DCE → Left=B, Right=DCE
- Preorder of right = BCDE → without B = CDE → Root of right = C
- C's inorder: D|C|E → Left=D, Right=E

Tree:
```
        A
       / \
      B   C
         / \
        D   E
```
Postorder: B D E C A
**Ans: A**

---

**Q41.** Postorder = DEBFCA, Inorder = DBEAFC. Preorder:
(A) ABDECF  (B) ABCDEF  (C) ABDCFE  (D) ADBECF

**Trace:**
- Root = A (last postorder)
- Inorder split: DBE | A | FC → Left=DBE, Right=FC
- Postorder of left = DEB → Root B
- B's inorder: D|B|E → Left=D, Right=E
- Right subtree postorder = FC → Root C
- C's inorder: F|C| (empty) → Left=F

Tree:
```
        A
       / \
      B   C
     / \ /
    D  E F
```
Preorder: A B D E C F
**Ans: A**

---

**Q42.** BST insertion of 10, 5, 15, 3, 7, 12, 20 then delete root (using inorder successor). New root:
(A) 5  (B) 7  (C) 12  (D) 15

**Trace:**
```
Tree:       10
           /  \
          5    15
         / \   / \
        3   7 12  20

Inorder successor of 10 = smallest in right subtree = 12
Replace 10 with 12, delete original 12.
```
**Ans: C**

---

**Q43.** BST insertion: 8, 3, 10, 1, 6, 14, 4, 7, 13. Height of tree (root height = 0):
(A) 2  (B) 3  (C) 4  (D) 5

**Trace:**
```
              8
             / \
            3   10
           / \    \
          1   6   14
             / \  /
            4   7 13

Heights: leaves at depth 3 (4,7,13), so height = 3
```
**Ans: B**

---

**Q44.** Maximum heap [50, 30, 40, 10, 20]. Insert 60. Result array:
(A) [60,30,50,10,20,40]  (B) [60,50,40,10,20,30]  (C) [60,30,40,10,20,50]  (D) [50,30,60,10,20,40]

**Trace:**
```
Initial heap (array): [50,30,40,10,20]
Add 60 at end: [50,30,40,10,20,60]
Position 5, parent = (5-1)/2 = 2 → arr[2]=40
60 > 40? Yes, swap: [50,30,60,10,20,40]
60 at index 2, parent = (2-1)/2 = 0 → arr[0]=50
60 > 50? Yes, swap: [60,30,50,10,20,40]
60 at index 0 (root) - done!
```
**Ans: A**

---

**Q45.** Max heap [100,80,70,50,60,40,30]. Delete root (extract max). Resulting array:
(A) [80,70,60,50,30,40]  (B) [80,60,70,50,30,40]  (C) [80,70,40,50,60,30]  (D) [70,80,60,50,30,40]

**Trace:**
```
Replace root with last: [30,80,70,50,60,40]
Heapify down 30:
  - 30 vs 80,70 → larger is 80 → swap: [80,30,70,50,60,40]
  - 30 at idx 1, children at 3,4 = 50,60 → larger 60 → swap: [80,60,70,50,30,40]
  - 30 at idx 4, no children → done
```
**Ans: B**

---

**Q46.** Inorder traversal of BST gives: 1,3,5,7,9,11,13. If root has value 7, what's preorder?
(A) 7,3,1,5,11,9,13  (B) 7,5,3,1,11,13,9  (C) 1,3,5,7,9,11,13  (D) 7,9,11,13,1,3,5

**Trace:**
```
Root = 7
Left subtree inorder: 1,3,5
Right subtree inorder: 9,11,13

Standard balanced BST:
              7
             / \
            3   11
           / \  / \
          1   5 9  13

Preorder: 7,3,1,5,11,9,13
```
**Ans: A**

---

**Q47.** A complete binary tree has 9 nodes. Height (root=0)?
(A) 2  (B) 3  (C) 4  (D) 9

**Trace:**
```
Level 0: 1 node (1)
Level 1: 2 nodes (3)
Level 2: 4 nodes (7)
Level 3: 2 nodes (9 total)
Height = 3
```
**Ans: B**

---

**Q48.** Level-order of tree:
```
        1
       / \
      2   3
     /     \
    4       5
```
Output:
(A) 1,2,3,4,5  (B) 4,2,5,3,1  (C) 1,4,2,5,3  (D) 4,5,2,3,1

**Trace:** BFS level by level: 1, then 2,3, then 4,5.
**Ans: A**

---

**Q49.** BST with values 5,3,8,1,4,7,9. Search for 7 takes how many comparisons?
(A) 1  (B) 2  (C) 3  (D) 4

**Trace:**
```
Tree:
        5
       / \
      3   8
     /\  /\
    1 4 7 9

Search 7:
- Compare with 5: 7 > 5, go right (1 comp)
- Compare with 8: 7 < 8, go left (2 comp)
- Compare with 7: match! (3 comp)
```
**Ans: C**

---

**Q50.** Min heap [3,5,4,10,8,7]. Extract min, result:
(A) [4,5,7,10,8]  (B) [5,7,4,10,8]  (C) [4,7,5,10,8]  (D) [3,5,4,10,8]

**Trace:**
```
Replace root with last: [7,5,4,10,8]
Heapify down 7:
- 7 vs 5,4 → smaller is 4 → swap: [4,5,7,10,8]
- 7 at idx 2, children at 5,6 (none, end of array)
- Done
```
**Ans: A**

---

**Q51.** AVL tree after inserting 10, 20, 30 (creates imbalance):
(A) Rotation needed  (B) Stays as is  (C) Becomes unbalanced  (D) Tree breaks

**Ans: A** — Right-Right case, left rotation makes 20 root.

---

**Q52.** Number of leaf nodes in full binary tree with 7 internal nodes:
(A) 6  (B) 7  (C) 8  (D) 14

**Ans: C** — Full BT: L = I + 1 = 8.

---

**Q53.** Tree inserts: 4,2,1,3,6,5,7. Inorder:
(A) 1,2,3,4,5,6,7  (B) 4,2,1,3,6,5,7  (C) 1,3,2,4,5,7,6  (D) 7,6,5,4,3,2,1

**Trace:** BST inorder = sorted.
**Ans: A**

---

**Q54.** Height of perfect binary tree with 31 nodes:
(A) 4  (B) 5  (C) 31  (D) 30

**Trace:** 2^(h+1) - 1 = 31 → h = 4.
**Ans: A**

---

**Q55.** Binary tree with all left children only (left-skewed). Height with n nodes:
(A) log n  (B) n-1  (C) n  (D) √n

**Ans: B** — Skewed tree height = n-1.

---

**Q56.** Heap operations: build from [4,10,3,5,1]. Final max-heap:
(A) [10,5,3,4,1]  (B) [10,4,3,5,1]  (C) [10,5,4,3,1]  (D) [10,3,4,5,1]

**Trace (build heap, heapify from n/2-1 down):**
```
Start: [4,10,3,5,1]
i=1 (10): children 5,1, 10 is largest, no swap
i=0 (4): children 10,3, largest is 10, swap
        [10,4,3,5,1]
        heapify at idx 1: children 5,1, largest 5, swap
        [10,5,3,4,1]
        idx 3 (4) is leaf, done

Final: [10,5,3,4,1]
```
**Ans: A**

---

**Q57.** Inorder predecessor of node 50 in BST with subtree:
```
    50
   /
  30
 / \
20  40
```
(A) 20  (B) 30  (C) 40  (D) 50

**Ans: C** — Largest in left subtree = 40.

---

**Q58.** BST after inserting 6,4,8,3,5,7,9 then deleting 6 (using successor):
New root:
(A) 7  (B) 5  (C) 4  (D) 8

**Trace:** Successor = smallest in right subtree of 6 = 7.
**Ans: A**

---

**Q59.** Number of binary trees with 3 nodes:
(A) 3  (B) 4  (C) 5  (D) 6

**Trace:** Catalan number C(3) = 5. The 5 structurally different BSTs.
**Ans: C**

---

**Q60.** Inorder of BST after inserting 50,30,70,20,40,60,80, then deleting 30:
(A) 20,40,50,60,70,80  (B) 20,40,30,50,60,70,80  (C) 30,40,50,60,70,80  (D) 50,20,40,60,70,80

**Trace:** After deletion, inorder still sorted, just without 30.
**Ans: A**

---

**Q61.** Maximum number of nodes at level 5 (root at level 0) in binary tree:
(A) 16  (B) 32  (C) 5  (D) 31

**Ans: B** — 2^5 = 32.

---

**Q62.** A heap of 100 elements has height (root=0):
(A) 6  (B) 7  (C) 50  (D) 99

**Ans: A** — ⌊log₂(100)⌋ = 6.

---

**Q63.** Build min-heap from [9,5,6,2,3]. Result:
(A) [2,3,6,5,9]  (B) [2,3,6,9,5]  (C) [2,5,6,9,3]  (D) [2,5,3,9,6]

**Trace:**
```
[9,5,6,2,3]
i=1 (5): children 2,3, min=2, swap → [9,2,6,5,3]
i=0 (9): children 2,6, min=2, swap → [2,9,6,5,3]
        heapify at 1 (9): children 5,3, min=3, swap → [2,3,6,5,9]
        leaf at idx 4, done
Result: [2,3,6,5,9]
```
**Ans: A**

---

**Q64.** In max heap, parent index of 7 is:
(A) 2  (B) 3  (C) 4  (D) 6

**Trace:** (7-1)/2 = 3.
**Ans: B**

---

**Q65.** B-Tree of order 5 means each node can have max:
(A) 5 children  (B) 5 keys  (C) 4 children  (D) Depends on implementation

**Ans: A** — Order = max children. (Some texts use order = max keys, but standard is children.)

---

# 📚 SECTION D: SORTING TRACE (Q66-80)

---

**Q66.** Insertion sort on [5,2,4,6,1,3] after 2 passes:
(A) [2,4,5,6,1,3]  (B) [2,5,4,6,1,3]  (C) [2,4,5,1,3,6]  (D) [5,2,4,6,1,3]

**Trace:**
```
Initial: [5,2,4,6,1,3]
Pass 1 (i=1, key=2): shift 5 right → [2,5,4,6,1,3]
Pass 2 (i=2, key=4): shift 5 right → [2,4,5,6,1,3]
```
**Ans: A**

---

**Q67.** Bubble sort on [5,1,4,2,8]. After first pass:
(A) [1,4,2,5,8]  (B) [1,2,4,5,8]  (C) [5,1,4,2,8]  (D) [1,4,2,8,5]

**Trace:**
```
[5,1,4,2,8]
Compare 5,1: swap → [1,5,4,2,8]
Compare 5,4: swap → [1,4,5,2,8]
Compare 5,2: swap → [1,4,2,5,8]
Compare 5,8: no swap → [1,4,2,5,8]
```
**Ans: A**

---

**Q68.** Selection sort on [29,10,14,37,13]. After 2 iterations:
(A) [10,13,14,37,29]  (B) [10,14,29,37,13]  (C) [13,14,10,37,29]  (D) [10,13,29,37,14]

**Trace:**
```
[29,10,14,37,13]
Iter 1: min = 10 (index 1), swap with index 0 → [10,29,14,37,13]
Iter 2: min in [29,14,37,13] = 13 (index 4), swap with index 1 → [10,13,14,37,29]
```
**Ans: A**

---

**Q69.** Quicksort partition (Lomuto, pivot=last) on [10,80,30,90,40,50,70] with pivot 70:
After partition, pivot index:
(A) 3  (B) 4  (C) 5  (D) 6

**Trace:**
```
pivot=70
Elements ≤70: 10,30,40,50 (count=4)
pivot goes to index 4
Result: [10,30,40,50,70,90,80]
```
**Ans: B**

---

**Q70.** Merge sort on [38,27,43,3,9,82,10]. Merge of [38,27] and [43,3]:
Wait, merge happens on SORTED subarrays. After sorting [38,27]=[27,38] and [43,3]=[3,43], merge:
(A) [27,38,3,43]  (B) [3,27,38,43]  (C) [38,27,43,3]  (D) [3,43,27,38]

**Trace:** Merge sorted lists.
**Ans: B**

---

**Q71.** How many comparisons in best case bubble sort for n elements (with optimization)?
(A) n-1  (B) n²  (C) n log n  (D) n!

**Ans: A** — One pass, n-1 comparisons, no swaps → exit.

---

**Q72.** Counting sort on [4,2,2,8,3,3,1] with range 0-8. Time complexity:
(A) O(n)  (B) O(n+k)  (C) O(n log n)  (D) O(n²)

**Ans: B** — n=7, k=9 → O(n+k).

---

**Q73.** Radix sort sorts integers digit by digit. For 3-digit numbers, number of passes:
(A) 1  (B) 3  (C) 10  (D) Variable

**Ans: B** — One pass per digit.

---

**Q74.** Quicksort worst case occurs when:
(A) Array is sorted  (B) Pivot always selects smallest  (C) Equal elements  (D) All of these

**Ans: D** — All create unbalanced partitions.

---

**Q75.** Number of swaps in selection sort for n elements:
(A) 0  (B) n  (C) n-1  (D) n²

**Ans: C** — One swap per iteration, n-1 iterations.

---

**Q76.** Insertion sort best case (already sorted) complexity:
(A) O(1)  (B) O(n)  (C) O(n²)  (D) O(n log n)

**Ans: B** — One comparison per element, no shifts.

---

**Q77.** Heap sort: build max heap of [4,10,3,5,1] then extract max once:
(A) [5,4,3,1]  (B) [5,4,3,1,10]  (C) [5,1,3,4,10]  (D) [4,5,3,1,10]

**Trace:**
```
Max heap: [10,5,3,4,1]
Extract max: swap with last, reduce size
[1,5,3,4,10] (10 placed at end, size=4)
Heapify down 1: children 5,3 → swap with 5 → [5,1,3,4,10]
  At idx 1, child = 4 → swap → [5,4,3,1,10]
```
**Ans: B** (with 10 at end)

---

**Q78.** Best sorting algorithm for nearly sorted array:
(A) Quick sort  (B) Insertion sort  (C) Heap sort  (D) Merge sort

**Ans: B** — Near-sorted has O(n) for insertion sort.

---

**Q79.** Stable sort preserves order of:
(A) Different elements  (B) Equal elements  (C) Negative numbers  (D) Largest elements

**Ans: B** — Equal keys keep their original relative order.

---

**Q80.** Total comparisons in worst case merge sort for n=8:
(A) 8  (B) 17  (C) 24  (D) 64

**Trace:** n log n = 8 × 3 = 24 max comparisons.
**Ans: C**

---

# 📚 SECTION E: GRAPH TRAVERSAL (Q81-100)

---

**Q81.** BFS from A on graph: A-B, A-C, B-D, C-E. Adjacency order alphabetical. BFS visits:
(A) A,B,C,D,E  (B) A,B,D,C,E  (C) A,C,E,B,D  (D) A,D,E,B,C

**Trace:**
```
Q: [A], visit A
Q: [B,C], visit B, enqueue D
Q: [C,D], visit C, enqueue E
Q: [D,E], visit D
Q: [E], visit E
Order: A,B,C,D,E
```
**Ans: A**

---

**Q82.** DFS from A on same graph. DFS visits:
(A) A,B,C,D,E  (B) A,B,D,C,E  (C) A,C,E,B,D  (D) A,D,E,B,C

**Trace:**
```
A → push neighbors B,C → pop C (or B based on order)
Using neighbors in order, recursive DFS:
A → B → D (B has no more neighbors) → back → C → E
Order: A,B,D,C,E
```
**Ans: B**

---

**Q83.** Number of edges in MST of graph with 6 vertices:
(A) 5  (B) 6  (C) 15  (D) Depends on graph

**Ans: A** — n-1 = 5.

---

**Q84.** Dijkstra's algorithm starts from source S=A. Edges: A-B(1), A-C(4), B-C(2), B-D(5), C-D(1). Shortest distance to D:
(A) 4  (B) 5  (C) 6  (D) 7

**Trace:**
```
A: 0
A→B = 1
A→C = min(4, 1+2) = 3
A→D = min(1+5, 3+1) = min(6, 4) = 4
```
**Ans: A**

---

**Q85.** A graph has 8 vertices, 12 edges. Is it possibly a tree?
(A) Yes  (B) No  (C) Depends  (D) Cannot determine

**Ans: B** — Tree has exactly n-1 = 7 edges, not 12.

---

**Q86.** BFS distance from source. If d(s,u)=2 and v is enqueued after u, then d(s,v):
(A) < 2  (B) = 2  (C) ≥ 2  (D) Cannot say

**Ans: C** — Nodes enqueued later have ≥ distance.

---

**Q87.** Number of strongly connected components in directed graph A→B→C→A and D→E:
(A) 1  (B) 2  (C) 3  (D) 5

**Trace:** {A,B,C} is one SCC, {D} and {E} are separate (D→E only one direction).
**Ans: C**

---

**Q88.** Adjacency matrix of undirected graph is:
(A) Always symmetric  (B) Never symmetric  (C) Sometimes symmetric  (D) Diagonal only

**Ans: A** — Undirected ⇒ matrix[i][j] = matrix[j][i].

---

**Q89.** Topological sort on DAG: A→B, A→C, B→D, C→D. Valid order:
(A) A,B,C,D  (B) A,C,B,D  (C) Both A and B  (D) D,B,C,A

**Ans: C** — Both orderings are valid.

---

**Q90.** A connected graph with 5 vertices and 10 edges is:
(A) Tree  (B) Has cycles  (C) Disconnected  (D) Bipartite

**Ans: B** — More edges than n-1 means cycles exist.

---

**Q91.** DFS uses recursion. Stack depth for graph with V vertices:
(A) O(1)  (B) O(log V)  (C) O(V)  (D) O(V²)

**Ans: C** — Worst case linear path.

---

**Q92.** Prim's vs Kruskal's: which is better for SPARSE graph?
(A) Prim's  (B) Kruskal's  (C) Same  (D) Neither

**Ans: B** — Kruskal's O(E log E) better when E small.

---

**Q93.** Bellman-Ford detects:
(A) MST  (B) Shortest path  (C) Negative cycles  (D) Connected components

**Ans: C** — Special feature beyond Dijkstra.

---

**Q94.** A graph is bipartite if:
(A) 2 vertices  (B) No odd cycles  (C) Connected  (D) Acyclic

**Ans: B** — Iff no odd-length cycles.

---

**Q95.** Floyd-Warshall complexity:
(A) O(V²)  (B) O(V³)  (C) O(V·E)  (D) O(E²)

**Ans: B** — Triple nested loops.

---

**Q96.** BFS from A in graph with edges A-B, A-C, B-D, C-D, D-E. Distance to E:
(A) 1  (B) 2  (C) 3  (D) 4

**Trace:** A→B→D→E or A→C→D→E. Distance = 3.
**Ans: C**

---

**Q97.** Hamilton path visits:
(A) Every edge once  (B) Every vertex once  (C) Starts and ends at same vertex  (D) Shortest distances

**Ans: B** — Visit each vertex exactly once.

---

**Q98.** Eulerian circuit visits:
(A) Every vertex once  (B) Every edge once  (C) Both  (D) Neither

**Ans: B** — Each edge exactly once, returns to start.

---

**Q99.** Number of edges in a complete bipartite graph K(3,4):
(A) 7  (B) 12  (C) 24  (D) 81

**Ans: B** — 3 × 4 = 12.

---

**Q100.** DFS reveals tree edges and:
(A) Cross edges  (B) Back edges  (C) Forward edges  (D) All of these

**Ans: D** — DFS classifies all edge types.

---

# 🎯 ANSWER KEY (Q1-100)

```
1-10:    B B A A B A B A A A A B A C B B A B A A
11-20:   A B B C B A B C A A
21-35:   B A A C A B A C B B B C B A A
36-50:   B A A B A A C B A A A C C A A
51-65:   A C A A B A C A C A B A A B A
66-80:   A A A B B A B B D C B C B B C
81-100:  A B A A B C C A C B C B C B B C B B B D
```

---

## 💪 USAGE GUIDE

**Day 1-2:** Sections A & B (Stacks/Queues) - 35 problems
**Day 3-4:** Section C (Trees) - 30 problems
**Day 5:** Section D (Sorting) - 15 problems
**Day 6:** Section E (Graphs) - 20 problems
**Day 7:** Re-do wrong answers, time yourself

**Continue to Part 3 for ADVANCED problems!** 🚀
