#### 21.合并两个链表

https://leetcode-cn.com/problems/merge-two-sorted-lists/comments/

解题思路：

1）基本思路：指针、迭代

2）两个链表是非递减的

3）先分析list1跟list2链表为空的情况。

4）list表不为空时。先生成ListNode链表对象，创建首节点，节点的val为0，并声明一个变量用来在移动过程中指向当前节点。然后将list1.val跟list2.val逐一比较，改变指针的指向，如果list1.val大，那么cur.next就等于list1,即将指针指向它，其他同理。

```java
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        if(list1 == null){
            return list2;
        }
        if(list2 == null){
            return list1;
        }
        //生成ListNode链表对象，创建首节点，节点的val为0
        ListNode head=new ListNode(0);
        //声明一个变量用来在移动过程中指向当前节点
        List cur;
        //指向首节点
        ListNode cur=head;
        while(list1!=null && list2!=null){
            if(list1.val<list2.val){
                cur.next=list1;
                list1=list1.next;
            }else{
                cur.next=list2;
                list2=list2.next;
            }
            cur=cur.next;
            
        }
        cur.next=list1 == null?list2:list1;
        return head.next;
    }
}
```

#### [67. 二进制求和](https://leetcode-cn.com/problems/add-binary/)

思路：方法很直接，就是利用大数值BigInteger构造方法转换进制

```java
import java.math.BigInteger;
class Solution {
    public String addBinary(String a, String b) {
        BigInteger x = new BigInteger(a,2);   //a为值，2为进制
        BigInteger y = new BigInteger(b,2);
        return x.add(y).toString(2);
 
    }
}
```

```
同类：BigInteger(20,2)  ,将十进制的20转换成2进制
```

#### [53. 最大子数组和](https://leetcode-cn.com/problems/maximum-subarray/)

1)基本思路：每加一个数就跟没加这个数之前的和进行比较，如果加了这个数之后这个和比之前的小了，那么保留之前那个数，然后加了的那个数的和继续往下加一个数，然后再次跟最初的那个比较，以此类推。（核心思想：贪心算法）

```java
class Solution {
    public int maxSubArray(int[] nums) {
     int result =Integer.MIN_VALUE;
     int sum = 0;
     for(int i=0;i<nums.length;i++){
         sum += nums[i];
         result = Math.max(result,sum);
         if(sum < 0){
             sum = 0;
         }
     }
     return result;
    }
}
```

