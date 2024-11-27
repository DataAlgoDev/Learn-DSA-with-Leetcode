#  **1 Dimensional Data Sturucture**
    
**Data Structures in use**
>
>String | Array/List | Stack | Queue | Hash Structures | Linked List

**Techniques and Algorithms**
>
>Multi-Pointer(2, 3, ...) | Sliding Window | Prefix Sum | Recursion-Backtracking | DP | Sorting | Searching

### **2 Pointers**

Uses left and right pointer. Usually O(n)

[167. Two Sum II - Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/)
```python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        n = len(numbers)
        l = 0
        r = n - 1
        while l < r:    # Loop till they meet. O(n)
            summ = numbers[l] + numbers[r]
            if summ == target:
                return [l + 1, r + 1]   # 1 indexed o/p
            elif summ < target:
                l += 1
            else:
                r -= 1
```

[11. Container With Most Water](https://leetcode.com/problems/container-with-most-water/description/)

```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        capacity = 0        # Maximum capacity it can have
        l, r = 0, len(height) - 1
        
        while l < r:                    # O(n)
            product = (r - l) * min(height[l], height[r]) # Current water content
            if product > capacity:
                capacity = product      # Keeping max capacity stored every while
            if height[l] <= height[r]:  # Update condition for pointers
                l += 1
            else:
                r -= 1
        return capacity
```

### **3 Pointers**
Uses 3 pointer : left, right, mid

