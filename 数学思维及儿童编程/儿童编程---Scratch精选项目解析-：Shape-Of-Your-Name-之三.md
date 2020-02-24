接上一篇《[儿童编程Scratch精选项目解析 ：Shape Of Your Name 之二](https://www.jianshu.com/p/6dd6e62bd822)》的内容。本篇将尝试重构项目的部分代码。

代码的重构过程就像写作文，需要经过反复思考和不断尝试才能渐入佳境。程序重构以后，内部逻辑更清晰明了，程序运行速度更快，或是扩展出新的功能等等的同时，也是编程能力的提升和思维能力拓展的过程。如果留心观察，就会发现在Scratch官网上这些优秀的项目都是经过了一轮又一轮修改的。Shape Of Your Name 这个项目也是如此。

作者CleverKitten在最近又修改了几次，其中一个比较大的修改就是把两个自定义积木减少为一个。我们先看看CleverKitten自己的改动是怎么样的？

下载早期的代码（[点击此处](https://github.com/rexin1999/Scratch2_Learning/raw/master/Shape%20Of%20Your%20Name%20Radial%20Symmetry_original.sb2)），用Scratch离线编辑器（2.0以上版本）打开这个项目。可以看到，有两个自定义积木Encodex和Encodey。

这两个自定义积木的作用是把字母转换为数字，转换的规则是：
1. 读取输入的文字；
1. 对照字母表的顺序，把输入的文字逐个把字母a-z转为数字1-26；
1. 把转换后的数字的个位数按顺序保存下来作为转码结果；
1. 为了实现绘制一个封闭的图形，那么需要在终点时返回起点位置；

在早期代码中，CleverKitten是把同样的算法用在设定X坐标和Y坐标上，我们可以先运行一下程序，看看变量X和变量Y的关系是怎么样的。

![](https://upload-images.jianshu.io/upload_images/275449-0464874e1a6a8b80.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

咦，怎么出现了X，Y？我的程序界面上没有啊！？让我告诉你一个调试程序的小技巧，在脚本-数据界面上把你需要观察的变量或者列表前的勾选打上，这样变量的情况就会出现在程序的运行界面上。在调试程序过程中，跟踪变量的数值变化非常有用。

我输入了文字：abcd后得到了四个三角形。为什么是三角形？难道不应该是四边形吗？这个问题留待大家自己思考，我提供一点提示：输入adhi试试看，然后再想想为什么？

观察变量显示窗口，我们可以看出列表变量X和列表变量Y二者的关系。是什么关系啊？请多输入不同字母组合进行观察。

既然有这样的关系，那就不需要重复计算两次，只需要计算其中一个列表的值，另一个列表改变一下顺序直接保存下来就可以。下面是CleverKitten写的新代码，不过，看上去还是很啰嗦。

![重构自定义积木块一](https://upload-images.jianshu.io/upload_images/275449-833423172f856f66.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

下面是我的做法，是不是简单很多？确实是简化了很多，但简化并不是简单哦，越简洁的代码其实往往也越不简单。

![重构自定义积木块二](https://upload-images.jianshu.io/upload_images/275449-375fd7824da77cfb.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这部分的代码我放进自定义积木块里，主程序部分代码就更加简洁了。主程序代码能有多简洁？等待输入的语句之后，只有三行！！hohoho……发出了圣诞老人的招牌笑声……

![](https://upload-images.jianshu.io/upload_images/275449-401a6a429fba1591.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

因为绘制的是轴对称的图形，所以，我把CleverKitten画了四次的图形合并成一个函数，而且无需进行四次独立计算，只需要计算一次，然后再稍做变换就可以获得另外的三组数据。我这里偷了个懒，自定义积木块Draw其实还可以优化哦！这个任务就交给你来完成吧。

在运行时，我的版本（[代码链接](https://github.com/rexin1999/Scratch2_Learning/raw/master/Another%20Shape%20Of%20Your%20Name.sb2)）的运行速度明显比CleverKitten快很多，而且输入的字符越长，差别就越明显。

到这里，Shape Of Your Name项目我们就学习完啦! 期待看到你的Scratch作品哦！


-------
热心的系列文集：
- [《春风小学堂字课》](http://www.jianshu.com/nb/19650121)
- [《语文英语读写能力》](http://www.jianshu.com/nb/8869173)
- [《语文同步说文解字》](http://www.jianshu.com/nb/6718880)
- [《数理思维及儿童编程》](http://www.jianshu.com/nb/10476879)
