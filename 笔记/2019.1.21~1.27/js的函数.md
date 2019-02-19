> # js的函数
### 1.函数的基本样式
    function say(){
			alert('Hello,world!');
		}
		say();
> #### 注意：函数使用需要声明和调用，如果只声明不调用，函数是不会执行的。js没有java等后台语言的继承，封装，多态的特点
### 2.函数的声明
+ 自定义函数
        可以先使用，后声明
            function  say(){
			alert('hello,world!');
		}
+ 匿名函数
    必须先声明，后使用
    var run = function(){
			alert('Hi  i  am  running...');
		}
		run();
>> 注意：通常使用自定义函数，自定义函数可以先使用，而匿名函数必须先声明才能使用，所以自定义函数能使代码更工整。
### 3.函数的参数
        function add(x,y){
			alert(x+'+'+y+'='+(x+y));
		}
        add(3,5);
#### 上面的xy是形参，而3，5是实参
> #### 注意：如果实参比形参多，多余的实参会被忽略，如果形参比实参多，则程序会报错。使用时一般实参形参一样多。
> # 注意：js里面没有方法重载，函数名重复时后面的方法会覆盖前面的方法。而其他后台语言如java则会正常当做两个方法！！！
### 4.函数的返回值
        用于返回函数的执行结果，可以外部使用，但是return后面的代码将不会执行！！！
### 5.函数变量的作用域
#### script标签可以认为是js的window对象
        1. 在window对象里声明的变量,在函数里都可以使用
        2. 函数内部不能调用其他函数内部的变量
	    3. 在window作用域不能调用函数内部的变量

> # 函数排序
> ## 选择排序
        var arr = [1,8,5,7,4,3,2];

		// 0 1 2 3 4 
		for(var j = 0 ; j < arr.length-1 ; j++){
			// 默认最小值的下标为 0 
			var minIndex = j;
			for(var i = 1+j ; i < arr.length ; i ++){
				if(arr[minIndex]>arr[i]){
					//让贤
					minIndex = i;
				}
			}
			//如果最小下标依然是j 就没必要交换位置
			if(j!=minIndex){
				//放到第一个位置
				var temp = arr[j];
				arr[j] = arr[minIndex];
				arr[minIndex] = temp;
			}
			
			console.log('获取了最小下标为'+minIndex);
			console.log(arr);
		}
		console.log('最终结果为:',arr);

> ## 冒泡排序
        var arr = [8,5,4,3,2];

	    for(var j = 1 ; j < arr.length ; j ++){
	    	for(var i = 0 ; i < arr.length-j ; i++){
	    		if(arr[i]>arr[i+1]){
	    			//交换位置
	    			var temp = arr[i];
	    			arr[i] = arr[i+1];
	    			arr[i+1] = temp;
	    		}
	    	}
    		console.log('第'+j+'轮的结果',arr);
	    }
	    console.log('最终结果',arr);
		
