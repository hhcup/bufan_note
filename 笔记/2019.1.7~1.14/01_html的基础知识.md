## 一．基本介绍
> ### 1.html基本骨架

        <!DOCTYPE html>
        <html>
        <head>
	    <title></title>
        </head>
        <body>

        </body>
        </html>
+ h标签
    -	h1-h6  标题标签（没有h7）
+ p标签
     -  段落标签   （每一组p标签形成一个段落）
+ br 换行符
    - （在html中代替回车，空格不敏感，）
***
> ### 2.图片路径
+ #### 1.绝对路径
    -  a 网络绝对路径：
        https://b-ssl.duitang.com/uploads/item/201608/27/20160827181638_cfC4t.jpeg
    -  b 本地绝对路径 
        D:/html_黄华超/img/fbb.jpg (基本不用)
+ #### 2.相对路径
    - a.同级路径   fbb.jpg
    - b.上级路径   ../fbb.jpg
    - c.同级文件夹下的图片 xx/xx/fbb.jpg
> + ### 插入图片
```img src+图片路径  Alt+图片加载失败显示的文字    title+鼠标悬停时显示的文字```

***
>### 3.超链接
+ ```<a href="地址">可点击的元素</a>
        eg：<a href="https://www.baidu.com">百度</a>
    ```
    - Target+_self  在此页面中打开
    -   Target+_blank  在新页面中打开
***
>### 4.列表（一般只会用到ul列表）
+ 1）有序列表：
    ```
    <ol>
	<li></li>
    <li></li>
    </ol>

    ```
+ 2)无序列表
    ```
       <ul>
	<li></li>
    <li></li>
    </ul>
 
    ```
+ 3）自定义列表
    ```
    <dl>
		<dt>第一章</dt>
			<dd>html基础</dd>
			<dd>html进阶</dd>
		<dt>第二章</dt>
			<dd>css基础</dd>
			<dd>css进阶</dd>
    </dl>

    ```