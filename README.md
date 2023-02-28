# notes
md data structure algorithm notes

# Markdown NOTES NEETCODE BEGINNERS


## Sorting - Insertion Sort
1. 1. Click button choose `.md` file.
2. break into subarrays 
3. sort the first 2nd, 3rd, then 4th values,
4. takes one value (element) & inserts it into a sorted array
```java
// index.js
for(i from 1 to arr.length){
  j=i-1
 while(j>=0 and arr[j+1] < arr[j]) {
     tmp=arr[j+1]
     arr[j+1]=arr[j]
     arr[j]=temp
     j-=1
  } // O(n2)
```

## Sorting - Merge Sort
1. recursive algorithm where we break it into 2 steps
2. divide & conquer 
```javascript
// index.js
int[] mergeSort(int[]arr, int s, int e){
 if (e-s+1<=1)
   return arr;

 m=(s+e)/2;
 mergeSort(arr,s,m);
 mergeSort(arr,m+1,e);

 merge(arr,s,e);

 return arr;
}
``` 

## Sorting - Quick Sort
1. partition the array with the pivot value (usually the right most value at the end)
2. similar to Merge Sort
3. everything less than or equal to the pivot will be on the Left partition of the array
4. 3. everything greater than or equal to the pivot will be on the Right partition of the array
5.
```java
// index.js
int[] quickSort(int[]arr, int s, int e){
 if (e-s+1<=1)
   return arr;
// Partion: elements smaller than pivot on left side
 for i from s to e {
   if(arr[i]<pivot) {
	   tmp=arr[left]
       arr[left]=arr[i]
       arr[i]=temp
       left+=1
    }
    
// Move pivot in-between left & right sides
arr[e]=arr[left]
arr[left]=pivot

 quickSort(arr,s,left-1);
 quickSort(arr,s,left+1, e);

 return arr;
}
``` 

## Binary Search
1. Can only do if the array is in some sort of sorted order 1.3.3.4.5.6.7.8
2. 3 options: target is on left, right, side
3. Parent/Child Sibling Nodes Root Leaf-Nodes 
```javascript
// suedocode
function binarySearch(arr, target){
	L,R = 0.len(arr) - 1
    
    while L <= R {
    mid = (L + R) //2
    
    if target > arr[mid]
    	L = mid + 1
    else if target < arr[mid]
    	R = mid - 1
     else
     	return mid
    }
}
``` 

## Binary Search Tree
1. Can only do if the array is in some sort of sorted order 1.3.3.4.5.6.7.8
2. options: target is on left, right, side
3. Parent/Child Sibling Nodes Root Leaf-Nodes 4. 4. SubTree: everything in the Left SubTree has to be less than the root value and
5. SubTree: Every singl node in the Right SubTree has to be greater than the root value
6. Has a Sorted Property similiar like ones for arrays
```javascript
// suedocode python
def search(root, target):
	if not root:
    	return False
        
     if target > root.val:
     	return search(root.right, target)
     elif target < root.val:
     	return search(root.left, target
     else:
     	return True
```


## Binary Search Tree - Insert
1. Right Leaf node < Root
3. Left Leaf node > Root
``` python
// index.js   
def search(root, target):
	if not root:
    	return False
        
     if target > root.val:
     	return search(root.right, target)
     elif target < root.val:
     	return search(root.left, target)
     else:
     	retrun True
``` 


## Binary Search Tree - Remove
1. Find the minimuim of the Tree
2. Case 1: 0 or 1 child
3. Case 2: 2 children
``` python
// index.js
def minValueNode(root):
	curr = root
    while curr and curr.left:
    	curr = curr.left
    return curr
    
def remove(root, val):
	if not root:
    	return None
        
    if val > root.val:
    	root.right = remove(root.right, val)
    elif val < root.val:
    	root.left = remove(root.left, val)
    else:
    	if not root.left:
        	return root.right
        elif not root.right:
        	return root.left
         else:
            minNode = minValueNode(root.right)
            root.val = minNode.val
            root.right = remove(root.right, minNode.val
     return root

}
``` 

## Binary Search Range
1. Can only do if the array is in some sort of sorted order 1.3.3.4.5.6.7.8
2. 3 options: target is on left, right, side
3. O(log n) where n is the range of numbers

