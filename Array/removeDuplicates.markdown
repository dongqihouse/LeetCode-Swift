# removeDuplicates

> 给定一个排序数组，你需要在原地删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。
> 不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。


```
给定 nums = [0,0,1,1,1,2,2,3,3,4],

函数应该返回新的长度 5, 并且原数组 nums 的前五个元素被修改为 0, 1, 2, 3, 4。

你不需要考虑数组中超出新长度后面的元素。
```

移除重复元素 并且规定了空间复杂度 其实也是用双下标就搞定了 没啥大问题 


第一刷
```swift
class Solution {
    func removeDuplicates(_ nums: inout [Int]) -> Int {     

        if (nums.count == 0) { return 0 }

        var size = 0

        for index in 0 ..< nums.count {
            if (nums[index] != nums[size]) {
            size += 1
            nums[size] = nums[index]
            }
        }  

        return size + 1
    }
}
```
