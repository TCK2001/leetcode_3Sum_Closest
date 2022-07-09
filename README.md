# leetcode_3Sum_Closest
+ 3개의 input값을 더한값이 target값이랑 비슷할경우 return 
+ 跟前一題很像，但是判斷接近target的值

-----
+ Example1
```
Input: nums = [-1,2,1,-4], target = 1
Output: 2
Explanation: The sum that is closest to the target is 2. (-1 + 2 + 1 = 2).
```
----
+ Example2
```
Input: nums = [0,0,0], target = 1
Output: 0
```
----
```python
class Solution:
    def threeSumClosest(self, nums: List[int], target: int) -> int:
        nums.sort()
        res = sum(nums[:3]) # 앞에 잴 작은 3개 더한값 비교하기 위해서 선언함
        
        for i in range(len(nums) - 2):
            l = i + 1
            r = len(nums) - 1
            
            while l < r:
                Tsum = nums[i] + nums[l] + nums[r]
                if abs(Tsum - target) < abs(res - target): # Tsum - target이 res - target보다 작을경우 그 말은 Tsum < res , Tsum값이 더 작을경우 결과값을 Tsum으로 변경
                    res = Tsum
                if Tsum < target: # Tsum이 target보다 작을경우 l++  앞에 문제랑 똑같이 판단
                    l += 1
                else:
                    r -= 1
        return res
```
---
```
결론 : 
TLE...... I don't know why
```
---
```
結論:
TLE.....
```
---
### Result
TLE......
