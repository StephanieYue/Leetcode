
### Leetcode 34
```python
class Solution(object):
    def search(self, nums, l, r, target):
        if nums[l] == target == nums[r]:
            return([l,r])
        elif nums[l] <= target <= nums[r]:
            mid = int((l+r)/2)
            lindex = self.search(nums,l,mid,target)
            rindex = self.search(nums,mid+1,r,target)
            if -1 in lindex+rindex:
                return max(lindex,rindex)
            else:
                return [lindex[0],rindex[1]]
        else:
            return([-1,-1])
        
    def searchRange(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        if not len(nums):
            return([-1,-1])
        return self.search(nums,0,len(nums)-1,target)
```

### Leetcode 74
```python
class Solution(object):
    def searchMatrix(self, matrix, target):
        """
        :type matrix: List[List[int]]
        :type target: int
        :rtype: bool
        """
        if not len(matrix):
            return False
        
        nrow = len(matrix)
        ncol = len(matrix[0])
        l = 0
        r = nrow * ncol - 1
        
        while l <= r:
            mid = int((l+r)/2)
            num = matrix[int(mid/ncol)][mid%ncol]
            if num == target:
                return True
            elif num < target:
                l = mid+1
            else:
                r = mid-1
        
        return False
```

### Leetcode 162
```python
class Solution(object):
    def findPeakElement(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        l, r = 0, len(nums) - 1
        
        while l + 1 < r:
            mid = int((l+r)/2)
            if nums[mid] > nums[mid+1] and nums[mid] > nums[mid-1]:
                return mid
            elif nums[mid] < nums[mid+1]:
                l = mid + 1
            else:
                r = mid - 1
        
        return l if nums[l] >= nums[r] else r
                
```

### Leetcode 153
```python
class Solution(object):
    def findMin(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        l, r = 0, len(nums) - 1
        while l<r:
            mid = int((l+r)/2)
            if nums[mid] > nums[r]:
                l = mid + 1
            else:
                r = mid
        
        return nums[r]
```
### Leetcode 704
```python
class Solution(object):
    def search(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        l, r = 0, len(nums)-1
        while l<=r:
            mid = (int)((l+r)/2)
            if nums[mid] == target:
                return mid
            elif nums[mid] < target:
                l = mid + 1
            else:
                r = mid - 1
                
        return -1
```
### Leetcode 81


```python
class Solution(object):
    def twoSum(self, nums, target):
        nums.sort()
        head = 0
        tail = len(nums) - 1
        # res = []
        while head < tail:
            if nums[head] + nums[tail] == target:
                return [head, tail] # 找到一组就返回
                # res.append([head, tail])
                # head += 1
                # tail -= 1
            elif nums[head] + nums[tail] < target:
                head += 1
            else:
                tail -= 1
        # return res # 返回所有组合
```
