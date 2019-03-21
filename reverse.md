# 整数反转

> 题目描述：给出一个 32 位的有符号整数，你需要将这个整数中每位上的数字进行反转。
>
> 假设我们的环境只能存储得下 32 位的有符号整数，则其数值范围为 [−231,  231 − 1]。请根据这个假设，如果反转后整数溢出那么就返回 0。

## 解题思路

> 把int类型的数据转化为StringBuffer;调用reverse方法进行反转，然后在转回为int ，如果抛出异常则说明反转之后的整数超出范围，则返回0。

## 代码

~~~java
class Solution {
    public int reverse(int x) {
      int result = 0;
        try {
            if (x >= 0) {
                result = Integer.parseInt(new StringBuffer(Integer.toString(x)).reverse().toString());
            } else {
                result = -(Integer.parseInt(new StringBuffer(Integer.toString(-x)).reverse().toString()));
            }
        } catch (Exception e) {
            return result;
        }

        return result;  
    }
}
~~~

