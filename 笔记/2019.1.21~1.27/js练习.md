> # js的几个练习
## 1.翻转数组
+ ### a）通过push实现
        var arr = ['a','b','c','d','e'];
		function reverse (arr) {
			// 数组是先进后出
			var arr2 = [];
			for(var i = arr.length-1 ; i>=0 ; i--){
				// 从后面加入新元素
				arr2.push(arr[i]);
			}
			return arr2;
		}
> ###注意：push是将元素从后面放入数组中，类似于栈结构！！！！
+ ### b） 通过交换数组下标实现
        function reverse2(arr){
			for(var i = 0 ; i < Math.floor(arr.length/2) ; i++){
				var temp = arr[i];
				arr[i] = arr[arr.length-1-i];
				arr[arr.length-1-i] = temp;
			}
			return arr;
		}
> #### 此方法通过交换i和length-i位的元素来实现数组的翻转，可通过地板函数和length-1控制交换次数！！！
***
## 求阶乘
+ ### for循环求阶乘
        function jc(n){
			var total = 1;
			for(var i = 1 ; i <= n ; i++){
				total *= i;
			}

			return total;
		}
> #### 利用for循环控制阶乘的次数，用total*=i累计结算结果
+ ### 递归法求阶乘
        1的阶乘  jc(1)
		2  2*jc(1)
		3  3*jc(2)
		4  4*jc(3)


        function jcDg(n){
			if(n==1){
				return 1;
			}
			return n*jcDg(n-1);
		}
> #### 通过调用自己，实现n*n+1的累计结果，当n等于1时跳出循环。
> ### 注意：1.递归要有跳出条件！！！2.递归不适合很大的数，否则会造成内存溢出！！！
***
## 求阶乘的和
        function jc (n) {
			//跳出条件
			if(n==1){
				return 1;
			}
			return n*jc(n-1);
		}

		function jcSum(n){
			var sum = 0 ;
			for(var i = 1 ; i <= n ; i ++){
				sum += jc(i);
			}
			return sum;
		}
> #### 封装求阶乘的函数jc（），通过for循环累加每一次的阶乘的积。
***
## 斐波那契数列（兔子问题）
    1  1
	2  1
	3  2
	4  3
	5  5
	6  8	
	7  13
	8  21
    分析数据可知，从第3天起，每天兔子的数量等于前两天的兔子数量之和

    1  fb(1)  1
	2  fb(2)  1
	3  fb(3)  fb(1)+fb(2)
	4  fb(4)  fb(3)+fb(2)
	...
	n  fb(n)  fb(n-1)+fb(n-2)
    通过递归，将前两天的兔子和相加后再作为参数参与递归

    function fb (n) {
			if(n==1 || n==2){
				return 1;
			}
			return fb(n-1)+fb(n-2);
		}
> ### 利用递归的方法，将兔子数量从第一天开始每天累加
***
## 输入日期，判断天数
+ #### 问题分析：
        输入某年某月某日，判断这一天是这一年的第几天？（闰年）
    （四年一闰，百年不闰，四百年在闰）
    只有在闰年的时候366天  在2月29天多一天
    其余的时间2月都是28
    - 1.是否是闰年？
    - 2.每个月多少天？
+ #### 代码：
        1. 获取年月日 为字符串类型
        每个月的天数
		var monthDays = [31,28,31,30,31,30,31,31,30,31,30,31];
		var dateStr = prompt('请输入年月日: ','2019-01-24');
		
		alert('您输入的日期: '+dateStr+'在当前年份属于第'+getDayCount(dateStr)+'天');
		
		function getDayCount(dateStr){
			// 2. 把年月日字符串转换为日期类型  Object类型  2012-03-20
			var date = new Date(dateStr);
			// 3. 闰年
			// alert(isRun(2000));
			// 4. 获取每一个月的天数
			var year = date.getFullYear();
            注意：此处月数不用加1！！！
			var month = date.getMonth();
			var day = date.getDate();
			var rs = day;
            当月数为1时，i=0，month=0；所以for循环不会执行，此时天数等于day
			for(var i = 0 ; i < month ; i ++){
				rs += monthDays[i];
			}
			if(month>1){
				if(isRun(year)){
					rs ++;
				}
			}
			return rs;
		}
        判断是否为闰年
		function isRun (year) {
			return year%400==0 || (year%100!=0&&year%4==0);
		}
***
> # 补充
## 参数的类型 
    function foo (name,fn) {
			alert(name+ '啦啦啦');
			fn(name);
		}
		function bar(name){
			alert('Hi,'+name+',么么哒!');
		}
		函数体 本身也能作为参数传递,这种称之为 回调函数(了解)
		，在处理异步的情况使用最多
		foo('张三',bar);