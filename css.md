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
