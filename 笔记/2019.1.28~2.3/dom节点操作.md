# 1.DOM节点操作
### 节点的访问关系都是属性。节点的操作都是函数或者方法。
#### 使用方法是这样的document.createElement();
    注意:元素创建之后必须插入才能显示
## 插入节点
    使用方法： 父节点.appendChild();
              把创建的元素插入父节点

    使用方法：父节点.insertBefore(要插入的节点，参考节点)；
            把创建的元素插入父节点的兄弟元素前

    如果参考节点为null，那么他将在节点最后插入一个节点。
## 删除节点
    用法：父节点.removeChild（子节点）。
    删除操作 必须通过父节点执行
    节点自己删除自己：
    不知道父级的情况下，可以这么写：node.parentNode.removeChild(node)
## 复制节点
    用法：oldNode.cloneNode（true）
    想要复制的节点调用这个函数cloneNode()，得到一个新节点。 方法内部可以传参，入股是true，深层复制，如果是false，只复制节点本身。
## 节点属性（节点.属性）
    获取：getAttribute(名称)
    setAttribute是用于添加"属性"的,不是用于操作class内容的.
    设置：setAttribute(名称, 值)
    删除：removeAttribute(名称)

## 内容处理
    1.如何给p标签插入(替换)内容 innerText/textContent
		p1EL.innerText = '不凡学院!'; // 常用
		p1EL.textContent = '你好!'; // 不常用
	2.如何给input设置value
		usernameInput.value = '张胜男';
	3.如何给ul动态添加li
		var liStr = '';
		for(var i = 0 ;i < 5;  i ++){
			liStr += '<li>li_'+(i+1)+'</li>';
			}
		只能显示文本内容 不能解析html


