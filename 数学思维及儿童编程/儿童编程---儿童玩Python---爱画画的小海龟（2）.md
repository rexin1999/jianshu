![爱画画的小海龟](http://upload-images.jianshu.io/upload_images/275449-6c2fdc121da17db1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在[爱画画的小海龟（1）](http://www.jianshu.com/p/0e02af97c8d7)里，我们已经用程序控制小海龟画出了有趣的图形。

![黑白图形 ](http://upload-images.jianshu.io/upload_images/275449-ff3f51b4826f4a63.gif?imageMogr2/auto-orient/strip)

```
# 小海龟来画画
import turtle                   
t = turtle.Pen()                
for x in range(100):            
    t.forward(x)
    t.left(91)

```

接下来，我们为线条加上颜色，为了让颜色更鲜艳，我们把背景变成黑色。

![彩色图案](http://upload-images.jianshu.io/upload_images/275449-43d59f146fc8ee62.gif?imageMogr2/auto-orient/strip)

```
import turtle
t = turtle.Pen()
colors = ["red", "yellow", "blue", "green"] 
turtle.bgcolor("black") 
for x in range(100):
    t.pencolor(colors[x%4]) 
    t.forward(x)
    t.left(91)
```
仔细对比两段代码，找找有哪里不同？

```
import turtle
t = turtle.Pen()
colors = ["red", "yellow", "blue", "green"]  # <--新加的代码
turtle.bgcolor("black") # <--新加的代码
for x in range(100):
    t.pencolor(colors[x%4]) # <--新加的代码
    t.forward(x)
    t.left(91)
```
其中，colors里面有四种颜色，你可以尝试用其他的颜色，比如：brown，gold，gray，orange等来替换。bgcolor是background color的简写，你也可以把black替换成其他喜欢的颜色。运行程序后，你也许会得到这样的一个图形。

![换换颜色](http://upload-images.jianshu.io/upload_images/275449-dfc30f508beec06e.gif?imageMogr2/auto-orient/strip)

我相信你已经猜到了pencolor是为画笔指定颜色，那么colors[x%4]，是利用x%4这个算式自动从前面的colors中的一种颜色替换到下一种，你可以尝试在colors输入更多的颜色，又或者把4改为其他的数字，或者两样都做一下看看，记得每改变一次，就运行一次看看结果哦！


![效果不错哦！](http://upload-images.jianshu.io/upload_images/275449-53db02ca66e40555.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

-------
* 欢迎关注系列文集：[《如何提高孩子读写能力》](http://www.jianshu.com/nb/8869173)
* 欢迎关注系列文集：[《语文同步说文解字》](http://www.jianshu.com/notebooks/6718880)
* 欢迎关注系列文集：[《STEM Kids 少年学科技》](http://www.jianshu.com/nb/10476879)
