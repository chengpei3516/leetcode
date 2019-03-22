# 回文数

> 题目描述：判断一个整数是否是回文数。回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。

## 解题思路

> 把参数转为字符串，然后反转，比较两个字符串的值是否相等。

~~~java
class Solution {
    public boolean isPalindrome(int x) {
      
        String source = Integer.toString(x);
        String reverse = new StringBuffer(source).reverse().toString();
        if (source.equals(reverse)){
            return true;
        }
        return false;
    }
}
~~~

> 反转参数的后一半，比较前一半和后一半是否相等。

~~~java
class Solution {
    public boolean isPalindrome(int x) {
       if (x < 0 || (x % 10 == 0 && x != 0)) {
            return false;
        }
        int target = 0;
        while (x > target) {
            target = target * 10 + x % 10;
            x = x / 10;
        }
        return x == target || x == target / 10 ;
        }
    
}
~~~

