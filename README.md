# 冒泡排序

冒泡排序（Bubble Sort）也是一种简单直观的排序算法。它重复地走访过要排序的数列，一次比较两个元素，如果他们的顺序错误就把他们交换过来。走访数列的工作是重复地进行直到没有再需要交换，也就是说该数列已经排序完成。这个算法的名字由来是因为越小的元素会经由交换慢慢“浮”到数列的顶端。

## PHP 代码实现

```php
function bubbleSort($arr)
{
    $count = count($arr);
    if ($count == 0) return false;
    // 设置一个空数组 用来接收冒出来的泡
    $tmp = [];
    // 该层循环控制 需要冒泡的轮数
    for ($i = 0; $i < $count; $i++) {
        //该层循环用来控制每轮 冒出一个数 需要比较的次数
        for ($j = 0; $j < $count - 1 - $i; $j++) {
            if ($arr[$j] > $arr[$j + 1]) {
                $tmp = $arr[$j];
                $arr[$j] = $arr[$j + 1];
                $arr[$j + 1] = $tmp;
            }
        }
    }
    return $arr;
}

$arr = [6, 3, 8, 2, 9, 1];
print_r(bubbleSort($arr));
```

## JavaScript 代码实现

```js
function bubbleSort(arr) {
    var len = arr.length;
    for (var i = 0; i < len; i++) {
        for (var j = 0; j < len - 1 - i; j++) {
            if (arr[j] > arr[j+1]) {        // 相邻元素两两对比
                var temp = arr[j+1];        // 元素交换
                arr[j+1] = arr[j];
                arr[j] = temp;
            }
        }
    }
    return arr;
}
var arr = [6, 3, 8, 2, 9, 1];
console.log(bubbleSort(arr)); // 打印结果 [1, 2, 3, 6, 8, 9]
```

## Python 代码实现

```python
def bubbleSort(arr):
    for i in range(1, len(arr)):
        for j in range(0, len(arr)-i):
            if arr[j] > arr[j+1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
    return arr
```

## Go 代码实现

```go
package main

import "fmt"

func bubbleSort(arr []int) []int {
	length := len(arr)
	for i := 0; i < length; i++ {
		for j := 0; j < length-1-i; j++ {
			if arr[j] > arr[j+1] {
				arr[j], arr[j+1] = arr[j+1], arr[j]
			}
		}
	}
	return arr
}

func main() {
	arr := []int{1, 3, 9, 5, 66, 4}
	fmt.Printf("%+v", bubbleSort(arr)) // [1 3 4 5 9 66]
}
```