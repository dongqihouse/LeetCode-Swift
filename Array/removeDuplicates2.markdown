# removeDuplicates2

> 给定一个排序数组，你需要在原地删除重复出现的元素，使得每个元素只出现2次，返回移除后数组的新长度。
> 不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。


```
给定 nums = [0,0,1,1,1,1,2,3,3],

函数应返回新长度 length = 7, 并且原数组的前五个元素被修改为 0, 0, 1, 1, 2, 3, 3 。

你不需要考虑数组中超出新长度后面的元素。
```

这个leetcode 给的中等标签 很烦 思路是双下表 但是判断条件 怎么都想不好 。
贴一个大佬的答案 真是精髓啊

这个解答 对着 画画草图 真的很吊。 比中文版那个X度 提供的答案 好太多
第一刷 失败
```swift
class Solution {
    func removeDuplicates(_ nums: inout [Int]) -> Int {

        var i = 0

        for item in nums {
            if i < 2 || item > nums[i-2] {
                nums[i] = item
                i += 1
            }
        }

    return i


    }
}
```
