# 获取DOM元素的方法
+ document.getElementById    一个元素对象
+ [context].getElementByClass 元素集合
+ [context].getElementsByTagName 元素集合
+ document.getElementByName     节点集合
+ document.documentElement      获取整个HTML对象
+ document.body     获取整个body对象
+ document.head     获取整个head对象
+ [context].queryselector       一个元素对象
+ [context].queryselectorAll    获取元素集合



`getElementById`
> 此方法的上下文只能是document
>
>1. 一个HTML页面中ID理论上是不能重复的
>
>2. 如果Id重复了，获取的是第一个ID对应的元素对象
>
>3. 在IE7及更低的版本中，会把表单元素的name值当做id来识别使用（项目中尽量不要让id名和其他元素的name名相同）
>
> 4.如果我们把js放在结构下面，我们可以直接使用ID值来获取这个元素（不需要通过document获取），而且这种方式会把页面中所有Id是他的元素都获取到（元素对象/元素集合）=>（不规范）不推荐
>
> ### 面试题
```javascript
    //获取页面中所有Id名为box1的元素标签
    var allList=document.getElementsTagName('*');
    var rs=[];
    for(var i=0;i<allList.length;i++){
        var item=allList[i];
        if(item.id==box1){
            rs.push(item);
        }
    }
    console.log(rs);
```


`getElementByName`
>
> 通过元素的NAME属性值获取一组元素（类数组：节点集合NodeList）
>
> 它的上下文只能是document
>
> 1.IE浏览器只能识别表单元素的name属性值，所以这个方法一般都是用来操作表单元素的


`document.documengElement/document.body`
> 获取HTML或BODY
>
```JavaScript
//获取当前浏览器的可视宽度
document.documengElement.clientWhith||document.body.clientWhith
```
`querySelector/querySelectorAll`
> 在IE6~8下不兼容，而且也没有好的方法处理兼容，所以多用于移动端
> querySelector 获取一个元素对象
> querySelectorAll 获取一个元素集合
> 只要是css支持的选择器，这里大部分支持
```javascript
    //获取页面中所有Id名为box1的元素标签
   <div id="box1" class="box mark"></div> 1
   <div id="box2" class="mark"></div> 2
   <div id="box1" class="box"></div> 3
   console.log(document.querySelector('#box1')); =>1
   console.log(document.querySelectorAll('#box1')); =>[1,3]
   console.log(document.querySelectorAll('.box')); =>[1,3]
   console.log(document.querySelectorAll('body>div')); =>[1,2,3]
    console.log(document.querySelectorAll('#box2 li'));
```