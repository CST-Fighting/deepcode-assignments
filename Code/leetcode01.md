### 第一题:

#### [1. 两数之和](https://leetcode-cn.com/problems/two-sum/)

思路：一个数组nums中要两个数相加=target，可以用双层循环解决，两层循环的次数不同，外层循环为nums[i],用于控制轮数；内层循环为nums[j]，用于遍历数组中的元素，每多一次循环，j减一。

内部循环依赖受控于外部循环。外部循环控制结果出现几行，内部循环控制每行出现的个数。外部循环条件为(int i = 0;i<nums.length;i++)，内部循环条件为（j=nums.length;j>i;j++）。当i=0，取值为j>0的数，以nums.length逐一递减，以此列推。

例如：以一个长度为3的数组arr为例：

<img src="C:\Users\86134\Desktop\heima\T1.png" style="zoom:200%;" />

```
class Solution {
    public int[] twoSum(int[] nums, int target) {
         int []temps =new int[2];
       for(int i = 0;i<nums.length;i++){
           for(int j =nums.length-1;j>i;j--){
               if(nums[i]+nums[j] == target){
                   temps[0]=i;
                   temps[1]=j;
                   return temps;
               }
           }
       }
       return temps;
    }
}
```



### 第二题：

#### [20. 有效的括号](https://leetcode-cn.com/problems/valid-parentheses/)

理解题目：括号成对

代码思路：

1）先创建一个栈内存【利用栈的后进先出的思想】

2）遍历每个字符，判断是否入栈。如果是左括号就入栈，如果是右括号就取出栈顶元素，然后判断每个字符是否配对，有三种情况，所以可以用if语句表达。

3）考虑栈内存为empty的情况

4）打印输出返回Boolean值

```
import java.util.Stack;

class Solution {
    public static boolean isValid(String s) {
        # 1. 创建一个栈
        Stack<Character> stack = new Stack<>();
        #2. 循环遍历每个字符
        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            # 3. 如果是左括号, 就入栈
            if (c == '(' || c == '[' || c == '{') {
                stack.push(c);
                continue;
            }
            if (stack.isEmpty()) {
                #不匹配的情况
                return false;
            }
            char top = stack.pop();
            # 5. 检查栈顶元素和当前元素是不是配对的
            if (top == '(' && c == ')') {
                continue;
            }
            if (top == '[' && c == ']') {
                continue;
            }
            if (top == '{' && c == '}') {
                continue;
            }
            # 如果以上三种情况都不符合, 那就是非法字符串
            return false;
        }  
        if (stack.isEmpty()) {
            return true;
        }
        return false;
    }
  }
```

在网上看到别人写的代码，不是很懂：

```
class Solution {
    public boolean isValid(String s) {
        int length = s.length() / 2;
        for(int i =0;i <length;i++){
            s = s.replace("()","").replace("{}","").replace("[]","");
        }
        return s.length() ==0;
    }
}
```



### 第三题：

#### [709. 转换成小写字母](https://leetcode-cn.com/problems/to-lower-case/)

就是用了一个toLowerCase()方法

```
class Solution {
    public String toLowerCase(String s) {
        String s1 = s.toLowerCase();
        return s1;
 }
}
```

