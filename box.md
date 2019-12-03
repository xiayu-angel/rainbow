# 盒模型

下面是css代码
```css
        .border-box {
            width: 200px;
            height: 200px;
            margin: 10px;
            padding: 20px;
            border: 1px solid gold;
        }

        .content-box {
            width: 200px;
            height: 200px;
            margin: 10px;
            padding: 20px;
            border: 1px solid purple;
        }

```
下面是html代码
```html

    <div class="border-box">你好</div>
    <div class="content-box">世界</div>

```

效果图

![https://github.com/xiayu-angel/rainbow/blob/master/images/1.jpg]

![https://github.com/xiayu-angel/rainbow/blob/master/images/box.jpg]

根据上面的图来看，两个盒子在没有设置box-sizing前是一样的。设置了box-sizing之后将会有很大的不同。
接下来就一探究竟。

```css
        .border-box {
            width: 200px;
            height: 200px;
            margin: 10px;
            padding: 20px;
            border: 1px solid gold;
            box-sizing: border-box;
        }

        .content-box {
            width: 200px;
            height: 200px;
            margin: 10px;
            padding: 20px;
            border: 1px solid purple;
            box-sizing: content-box;
        }

```
两个盒子将box-sizing设置了不同的值

效果如下

![https://github.com/xiayu-angel/rainbow/blob/master/images/11.jpg]

可以看出一个盒子大一个盒子小，具体为什么呢？ 下面具体说
首先看第一个盒子的具体的数值

第一个盒子的box-sizing的值是border-box

效果图如下:

![https://github.com/xiayu-angel/rainbow/blob/master/images/box.jpg]
它的内容区 就是蓝色部分的`宽高`158px * 158px+ 绿色的`padding`区20px + 再加上金色的` border`区上下左右2px的值  加起来总共是200px*200px 所以`border-box`的内容区是(wh+padding+border)。  

再看第二个盒子的`box-sizing`的值是`content-box`

效果图如下:

![https://github.com/xiayu-angel/rainbow/blob/master/images/1.jpg]

它的内容区就是200*200 没有包括边框和内边距 所以`content-box`的内容区就是宽高

我更偏向于将`box-sizing`的值写成`border-box`。

以上就是我理解的两种盒模型。


