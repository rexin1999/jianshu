Python的设计哲学是“优雅”、“明确”、“简单”，是一门非常适合孩子学习的编程语言。从未接触过编程的孩子，建议先从[Scratch](http://baike.baidu.com/link?url=7r3zvPocRNVAJiqeOomBmNUsugaYBXy76ZFznlA_WYSm8DoRdHQ19LOIRhTLxYcDUqV_8e91tfyjufikb2uKAdwAQW0NuvryWEIksJXkmJi)和CodeMonkey（详见：[面向香蕉的编程：CodeMonkey | 儿童玩编程](http://www.jianshu.com/p/9ee12a0b0ea7)）开始。

**在开始之前，你可能需要一本教程。**

适合和孩子一起玩的Python书，国内目前比较容易找到的有两本：《趣学Python》和《和孩子一起学编程》，这两本书内容都不错，都是父亲给孩子写的编程入门书。后者的内容稍微深一点，建议先从《趣学Python》开始，然后在从《和孩子一起学编程》挑选一些内容来学习，《和孩子一起学编程》还有另外一个版本《父与子的编程之旅》，只是书名不同而已。

![趣学Python](http://upload-images.jianshu.io/upload_images/275449-d4e0d035c94ae5e9.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![和孩子一起学编程](http://upload-images.jianshu.io/upload_images/275449-34dc6fabc8d73028.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

在网络上还能找到一些电子书，我觉得其中有一本，书名：《*Teach Your Kids to Code* 》最好，甚至比前两本都好，国内的引进版书名是：《教孩子学编程（Python语言版）》（人民邮电出版社）。

![Teach Your Kids to Code](http://upload-images.jianshu.io/upload_images/275449-537ed88ad68e411b.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**源代码库**

第二步，你可以到[github](https://github.com)上找到上述教程中相关的源代码，当然，也可以像我一样，建个自己的代码库，然后把这些代码项目搜集起来，就像这样：https://github.com/HaoRay/ 这并不是必须的，但用起来真是很方便。

**Python运行环境**

接下来，需要搭建Python的运行环境。

前往官方网站：https://www.python.org/downloads/ 有两大系列可供选择：3系列和2系列。它们有部分代码不兼容，3的代码规范性更好，而2的代码资源更为丰富。具体选择什么版本，视乎你手上的教程用的是什么版本，我选择的是3系列，如果你发现我的代码在你的机器上运行时报错，那么很可能和你用的Python版本是2.7甚至更低有关。具体的操作步骤，还是看教程吧，如果没有，网上搜索一下，也很容易找到。

**爱画画的海龟**

虽然先学点基础知识可能会有帮助，但也许对孩子来说，先来点好玩的，更有吸引力。

好，先看一段代码，
```
# 小海龟来画画
import turtle                   
t = turtle.Pen()                
for x in range(100):            
    t.forward(x)
    t.left(90)

```
执行后效果是：

![爱画画的海龟 1](http://upload-images.jianshu.io/upload_images/275449-e88430be4cbc256d.gif?imageMogr2/auto-orient/strip)

这里用到了turtle库（详见《趣学Python》第四章，图中三角形的小箭头就是传说中的小海龟），我们用字母t 来代替turtle.Pen() 这一串代码。用循环语句for（如果接触过Scratch或者CodeMonkey的孩子一看就会），把最后的两条语句重复执行了100次，x最初的值是0，每执行一次，x的值加1，最后的值是99，range就是值的范围。forward表示前进，前进的距离由x值来决定，left是左转，每次转的角度是90°。

需要注意的for语句后面的冒号和随后代码的缩进（四个空格），空行作为结束。

接下来只用改动一点点，把90改为91。

```
# 小海龟来画画
import turtle                   
t = turtle.Pen()                
for x in range(100):            
    t.forward(x)
    t.left(91)

```
效果马上就不同了。

![爱画画的海龟 2](http://upload-images.jianshu.io/upload_images/275449-ff3f51b4826f4a63.gif?imageMogr2/auto-orient/strip)

可以再试试改成其他的数字或者和x有关的算数表达式看看，比如：90+x%4 

下一次，我们来画彩色的，你能想到是怎样做到的吗？

![color1.gif](http://upload-images.jianshu.io/upload_images/275449-43d59f146fc8ee62.gif?imageMogr2/auto-orient/strip)

-------
* 欢迎关注系列文集：[《如何提高孩子读写能力》](http://www.jianshu.com/nb/8869173)
* 欢迎关注系列文集：[《语文同步说文解字》](http://www.jianshu.com/notebooks/6718880)
* 欢迎关注系列文集：[《STEM Kids 少年学科技》](http://www.jianshu.com/nb/10476879)
