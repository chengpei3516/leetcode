# 删除排序数组中的重复项

> 题目描述：
>
> 给定一个排序数组，你需要在**原地**删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。
>
> 不要使用额外的数组空间，你必须在**原地修改输入数组**并在使用 O(1) 额外空间的条件下完成。

## 解题思路

> 数组完成排序后，我们可以放置两个指针 i和 j，其中 i是慢指针，而 j是快指针。只要 nums[i] = nums[j]*n**u**m**s*[*i*]=*n**u**m**s*[*j*]，我们就增加 j以跳过重复项。
>
> 当我们遇到 nums[j] \neq nums[i]*n**u**m**s*[*j*]̸=*n**u**m**s*[*i*] 时，跳过重复项的运行已经结束，因此我们必须把它（nums[j]*n**u**m**s*[*j*]）的值复制到 nums[i + 1]*n**u**m**s*[*i*+1]。然后递增 i，接着我们将再次重复相同的过程，直到 j到达数组的末尾为止。

## 代码

~~~java
class Solution {
    public int removeDuplicates(int[] nums) {
    if (nums.length == 0) return 0;
    int i = 0;
    for (int j = 1; j < nums.length; j++) {
        if (nums[j] != nums[i]) {
            i++;
            nums[i] = nums[j];
        }
    }
    return i + 1;
    
    }
}
~~~

# 解题思路

> 创建一个TreeSet(),把数组中的值放入TreeSet()中去重复，然后遍历set，把set中的值放入数组中。

## 代码

~~~java
class Solution {
    public int removeDuplicates(int[] nums) {
        Set<Integer> set = new TreeSet<>();
        for (int i = 0; i < nums.length; i++) {
            set.add(nums[i]);
        }
        int index = 0;
        for (Integer value : set) {
            nums[index] = value;
            index++;
        }
        return set.size();
    }
}
~~~

