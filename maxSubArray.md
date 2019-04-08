# 最大子序和

> 题目描述：给定一个整数数组 `nums` ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。
>
> **示例:**
>
> ```
> 输入: [-2,1,-3,4,-1,2,1,-5,4],
> 输出: 6
> 解释: 连续子数组 [4,-1,2,1] 的和最大，为 6。
> ```

## 解题思路

> 去掉子数组里和为负数的连续数组

## 代码

~~~java
class Solution {
    public int maxSubArray(int[] nums) {
        int res = nums[0];
        int sum = 0;
        for (int i = 0; i < nums.length; i++) {
            sum += nums[i];
            if (sum > res) {
                res = sum;
            }
            if (sum < 0) {
                sum = 0;
            }
        }
        return res;
    }
}
~~~