```python
# binary search on some range of values
def binarySearch(low, high){    
    while low <= high:
    mid = (low + high) //2
    
    if isCorrect(mid) > 0:
    	high = mid - 1
    elif if isCorrect(mid) < 0:
    	low = mid + 1
     else:
     	return mid
    return - 1

# Return 1 if n is too big, -1 if too small, 0 if correct
def isCorrect(n):
	if n > 10:
    	return 1
    elif n < 10:
    	return -1
	else:
    	return 0
``` 

## BST - Depth First Search - Traversal
1. Right Leaf node < Root
2. Left Leaf node > Root
3. Go down Left then down the Right nodes like an array

``` python

def inorder(root):
	if not root:
    	return
    inorder(root.left)
    print(root.val)
    inorder(root.right)
    
def preorder(root):
	if not root:
    	return
    print(root.val)
    preorder(root.left)
    preorder(root.right)
    
def postorder(root):
	if not root:
    	return
    postorder(root.left)
    postorder(root.right)
    print(root.val)
``` 

## BST - Breadth First Search 
1. Go level by level top to bottom and search at the closest nodes (getting to the breadth insead of debth)
2. Use a deque (deck) which means double ended queue (FIFO)
3. O(n)

``` python
from collections import deque

def bfs(root):
	queue = deque()
    
	if root:
    	queue.append(root)
        
     level = 0
     while len(queue) > 0;
     	print("level: ", level):
        for i in range(len(queue)):
        	curr = queue.popleft()
            print(curr.val)
            if curr.left:
            	queue.append(curr.left)
            if curr.right:
            	queue.append(curr.right)
         level += 1
``` 

## Arrays - RAM
1.[1, 3, 5] each one of them are stored in the RAM in terms of bytes, which gets converted to bits
2. commonly occupy 4 bytes (32 bits) in memory.
3. An address and a value gets associated with an integer upon storing it in RAM
4. RAM can access any integer at any address in a continuous Random Access Memory O(1)
5. Random Access Memory = continuous block of data, Byte = 8 bits, 


``` javascript
// index.js
function array(){

}
``` 

## Arrays - Static Arrays
1. insert continuous O(1)
2. order of the value does matter
3. shift the 6, then the 5, add 4 before the 6&5
4. r/w i-th element O(1) 
5. Insert/Remove End O(1)
6. Insert Middle O(n)
6. Remove Middle O(n)
7. R/W/Remove = O(1) constant time
8. of Fixed Size
```javascript
// index.js
function array(){

}
```

## Singly Linked List
1. ListNode - val - next
2. An object (ListNode) that encapsulates two things: Value, Next (pointer)
4. [] ---> [] ---> []
```
curr = ListNode1
while(curr != null)
curr = curr.next
```
```
tail.next = ListNode3
tail = ListNode3
// or: tail = tail.next O(1)
// moves tails to the end
```
```
head.next = head.next.next 
// deleting a node: O(n) if have to search for the element
// deletes the 3rd node
// moves head to the 3rd
```

## Doubly Linked List
1. ListNode - prev - val - next
2. 1st and last node is set to *null*
3. Doubly LL has edges pointing to and from
4. [] ---> <--- [] ---> <--- []
```javascript
tail.next = ListNode4
ListNode4.prev = tail
tail = tail.next
// adding a new node (ListNode4) and setting the tail to ListNode4 moving it from ListNode3

```

## Recursion - One-Branch
1. One-Branch, n factorial
```javascript
// index.js
n! = n * (n-1) * (n-2)* ...*1
5! = 5 * 4 * 3 * 2 * 1

5! = 5*4!
n! - n *(n-1)!
```
```javascript
// index.js
int factorial(int n){
 if(n<=1){ //base case
   return 1; 
}
return n*factorial(n-1)
}
```


## Recursion - Two-Branch
1. fibonacci Number: F(n)=F(n-1)+F(n-2)
2. F(0)=0, F(1)=1 //base case
3. O(1)
```java
// index.js
int fib(int n) {
 if(n<=1) { // base case
   return n;
  }
return fib(n-1)+fib(n-2)
}
```
## Quese
1. FIFO - Fist In First Out
2. Enque, Deque 
3. ex. shopping line
```java
// index.js
int fib(int n) {
 if(n<=1) { // base case
   return n;
  }
return fib(n-1)+fib(n-2)
}
```

## Stack
1. LIFO - Last In First Out 
2. Push, Pop, Peek/Top = O(1) 
3. ex. candy roll, set of stacked dishes
4. stack is an array horizontal or vertifal
```java
// index.js
int (int n) {
}
```
