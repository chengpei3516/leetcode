# 移除元素

> 定一个数组 *nums* 和一个值 *val*，你需要**原地**移除所有数值等于 *val* 的元素，返回移除后数组的新长度。
>
> 不要使用额外的数组空间，你必须在**原地修改输入数组**并在使用 O(1) 额外空间的条件下完成。
>
> 元素的顺序可以改变。你不需要考虑数组中超出新长度后面的元素。
>
> **示例 1:**
>
> ```
> 给定 nums = [3,2,2,3], val = 3,
> 
> 函数应该返回新的长度 2, 并且 nums 中的前两个元素均为 2。
> 
> 你不需要考虑数组中超出新长度后面的元素。
> ```

## 解题思路

>当 nums[j]*n**u**m**s*[*j*] 与给定的值相等时，递增 j*j* 以跳过该元素。只要 nums[j] \neq val*n**u**m**s*[*j*]̸=*v**a**l*，我们就复制 nums[j]*n**u**m**s*[*j*] 到 nums[i]*n**u**m**s*[*i*] 并同时递增两个索引。重复这一过程，直到 j*j* 到达数组的末尾，该数组的新长度为 i。

## 代码

~~~java
class Solution {
    public int removeElement(int[] nums, int val) {
        int length = 0;
        for (int i = 0; i < nums.length; i++) {
          if(nums[i] != val){
              nums[length] = nums[i];
              length++;
          }
        }

        return length;
    }
}
~~~

