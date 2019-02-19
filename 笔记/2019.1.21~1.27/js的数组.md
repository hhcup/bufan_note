> # js的数组
***
> ## js数组的声明
+ ### 1.通过对象形式创建数组
        var arr = new Array();
+ ### 2. 直接创建空的数组
        var arr=[1,2,3,4];
>> ### 注意：1.数组的下标是从0开始的  2.数组可以通过下标赋值，也可以通过下标取值！
        eg：arr[1]=22;
            console.log(arr[1]);
> ## js数组的遍历
+ ### 1.通过循环遍历数组
        for(var i = 0 ; i < arr.length ; i++){
			console.log('下标为'+i,arr[i]);
		}
+ ### 2.for....in
        for(var a in arr){
			console.log(arr[a])
		}
> ## js数组常用的方法
+ ### 1.concat()数组的拼接
        拼接数组，并不能影响到原来的数组，所以需要声明一个新数组来接收拼合后的数组。
        var arr = [1,2,3];
		var arr2 = [4,5,6];
        var arr3 = arr.concat(arr2);
		console.log(arr);
		console.log(arr3);

> ## 数组的常见方法
        1. push()   从后面推进去
        2. unshift()  从数组的前面放入
        3. pop()    删除最后一个元素
        4. shift()   删除第一个元素
>## 数组与字符串的转换
### 1.join
        join可以把数组转换为字符串
        var arr = [1,3,5,6,7];
        var str = arr.join('');==>1,3,5,6,7
        如果单引号内没有参数，则会默认逗号隔开
### 2.split
        split 打断 可以把字符串转换为数组
        var str2 = 'Hi  i am  fine  today';
	    var str3 = 'a|b|c|d|e'; 
        var arr2 = str2.split(' ');
	    var arr3 = str3.split('|');
        console.log(arr2);==>["Hi", "i", "am", "fine", "today"]
	    console.log(arr3);==>["a", "b", "c", "d", "e"]
        注意: 空格 也算字符