1. input 自动填充,去掉黄色背景

``` css
input:-webkit-autofill {
    -webkit-box-shadow : 0 0 0px 1000px white inset ;
    border : 1px solid #CCC !important ;
}
```

2. 去掉input button 点击时的边框

``` css
input[type="button"], input[type="submit"], input[type="reset"], button {
    -webkit-appearance: none;
    -webkit-tap-highlight-color: rgba(0,0,0,0);
    -webkit-tap-highlight-color: transparent;		/* For some Androids */
}

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
