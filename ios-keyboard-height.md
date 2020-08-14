# ios 计算键盘高度

## 场景

![](.gitbook/assets/8fe7f14157fca43544616f403c75fcee.gif)

在工作中遇到上图的场景，需要在键盘弹起时底部菜单跟着键盘弹起，方便在用户输入的时候进行下一步操作



## 关键API

```text
element.scrollIntoView(); //把元素滚动到视窗范围内
```

## 具体计算步骤

1、当键盘弹起时，底部的菜单会被键盘遮住

2、利用scrollInToView\(\)把底部菜单滚动到视窗范围内，这时候页面会向上滚动

3、步骤2中页面向上滚动的值就是键盘的高度

4、利用获取到的键盘高度设置容器的高度，

这样就可以达到键盘弹起时底部菜单被顶上来的效果

##  演示

![](.gitbook/assets/qrcode.png)

{% embed url="https://demos.focusbe.com/ioskeyboard/?v=1" %}



