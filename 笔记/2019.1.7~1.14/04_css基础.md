## css
### css基本写法

```css
	xx {
	color: green;
	font-size:20px;
}

```

### css选择器

```css
	
	1. 标签选择器(不常用)  p{}
	2. id选择器(不常用)  #title1{}
	3. class选择器(常用)  .title{}
		- class命名应该尽量按照当前标签的作用声明

```

### css的引入方式

```html
	1. 行内样式(极少用) <p style="color:red">xxx</p>
	2. 内部样式(演示使用) 
		<style>
			.title{
				color:red;
				font-size:20px;
			}
		</style>
	3. 引入样式(开发常用)
		<link rel="stylesheet" href="xxx.css">

```
### 基本选择器优先级
+ 标签选择器< class选择器 < id选择器  < 行内样式
+ 引入外部样式和内部style的优先级 采用 就近原则，在后面的部分权重更大


### 组合选择器
+ 交集选择器  
>		.class1.class2(同时带有class1和class2选择器)
+ 并集选择器
>		.class1,.class2(同时选择class1和class2选择器)
+ 后代选择
> 		.class1 .class2(选择class1里面的class2)

### 组合选择器权重
+ 通配符权重0(*)   继承样式权重是0(注意a标签无法继承p标签的颜色)
+ 标签选择器权重 1
+ class选择器权重 10
+ id选择器权重 100
+ 内部样式权重 1000 
+ 选择器可以组合,权重叠加

