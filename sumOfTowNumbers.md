#两数之和

> 问题描述：给定一个整数数组 `nums` 和一个目标值 `target`，请你在该数组中找出和为目标值的那 **两个** 整数，并返回他们的数组下标。
>
> ​       你可以假设每种输入只会对应一个答案。但是，你不能重复利用这个数组中同样的元素。

## 解题思路

> 直接通过两层循环，遍历数组，查找是否存在两个元素之和等于目标元素。

~~~java
class Solution {
    public int[] twoSum(int[] nums, int target) {
         
        for (int i = 0; i < nums.length - 1; i++) {
            for (int j = i + 1; j < nums.length; j++) {
               if (nums[i]+nums[j] == target){                  
                   return new int[]{i,j};
               }
            }
        }
        throw new IllegalArgumentException("No two sum solution");      
    }
}
~~~

> 把数组的索引和值存放到hashMap中，直接查找target-nums[i]的值是否存在于hashMap中。

~~~java
 public static  int[] twoSum(int[] nums, int target) {

        Map<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {

            int complemen = target - nums[i];

            if (map.containsKey(complemen)) {
                return new int[]{map.get(complemen),i};
            }
            map.put(nums[i],i);
        }
        throw new IllegalArgumentException("No two sum solution");

    }
~~~

