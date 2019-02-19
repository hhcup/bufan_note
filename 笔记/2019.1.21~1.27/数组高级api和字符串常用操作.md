> # 1.数组高级api
        var arr = [3,1,5,7];
	    var arr2 = ['a','adda','ac','a','a','ccd','ab','cc'];
## 1.toString()
    把数组转换成字符串，每一项用,分割。console.log(arr.toString());==>3,1,5,7
## 2.reverse()
    翻转数组  会影响数组本身
    console.log(arr.reverse());==>[7, 5, 1, 3]
## 3.sort();
    给数组排序，返回排序后的数组。如何排序看参数。
    arr.sort(function (a,b) {
			return a-b;
	})
### 4.indexOf()查找元素在数组中第一次出现的位置
###  lastIndexOf()查找元素在数组中最后一次出现的位置
> ### 注意：如果没找到返回-1


## 4.slice()从当前数组中截取一个新的数组
    不影响原来的数组，参数start从0开始,end从1开始
    var arr3 = arr2.slice(3,5);
    splice()删除或替换当前数组的某些项目，参数start,deleteCount,options(要替换的项目)
		删除"ac"
		arr2.splice(3,1);
### splice删除并替换
    arr2.splice(3,1,'abc');
***
## 清空数组
    1. arr.length = 0 ;
    2. arr = []; 常用
***
# 2.字符串常用操作
    var str = 'abcdefaasdfsdfasdfsdfsadfasdfg';
+ ### charAt获取相应位置字符
    console.log(str.charAt(5));==>f
+ ### charCodeAt  对应位置的ASCII编码
    console.log(str.charCodeAt(1));==>98
+ ### indexOf  返回字符在字符串中的位置
    console.log(str.indexOf('bc'));==>1
+ ### slice()	  方法可提取字符串的某个部分，并以新的字符串返回被提取的部分。用法同数组。
+ ### substr() 用的非常多 从m开始截取n个元素
    var str2 = str.substr(0,str.length-1);
		console.log(str2);==>abcdefaasdfsdfasdfsdfsadfasdf
***
## 作业练习
### 找出元素在数组中出现的次数并打印。
+ ### 1.方法一
    var arr = ["c","a","z","a","a"];
		var charArr = [];
		var countArr = [];

		for(var i = 0 ; i < arr.length ; i ++){
			1.判断charArr是否存在
			2.如果存在不插入,在countArr对应的下标++,不然的话插入,而且给countArr追加1
			var index = charArr.indexOf(arr[i]);
			index为-1时，该元素不存在
			if(index == -1){
				charArr.push(arr[i]);
				countArr.push(1);
			}else{
				countArr[index] = ++countArr[index];
			}
		}
		for(var i = 0 ; i < charArr.length ; i++){
			console.log(charArr[i]+'出现的次数为:'+countArr[i]);
		}
+ ### 2.方法二
		var arr = ["c","a","z","a","a","z","b"];
		// var rs = {
		// 	a:3,
		// 	c:1,
		// 	z:1
		// }
		// boolean  如果是字符串,只要有内容则为true,如果是''则为false
		// 如果是undefined/null  ==> false处理
		// 0 被当做false处理, 非0 为true
		
        
        var rs = {};
		for(var i = 0 ; i < arr.length ; i ++){
			//判断是否存在arr[i]对应的值这个属性
			if(rs[arr[i]]){
				rs[arr[i]]++;
			}else{
				rs[arr[i]] = 1;
			}
		}
		console.log(rs);

        /*
			重要!!!给对象动态添加属性 不能用.,必须用[]
			var key = 'a';
			rs[key] = 123;
			console.log(rs);
            这里不能判断对象里到底有没有a，b，c，所以只能用key给其添加属性
		*/