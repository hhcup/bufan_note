# 1.事件
+ ## 概述
        JS是以事件驱动为核心的一门语言。
        js是采用事件驱动(event-driven)响应用户操作的。比如通过鼠标或者按键在浏览器窗口或者网页元素(按钮，文本框...)上执行的操作，我们称之为事件(Event)。
        由鼠标或热键引发的一连串程序的动作，称之为事件驱动(Event-Driver)。对事件进行处理程序或函数，我们称之为事件处理程序(Event Handler)。
+ ## 事件三要素
        事件源、事件、事件驱动程序。

        事件源 ：要触发的对象  （一般是名词，事件发起者，比如开关按钮）
        事件：怎么触发这个事情  （一般是动词，触发事件，比如点击开关）
        事件处理程序:发生了什么事情 （处理结果，比如灯亮了）

        js做什么：获取事件源、绑定事件、书写事件驱动程序。

        1. dom元素  document element model 
		页面中所有的标签都是dom元素
	    2. node节点  
		页面中所有的标签都是node节点
		标签的文本内容也是node节点
		标签的换行 回车 也是节点
		标签的属性也是节点
		标签的注释 也是节点
***
# 2.获取DOM元素的方法
## 三个方法 获取dom元素
	1.document.getElementById(); // 根据id获取
    直接获取到元素【不常用】
	2.document.getElementsByClassName(); //根据class名称获取【常用】
    结果类型为 html collection 集合,类似于数组但不是数组,我们称之"伪数组"
    可以通过数组下标获取内容,但是不具备数组的sort等基本api
> #### 所以在用此方法时通常需要搭配数组下标获取需要的元素。
    
	3.document.getElementsByTagName(); // 根据标签名获取【不常用】，同class用法
> ## 注意：
    nodeType==1时才是元素节点(标签)
    nodeType  ==  1  表示的是元素节点  元素就是标签
    nodeType  ==  2  表示的是属性节点
    nodeType  ==  3  表示的是文本节点
	nodeType = 8     表示的是注释

> # class选择器问题
    一般在ie8里会存在很多兼容问题, 需要兼容处理(写两套代码)
		
		在ie8不支持getElementsByClassName

		var d1El = document.getElementsByTagName('div')[0];
		var d1El = document.getElementById('d1');

		在ie8不支持console这个对象

		console.log(d1El);
		alert(d1El);

# 3.获取节点
+ ## 兄弟节点
    - ### nextSibling 调用者是节点
            IE678中指下一个元素节点（标签、注释）。在火狐谷歌IE9+(标准)以后都指的是下一个节点（包括空文档和换行节点）。
            var li4 = document.getElementById('li4');
        #### 兼容写法 不能改变顺序
		    var li5 = li4.nextElementSibling || li4.nextSibling;
    - ## previousSibling 调用者是节点
            指前一个元素节点，用法同nextSibling
+ ## 单个子节点
    - ### firstChild 调用者是父节点。
        IE678中指第一个子元素节点（标签）。在火狐谷歌IE9+以后都指的是第一个节点（包括空文档和换行节点）。
    - ### firstElementChild
            在火狐谷歌IE9都指的第一个元素节点
    - ### lastChild 调用者是父节点。
            IE678中指最后一个子元素节点（标签）。在火狐谷歌IE9+以后都指的是最后一个节点（包括空文档和换行节点）。
    - ### lastElementChild
            在火狐谷歌IE9都指的最后一个元素节点。
+ ## 所有子节点 
    - ### childNodes：它是标准属性，嫡出，它返回指定元素的子元素集合，包括HTML节点，所有属性，文本节点
    - ### children：非标准属性，庶出，它返回指定元素的子元素集合。
            但它只返回HTML节点，甚至不返回文本节点，虽然不是标准的DOM属性，但它和innerHTML方法一样，得到了几乎所有浏览器的支持。
> ## 注意：children在IE6/7/8中包含注释节点 ，所以在IE678中，注释节点不要写在里面，不然会当做节点处理！！！


***
# 过滤节点的方法
 ###  在使用class获取节点时，获取的是一个伪数组，可能包含了其他的元素，所以在进行使用的时候要把目标元素筛选出来！！！
        function myChildren (pNode) {
			var children = pNode.children;
			var rs = [];
			for(var i = 0 ; i < children.length ; i++){
				//过滤元素节点
				if(children[i].nodeType == 1){
					rs.push(children[i]);
				}
			}
			return rs;
		}
        



