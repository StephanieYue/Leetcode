

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
