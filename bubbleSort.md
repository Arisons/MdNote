####理解冒泡排序的原理####
>简言之，每次两两比较都把较大的放在后面（形成新的数组）;
>每次循环的次数都是数组的长度减 1 ;
>>以下代码引用自[百度百科](http://baike.baidu.com/link?url=_z0cC9C5hspOZLjkIUo84TFCqqr2h-agoxq7TbF7b2P0XxQLXNP3NP7R_TqqBztSMI_cq3A3x5tvsZm4dHCzQq "冒泡排序") （稍有改动）

	function bubbleSort(arr) {
        var i = arr.length, j;
        var tempExchangVal;
        while (i > 0) {
            for (j = 0; j < i - 1; j++) {
                console.log(arr);
                console.log(arr[j]);
                console.log(arr[j+1]);
                if (arr[j] > arr[j + 1]) {
                    tempExchangVal = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = tempExchangVal;
                }
                console.log(arr);
            }
            i--;
            console.log(i);
        }
        return arr;
    }

    var arr = [3, 2, 4, 9, 1, 5, 7, 6, 8];
    var arrSorted = bubbleSort(arr);
    console.log(arrSorted);

从输出语句可以看出，每次排序中发生的变化；