#### [349. 两个数组的交集](https://leetcode-cn.com/problems/intersection-of-two-arrays/)

1)因为返回的交集的数字不能重合，而Set集合中的对象不按特定的方式排序且不能包含重复的对象，所以确定采用Set集合中的HashSet实现Set接口

2)分两种情况：一是数组为空或者数组长度为0，二是数组不空

3）数组不空：先定义两个哈希接口： Set<Integer> set1 = new HashSet<>();
                                                                 Set<Integer> resSet = new HashSet<>();

4）遍历第一个数组，将数组中的对象输入到第一个哈希接口set1中（同时会过滤掉重复的对象）

5）遍历第二个数组，同时判断是否存在set1中的元素，若有将该元素加入到reSet哈希接口中

5）定义一个resArr数组，将reSet的个数定义为该数组的长度。

6）遍历resArr数组，打印输出重复的元素

```
import java.util.HashSet;
import java.util.Set;

class Solution {
    public int[] intersection(int[] nums1, int[] nums2) {
        if (nums1 == null || nums1.length == 0 || nums2 == null || nums2.length == 0) {
            return new int[0];
        }
        Set<Integer> set1 = new HashSet<>();
        Set<Integer> resSet = new HashSet<>();
        //遍历数组1
        for (int i : nums1) {
            set1.add(i);
        }
        //遍历数组2的过程中判断哈希表中是否存在该元素
        for (int i : nums2) {
            if (set1.contains(i)) {
                resSet.add(i);
            }
        }
        int[] resArr = new int[resSet.size()];
        int index = 0;
        //将结果转为数组
        for (int i : resSet) {
            resArr[index++] = i;
        }
        return resArr;
    }
}
```



#### [88. 合并两个有序数组](https://leetcode-cn.com/problems/merge-sorted-array/)

1）确定思路：先合并两个有序数组，再用冒泡排序实现排序

2）定义两个数组num1，num2,以及其长度，遍历数组num2,将num2中的元素合并到num1。

3）用冒泡排序Arrays.sort()算法

```
// 直接合并后排序
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        for (int i = 0; i != n; ++i) {
            nums1[m + i] = nums2[i];
        }
        Arrays.sort(nums1);
    }
}
```



补充知识：

使用R中的merge（）函数合并数据，可在两个不同的数据框中标识共同的列或行

使用merge（）获取数据集中交叉部分

x: 第一个数据框.

y: 第二个数据框.

by, by.x, by.y: 指定两个数据框中匹配列名称。缺省使用两个数据框中相同列名称。

all, all.x, all.y: 指定合并类型的逻辑值。缺省为false，all=FALSE (仅返回匹配的行)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   

```
merge() 函数支持4种类型数据合并:

Natural join: 仅返回两数据框中匹配的数据框行，参数为：all=FALSE.

Full outer join: 返回两数据框中所有行， 参数为： all=TRUE.

Left outer join: 返回x数据框中所有行以及和y数据框中匹配的行，参数为： all.x=TRUE.

Right outer join: 返回y数据框中所有行以及和x数据框匹配的行，参数为： all.y=TRUE.


```





#### [234. 回文链表](https://leetcode-cn.com/problems/palindrome-linked-list/)

1）思路：使用数组和指针

2）定义链表的长度int len,和头结点ListNode cur = head;

3)如果头结点为不为null，则用while（）循环到最后一个元素，直至cur=head;

4)将循环找到的cur=head是的len作为新数组res的长度，并将元素加到数组res当中，遍历循环数组。

5）比较回文。（回文：正着跟倒着念一样。）用for循环将数组对半比较，头尾比较，向中间靠。

```
// 方法一，使用数组
class Solution {
    public boolean isPalindrome(ListNode head) {
        int len = 0;
        // 统计链表长度
        ListNode cur = head;
        while (cur != null) {
            len++;
            cur = cur.next;
        }
        cur = head;
        int[] res = new int[len];
        // 将元素加到数组之中
        for (int i = 0; i < res.length; i++){
            res[i] = cur.val;
            cur = cur.next;
        }
        // 比较回文
        for (int i = 0, j = len - 1; i < j; i++, j--){
            if (res[i] != res[j]){
                return false;
            }
        }
        return true;
    }
}

```



这个看着很高级，先放在这儿。

```
// 方法二，快慢指针
class Solution {
    public boolean isPalindrome(ListNode head) {
        // 如果为空或者仅有一个节点，返回true
        if (head == null && head.next == null) return true;
        ListNode slow = head;
        ListNode fast = head;
        ListNode pre = head;
        while (fast != null && fast.next != null){
            pre = slow;  // 记录slow的前一个结点
            slow = slow.next;
            fast = fast.next.next;
        }
        pre.next = null;  // 分割两个链表

        // 前半部分
        ListNode cur1 = head;
        // 后半部分。这里使用了反转链表
        ListNode cur2 = reverseList(slow);

        while (cur1 != null){
            if (cur1.val != cur2.val) return false;

            // 注意要移动两个结点
            cur1 = cur1.next;
            cur2 = cur2.next;
        }
        return true;
    }
    ListNode reverseList(ListNode head){
        // 反转链表
        ListNode tmp = null;
        ListNode pre = null;
        while (head != null){
            tmp = head.next;
            head.next = pre;
            pre = head;
            head = tmp;
        }
        return pre;
    }
}
```

![img](https://pic.leetcode-cn.com/1632295761-FFtzDW-234.%E5%9B%9E%E6%96%87%E9%93%BE%E8%A1%A8.png)