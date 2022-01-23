第一题：

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

第二题：

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

第三题：

```
class Solution {
    public String toLowerCase(String s) {
        String s1 = s.toLowerCase();
        return s1;
 }
}
```

