# moveZeroes
> 给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。


示例

```
输入: [0,1,0,3,12]
输出: [1,3,12,0,0]
```

说明： 
    空间复杂度为O(1)
    时间复杂度为O(n)
    
    
================================================

看到这道题 第一反应就是 新建一个额外的数组然后循环判断 ！= 0 就存放，然后赋值给原数组 easy
但是要求是 空间复杂度为O(1)

这里改进的方法是利用这个指定的空间 创建一个 下标i ,来指定*结果数组*进度

遍历当前数组 当 item ！= 0 的时候 结果下标i 前进一位 ，进行交换

目前我的第一遍答案 还有点问题 刷二遍的时候更新
 
第一刷
```swift
class Solution {
func moveZeroes(_ nums: inout [Int]) {
    var j = 0

    for i in 0 ..< nums.count {
        if nums[i] == 0 {
            continue
            }
        let temp = nums[j]
        nums[j] = nums[i]
        nums[i] = temp
        j += 1
        }
    }
}
```

    
    
