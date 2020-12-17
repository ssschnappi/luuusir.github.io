# 12.15

## boolean

1.布尔对象的生成

```JavaScript
var bool = new Boolean(true)
```

2.`!`的用法

- 取反
- 强制类型转换，把其他类型转换为Boolean类型

```JavaScript
console.log(!false);//true

var obj = {}
console.log(!obj);//false
```

## number

```javascript
        // 类型转换
        console.log(Number('123'));

        // 使用new关键字，创建一个number类型对象(数字对象)
        var num = new Number(5);
        console.dir(num);

        // 直接使用number()函数，不使用new关键字，创建的是一个数字
        var num1 = Number(2);
        console.dir(num1);
        console.dir(typeof num1);

        // 数字和数字对象的计算结果是数字
        console.log(num + num1);

        // 数字对象中，传递的参数如果不是数字类型的，number会做类型转换。
        num = new Number(true);
        num = new Number('123');
        console.log(num);

        var num2 = 5.169455;
        // 把数字转化为字符串类型
        console.log(num2.toString());
        // 以四舍五入方式保留小数点后几位数，并转化为字符串类型
        console.log(num2.toFixed(2));
        // 转化为指数形式，并转化为字符串类型
        console.log(num2.toExponential());
        // 判断是不是整数，返回布尔值
        console.log(Number.isInteger(num2));
        // 从字符串中解析，保留整数
        console.log(Number.parseInt('-121.45.aaf522'));
        // 从字符串中解析，保留小数
        console.log(Number.parseFloat('121.45.aaf522'));
        // 共保留几位有效数字(四舍五入保留)
        console.log(num2.toPrecision(3));
        // 转化为指数形式，并转化为字符串类型，同时保留几位小数
        console.log(num2.toExponential(2));
        // 最大值(+=)
        console.log(Number.MAX_VALUE);
        // 最小值(-=)
        console.log(-Number.MAX_VALUE);
        // 最小值，无限接近于0
        console.log(Number.MIN_VALUE);
```

## 排序

### 冒泡排序

相邻的数字两两比较，按照从小到大的顺序进行交换，一趟比较之后，最大或者最小的数字被交换到最后一位，然后再从头开始进行两两比较，直到倒数第二位时结束
![冒泡](https://www.runoob.com/wp-content/uploads/2019/03/bubbleSort.gif)

```JavaScript
function bubbleSort(arr) {
    var len = arr.length;
    for (var i = 0; i < len - 1; i++) {
        for (var j = 0; j < len - 1 - i; j++) { //j < len - 1 - i,最大的已排序后就不用排了，即减一
            if (arr[j] > arr[j+1]) {        // 相邻元素两两对比
                var temp = arr[j+1];        // 元素交换
                arr[j+1] = arr[j];
                arr[j] = temp;
            }
        }
    }
    return arr;
}
```

### 选择排序

首先在未排序序列中找到最小（大）元素，存放到排序序列的起始位置。再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾。重复第二步，直到所有元素均排序完毕。

![选择](https://www.runoob.com/wp-content/uploads/2019/03/selectionSort.gif)

```JavaScript
function selectionSort(arr) {
    var len = arr.length;
    var minIndex, temp;
    for (var i = 0; i < len - 1; i++) {
        minIndex = i;
        for (var j = i + 1; j < len; j++) {
            if (arr[j] < arr[minIndex]) {     // 寻找最小的数
                minIndex = j;                 // 将最小数的索引保存
            }
        }
        temp = arr[i];
        arr[i] = arr[minIndex];
        arr[minIndex] = temp;
    }
    return arr;
}
```

```JavaScript

```
