# css的常用属性
***
>## 文字属性
### 1.font-size
    控制字体的大小，单位是px
### 2.font-family 
    控制字体，尽量使用英文表示字体，同时尽量使用系统自带字体，能大幅缩短页面的加载速度和提高兼容性。
### 3.color
    控制文字的颜色，通常用16进制和rgb和rgba表示。
### 4.font-weight
    控制字体的粗细，100-900，预定义的有lighter light normal bord border 
### 5.font-style
    italic 斜体
### 6.lin-height
    行高，可以控制单行文本垂直居中，可以控制多行文本的行距。
### 7.text-indent
    字体缩进，段落首行缩进
## 字体的缩写
***
    {font: font-style font-weight  font-size/line-height  font-family;}
***
> ## 背景属性
***
### 1.background-color
    背景颜色，格式同字体颜色
### 2.background-image
    url（图片的路径）
### 3.background-repeat
    背景图片的平铺方式，有x，y轴平铺，通常使用no-repeat
### 4.background-position
    背景图片的定位，如果写两个值，第一个代表x轴，第二个代表Y轴
    如果是fixed，则不会随着屏幕滚动而移动
***
> ## background的缩写
***
background: green url(1.jpg) no-repeat center center fixed;
***
