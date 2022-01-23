#### [1332. 删除回文子序列](https://leetcode-cn.com/problems/remove-palindromic-subsequences/)

这个是我最初的想法，但是解题错误：原因在于想错了，  if(chs[i] == chs[j])  这里的意思想的时候想错了，想表达的是所有的一一对应的头尾相同，但是这个我写的表达的是只要有一个相同就return1.

```java
class Solution { //先确定，这题的答案只有0、1、2，但因为1<=s.length<=1000,可以直接不考虑0
    public int removePalindromeSub(String s) {
        char[] chs = s.toCharArray();    //将字符串转成数组
        //如果说这个字符串是按顺序排好的，像ababababa这种的话，用一次就够了，
        //除了这种情况外，其他的都要2次      
        for(int i = 0,j = chs.length-1;j>i;i++,j--){
            if(chs[i] == chs[j]){            
                return 1;
            }
            }
        return 2;
    }
}
```

后来，改了一下：通过！！！

```java
class Solution {         //先确定，这题的答案只有0、1、2，但因为1<=s.length<=1000,可以直接不考虑0
    public int removePalindromeSub(String s) {
        char[] chs = s.toCharArray();    //将字符串转成数组
        //字符串一个一个排好，只要出现一次一一对应的头尾不同，次数就是要了两次，
        //只有ababababaaba这种要求特别严格的才要1次    
        for(int i = 0,j = chs.length-1;j>i;i++,j--){
            if(chs[i] != chs[j]){          //这里不一样  
                return 2;
            }
            }
        return 1;
    }
}

```



#### [3. 无重复字符的最长子串](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/)

最初的想法：将字符串转成数组，一个一个进入一个数组。先让第一个字符进去，然后注意比较这个字符与下一个字符的，如果相同就不让她进去，如果不同的话，再进一步的验证，即将这个字符与这个数组中的其他字符比较，若这个数组中没有这个字符的存在，那么进去，若已经存在，就拒绝。然后多个数组的长度进行比较，输出最大的。

但是我好像实现不了。

```java
import java.util.Math;
class Solution {
    public int lengthOfLongestSubstring(String s) {
        int []sum;
        sum[0] = 1;
        char[] chs = s.toCharArray();    //将字符串转成数组
        if(chs == null ){
            return 0;
        }
        //一个一个进入一个数组。先让第一个字符进去，然后注意比较这个字符与下一个字符的，如果相同就不让她进去，如果不同的话，再进一步的验证，即将这个字符与这个数组中的其他字符比较，若这个数组中没有这个字符的存在，那么进去，若已经存在，就拒绝。然后多个数组的长度进行比较，输出最大的。
        for(int i =0; i<chs.length;i++){
            if(chs[i]==chs[i+1]){
              sum[i+1] +=1;
            }
        }
        Arrays.sort(sum);
        return sum[sum.length-1];
    }
}
```



别人写的：

```java
class Solution {
    public int lengthOfLongestSubstring(String s) {
          // 记录字符上一次出现的位置
        int[] last = new int[128];
        for(int i = 0; i < 128; i++) {
            last[i] = -1;
        }
        int n = s.length();

        int res = 0;
        int start = 0; // 窗口开始位置
        for(int i = 0; i < n; i++) {
            int index = s.charAt(i);
            start = Math.max(start, last[index] + 1);
            res   = Math.max(res, i - start + 1);
            last[index] = i;
        }

        return res;
    }
}
```







#### [13. 罗马数字转整数](https://leetcode-cn.com/problems/roman-to-integer/)

这题，我写了很多个版本，第一个是别人的，后面几个是我自己写的，很复杂又表达不出我要表达的，编译报错！！！

```java
class Solution {
    public int romanToInt(String s) {
        char[] chars = s.toCharArray();
        int num1 = 0,num2 = 0;
        int value = 0;
        for (int i = chars.length-1;i >= 0;i--){
            switch (chars[i]){
                case 'I' : num1 = 1;break;
                case 'V' : num1 = 5;break;
                case 'X' : num1 = 10;break;
                case 'L' : num1 = 50;break;
                case 'C' : num1 = 100;break;
                case 'D' : num1 = 500;break;
                case 'M' : num1 = 1000;break;
            }
            if (num2 <= num1){     //
                value += num1;
            }else{
                value -=num1;
            }
            num2 = num1;
        }
        return value;
    }
}
//真的写的很简单！！！
```



