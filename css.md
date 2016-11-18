1. input 自动填充,去掉黄色背景

``` css
input:-webkit-autofill {
    -webkit-box-shadow : 0 0 0px 1000px white inset ;
    border : 1px solid #CCC !important ;
}
```

或者，关闭 自动填充

```
autocomplete="off"
```

2. 去掉input button 焦点或点击时蓝色边框 & 点击高亮

``` css
input[type="button"], input[type="submit"], input[type="reset"], button {
    -webkit-appearance: none;
    -webkit-tap-highlight-color: rgba(0,0,0,0);
    -webkit-tap-highlight-color: transparent;		/* For some Androids */
}
/* 边框 */
input{
	outline:none;
}

```

在移动端IE10上，需要如下代码才能去除

``` html
<meta name="msapplication-tap-highlight" content="no" />
```

3. 文字两端对齐

``` css
text-align:justify;
text-justify:inter-ideogra;		/* IE */
```

4. 关闭符号“x”

```
&#215;
```

5. 文字过多显示为省略号

``` css
.ellipsis{
	overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
}
```

6. 禁止input聚焦时，软键盘导致页面上滑

```
:focus{
	-webkit-tap-highlight-color:rgba(255, 255, 255, 0);
	-webkit-user-modify:read-write-plaintext-only;
}
```

7. ios transition translate 闪屏问题

当translate使用2d而非3d的呈现方式时，我们要设置当前动画移动元素的呈现方式为3d，它的所有子元素背面隐藏

``` css
.css{
	/*设置内嵌的元素在 3D 空间如何呈现：保留 3D*/
	-webkit-transform-style: preserve-3d;
	/*（设置进行转换的元素的背面在面对用户时是否可见：隐藏）*/
	-webkit-backface-visibility: hidden;
}
```

8. placeholder占位符颜色自定义

``` css
input:-moz-placeholder {
	color: #369;
}
::-webkit-input-placeholder {
	color:#369;
}
```

9. 禁止选中文本

``` css
-moz-user-select:none;
-webkit-user-select:none;
-ms-user-select:none;
user-select:none;
```

10. 屏蔽苹果浏览器对数字的识别

``` html
<meta content="telephone=no" name="format-detection">
```

11. HTML5 input在type="number"时的上下小箭头

``` css
/* Chrome */
input::-webkit-outer-spin-button,input::-webkit-inner-spin-button{
	-webkit-appearance: none !important;
	margin: 0; 
}
/* Firefox */
input[type="number"]{
	-moz-appearance:textfield;
}
```

12. 判断手机横竖屏

* css

``` css
@media screen and (orientation: portrait) {
  /*竖屏 css*/
} 
@media screen and (orientation: landscape) {
  /*横屏 css*/
}
```

* js

``` js
window.addEventListener("onorientationchange" in window ? "orientationchange" : "resize", function() {
	if (window.orientation === 180 || window.orientation === 0) { 
		alert('竖屏状态！');
	} 
	if (window.orientation === 90 || window.orientation === -90 ){ 
		alert('横屏状态！');
	}  
}, false); 
```
