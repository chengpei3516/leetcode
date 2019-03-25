# 最长公共前缀

> 题目描述：编写一个函数来查找字符串数组中的最长公共前缀。如果不存在公共前缀，返回空字符串 `""`。

## 解题思路

> 循环遍历数组中的字符串，比较相同索引的值是否相等

## 代码

~~~
class Solution {
    public String longestCommonPrefix(String[] strs) {
        String commonPrefix = "";
        int i = 0;
        int index = 0;
        if (strs.length == 0) {
            return commonPrefix;
        }
        if (strs.length == 1) {
            return strs[0];
        }
        while (true) {
            int length = strs[i].length() > strs[i + 1].length() ? strs[i + 1].length() : strs[i].length();
            if (index < length) {
                if (strs[i].charAt(index) != strs[i + 1].charAt(index)) {
                    break;
                }
                if (i == strs.length - 2) {
                    i = 0;
                    commonPrefix += Character.toString(strs[i].charAt(index));
                    index += 1;

                } else {
                    i++;
                }
                continue;
            }
            break;
        }

        return commonPrefix;
    }
}
~~~

