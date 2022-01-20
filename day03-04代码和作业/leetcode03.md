第一题：

思路：

```
 public ListNode deleteDuplicates(ListNode head) {
        
        ListNode cur = head;
        while(cur!=null&&cur.next !=null){
            if(cur.val == cur.next.val){
                cur.next = cur.next.next;   
            }else{
                cur = cur.next;
            }    

        }

        return head;
       
    }
```

第二题：

```
class Solution {

    List<Integer> list = new ArrayList<>();
    public Solution(ListNode head) {
        for (ListNode ln = head; ln != null; ln = ln.next) list.add(ln.val);
    }
    public int getRandom() {
        return list.get((int) (Math.random() * list.size()));
    }
}
```

