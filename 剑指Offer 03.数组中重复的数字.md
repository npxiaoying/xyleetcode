```java
class Solution {
    public int findRepeatNumber(int[] nums) {
        Set<Integer> set = new HashSet<>();
        int repeat = -1;
        for(int i=0;i<nums.length;i++){
            if(!set.add(nums[i])){
                repeat = nums[i];
                break;
            }
        }
        return repeat;
    }
}
```

题目链接：

https://leetcode.cn/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/

思路：

遍历数组，将数组中所有的值都存入Set集合中，如果Set集合添加失败则代表该元素重复，记录该重复数字，退出循环，返回结果。