```
class Solution {
    public int romanToInt(String s) {
         char[] chs = s.toCharArray();    //将字符串转成数组
         HashMap<Character,Integer> h = new HashMap<>();
         for(int i=0;i<s.length();i++){
             if(h.containsKey(chs[i])){
                 Integer c = h.get(chs[i]);
                 ++c;
                 h.put(chs[i],c);
             }else{
                 h.put(chs[i],1);
             }
         } 
       int result= 4map.getValue(a) + 9map.getValue(b)+40map.getValue(c) +90map.getValue(d) +400map.getValue(e) +900map.getValue(f)+ map.getValue(g)+5map.getValue(h)+10map.getValue(i)+50map.getValue(j) +100map.getValue(k)+500map.getValue(l)+1000map.getValue(m);
    System.out.println(result);
    }
}
```





```java
class Solution {
    public int romanToInt(String s) {
         char[] chs = s.toCharArray();    //将字符串转成数组
         s = s.replace("IV","a");
         s = s.replace("IX","b");
         s = s.replace("XL","c");
         s = s.replace("XC","d");
         s = s.replace("CD","e");
         s = s.replace("CM","f");
         s = s.replace("I","g");
         s = s.replace("V","h");
         s = s.replace("X","i");
         s = s.replace("L","j");
         s = s.replace("C","k");
         s = s.replace("D","l");
         s = s.replace("M","m");


         //用哈希表创建映射对象
         HashMap<Character,Integer> map = new HashMap<>();
         for(int i=0;i<s.length();i++){
             //判断是否已经存在该字符
             if(map.containsKey(chs[i])){
                 //存在的话，值+1，覆盖之前的映射
                 //map.get(chs[i])根据键返回值，+1
                map.put(chs[i],map.get(chs[i]));

         }else{
             //不存在，添加元素，值为1
             map.put(chs[i],1);
         }
      
    }
    //调用方法把映射中的所有键存放在Set集合中
    Set<Character> set = map.keySet();
    //遍历Set集合
    for(int i =0;i<chs.length;i++){
        return s ;
        return map.get(s) ;
    }
    int result = 4map.get(a) + 9map.get(b)+40map.get(c) +90map.get(d) +400map.get(e) +900map.get(f)+ map.get(g)+5map.get(h)+10map.get(i)+50map.get(j) +100map.get(k)+500map.get(l)+1000map.get(m);
    System.out.println(result);
    }
}
```

这个版本，emmmm编译报错，但不清楚哪里错了（虽然看着这么多就很容易出错的样子）

```java
class Solution {0
    public int romanToInt(String s) {
        int result;
         char[] chs = s.toCharArray();    //将字符串转成数组
         s = s.replace("IV","a");
         s = s.replace("IX","b");
         s = s.replace("XL","c");
         s = s.replace("XC","d");
         s = s.replace("CD","e");
         s = s.replace("CM","f");
         s = s.replace("I","g");
         s = s.replace("V","h");
         s = s.replace("X","i");
         s = s.replace("L","j");
         s = s.replace("C","k");
         s = s.replace("D","l");
         s = s.replace("M","m");
         Map<Character,Integer> map = new HashMap<>();
         for(int i=0;i<s.length;i++){
             char chs=s.cahAt(i);
             if(map.get(chs) != null){
                 map.put(chs,map.get(chs)+1);
             }else{
                 map.put(chs,1);
             }
         }
         for(Map.Entry<Character,Integer> en:map.entrySet()){
             return en.getKey();
             return en.getValue();
         }
         result = 4map.getValue(a) + 9map.getValue(b)+40map.getValue(c) +90map.getValue(d) +400map.getValue(e) +900map.getValue(f)+ map.getValue(g)+5map.getValue(h)+10map.getValue(i)+50map.getValue(j) +100map.getValue(k)+500map.getValue(l)+1000map.getValue(m);
    System.out.println(result);
    }
}
    
```

