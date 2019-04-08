#最后一个单词的长度

> 给定一个仅包含大小写字母和空格 `' '` 的字符串，返回其最后一个单词的长度。
>
> 如果不存在最后一个单词，请返回 0 。

## 解题思路

> 直接利用split切分，如果不为空就返回最后一个的长度

## 代码

~~~java
class Solution {
    public int lengthOfLastWord(String s) {
        String[] strArr = s.split(" ");
        if (strArr.length > 0) {
            return strArr[strArr.length - 1].length();
        }
        return 0;
    }
}
~~~

