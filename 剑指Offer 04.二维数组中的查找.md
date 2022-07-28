```java
class Solution {
    public boolean findNumberIn2DArray(int[][] matrix, int target) {
        if(matrix == null || matrix.length == 0 || matrix[0].length == 0){
            return false;
        }
        int rows = matrix.length;
        int columns = matrix[0].length;
        int row = 0, column = columns - 1;
        while(row < rows && column >= 0){
            int value = matrix[row][column];
            if(value == target){
                return true;
            } else if(value > target){
                column--;
            } else {
                row++;
            }
        }
        return false;
    }
}
```

题目链接：

https://leetcode.cn/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/

思路：

遍历数组，从二维数组的右上角开始遍历寻找，当前遍历值大于目标值向左移动，当前遍历值小于目标值向下移动，当前遍历值等于目标值则返回true,如果一直没找到则返回false