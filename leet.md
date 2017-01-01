#Leet Code

##Algorithms

### Median of Two Sorted Arrays
There are two sorted arrays nums1 and nums2 of size m and n respectively.

Find the median of the two sorted arrays. The overall run time complexity should be O(log (m+n)).

Example 1:
```
nums1 = [1, 3]
nums2 = [2]
```

The median is 2.0
Example 2:
```
nums1 = [1, 2]
nums2 = [3, 4]
```

The median is (2 + 3)/2 = 2.5

```python
class Solution(object):
    def findMedianSortedArrays(self, nums1, nums2):
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: float
        """
        set1, set2, l1, l2 = set(nums1), set(nums2), len(nums1), len(nums2)
        size = l1 + l2
        allsets = set1 | set2
        size2 = len(allsets)
        
        if size2 % 2 == 0:
            allLists = list(allsets)
            if l1 == 0 or l2 == 0 or nums1 == nums2 or size2 < 3:
                return allLists[int(size2/2)]
            return( (allLists[int(size2 / 2)] + allLists[int(size2 / 2) + 1]) / 2 )
        else:
            return list(allsets)[int(size2/2)]
```