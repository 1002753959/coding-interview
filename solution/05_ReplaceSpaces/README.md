## 替换空格

### 题目描述
请实现一个函数，将一个字符串中的每个空格替换成 `%20`。例如，当字符串为 `We Are Happy`，则经过替换之后的字符串为 `We%20Are%20Happy`。


### 解法
创建 `StringBuilder`，遍历原字符串，遇到非空格，直接 append 到 `StringBuilder` 中，遇到空格则将 `%20` append 到 `StringBuilder` 中。

> 🤔思路扩展：
在合并两个数组（包括字符串）时，如果从前往后复制每个数字（或字符）需要重复移动数字（或字符）多次，那么我们可以考虑从后往前复制，这样就能减少移动的次数，从而提高效率。

```java
/**
 * @author bingo
 * @since 2018/10/27
 */

public class Solution {
    /**
     * 将字符串中的所有空格替换为%20
     * @param str 字符串
     * @return 替换后的字符串
     */
    public String replaceSpace(StringBuffer str) {
        if (str == null || str.length() == 0) {
            return str.toString();
        }
        StringBuilder sb = new StringBuilder();
        int len = str.length();
        for (int i = 0; i < len; ++i) {
            char ch = str.charAt(i);
            sb.append(ch == ' ' ? "%20" : ch);
        }

        return sb.toString();
    }
}
```

### 测试用例
1. 输入的字符串包含空格（空格位于字符串的最前面/最后面/中间；字符串有多个连续的空格）；
2. 输入的字符串中没有空格；
3. 特殊输入测试（字符串是一个空指针；字符串是一个空字符串；字符串只有一个空格字符；字符串中有多个连续空格）。