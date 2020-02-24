接上一篇《[儿童编程Scratch精选项目解析 ：Shape Of Your Name 之一](https://www.jianshu.com/p/eb2e03807527)》的内容。本篇我们将学习如何读代码。

读代码往往比自己写代码还要困难，这是正常现象。其实，代码编写时是个逐渐添砖加瓦的过程，所以，读代码时只要化整为零，把整个代码按照要实现的功能拆解成多个部分来分析就容易理解了。

####备份源码
在开始拆解之前，先要保存一份原始的代码。有时候因为作者还在持续更新程序，所以，稳妥起见，是把源码保存一份到本地或者源码托管网站上。本例中，我保存了一份[Shape Of Your Name Radial Symmetry_original.sb2](https://github.com/rexin1999/Scratch2_Learning/blob/master/Shape%20Of%20Your%20Name%20Radial%20Symmetry_original.sb2 "Shape Of Your Name Radial Symmetry_original.sb2")，至于作者最新的源码则保存为： [Shape Of Your Name Radial Symmetry-latest.sb2](https://github.com/rexin1999/Scratch2_Learning/blob/master/Shape%20Of%20Your%20Name%20Radial%20Symmetry-latest.sb2 "Shape Of Your Name Radial Symmetry-latest.sb2") 。

有了原始备份，就可以放心大胆的去拆解代码了。

第一步，不是马上要去看代码，而是先运行程序，了解程序实现的功能，正如我们在上一篇中所做的那样。我们应该先阅读作者的说明文档，直接运行程序来了解程序的功能，这是非常重要的。

第二步，初步了解程序的角色、变量和自定义积木块。

####了解有哪些角色
![角色](http://upload-images.jianshu.io/upload_images/275449-3ba09f066f8e8b03.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

可以看到这里有五个角色，我试着删掉了后面4个，发现没有对执行结果产生影响。估计是留待以后作者想实现的功能用的。暂时我们只需要关注第一个角色就可以了。

####了解有哪些变量和列表


![变量](http://upload-images.jianshu.io/upload_images/275449-bd3a3a0b26e5680d.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如图，项目中有4个变量：ABC、Letter #、 Speed、number。其中Speed变量需要显示在界面上，所以它前面是有勾选，其他的则没有。从变量名称和实际运行的情况，我们可以明白Speed这个变量是用来设定和控制运行速度的。其他三个暂时还不清楚它们的用途。

![Speed](http://upload-images.jianshu.io/upload_images/275449-b365f7dcbb61e1c1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

然后，项目中有3个列表：Letters、X、Y。

X，Y有可能是绘图的坐标（我们先这样猜测，猜测是阅读代码中很重要的，除非作者直接给你说明，不然怎么样？）

####了解有哪些自定义的积木块
Scratch2.0开始可以自定义积木块，这些组装好的积木块往往会实现非常重要的作用。积木块的具体代码也在代码区，这里我们只需要知道有哪些积木块会用到就可以。

![积木块](http://upload-images.jianshu.io/upload_images/275449-2e37a308eb9b893e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

第三步，开始正式进入代码。开始前，先右键运行一下整理，把程序员遗留的垃圾代码先整理到旁边去，以免形成干扰。

####初始化变量和列表

![初始化](http://upload-images.jianshu.io/upload_images/275449-1ba40c7aa5420023.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

在这组代码里，我们看到对界面、画笔、变量ABC和Letter#、列表做初始化设置。包括：
- 清空界面，设定画笔、隐藏角色（小猫）
- 将ABC设定为：abcdefghijklmnopqrstuvwxyz
- 清空三个列表中的数值
- 将Letter# 设为1

通过部分代码，我们获得一个重要的信息，变量ABC是用来定义26个字母的。

####获取用户输入

![输入](http://upload-images.jianshu.io/upload_images/275449-4f1b8ccdcafa6197.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

用侦测工具中的询问等待积木获取用户输入的数据，并提示用户只输入字母：What's your name? Use only letters.

####根据回答给列表赋值
#####列表Letters
用循环语句对列表进行赋值是个好办法。循环的次数是用户输入的内容长度，这样一来，不管输入多少内容，都可以应对自如了。

把用户输入的内容逐个字母读取出来，保存在列表Letters中。

变量Letter#是作为指针，也可以理解为是计数器。

![列表Letters赋值](http://upload-images.jianshu.io/upload_images/275449-0152ea0dcfb3b01a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#####列表X和列表Y
![图片.png](http://upload-images.jianshu.io/upload_images/275449-7d013d9925e75535.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

接下来，作者根据列表Letters的值，给列表X和Y进行赋值。方法与前面类似，每次循环前都把指针Letter#进行了复位。这部分的代码有些啰嗦了，在下一篇的重构中，我将改写这部分的代码，提高程序的运行效率。

####调用自定义积木块
![调用自定义积木块](http://upload-images.jianshu.io/upload_images/275449-d47f9e9f5ac649b1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

自定义积木块在这里出现了，从名称上我们可以猜测是一个转码模块。让我们去看看这个模块的代码。

####解读自定义积木块
![Encodex](http://upload-images.jianshu.io/upload_images/275449-5bcdac7e3b290949.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这里可以发现，变量number有两个作用，一个作用是作为计数器，一个是根据ABC里的26个字母表来把输入的字母转换为数字（a对应1，b对应2……）

这个转换过程分为三层，第一层是1-10位，第二层是10-20位，第三层是20-26。这三层起到的作用是按照26个字母的顺序，把Letters中的字母提取出来，然后转换对应位置的个位数，记录到列表X。

这个转换动作实现了字母到数字的转换。

接下来，我们去看Encodey，会发现做的是同样的事情，只不过这次是记录到列表Y当中去。

在下一篇中，我也会重构这部分，作者在最新的代码中也把两个积木块合并成了一个。

####绘制图形
在使用的时候，我们会发图形实际上是由四个部分组成，四个部分的形状相同，但方向有改变。这部分代码中，可以看到很明显的四个部分，我们可以通过拆开这四个部分看执行的效果，了解对应的作用。

![绘制图形](http://upload-images.jianshu.io/upload_images/275449-2cf011a5766bb360.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

也可以直接阅读代码来理解这个绘制过程：定位-落笔-滑行-抬笔。

我只截取了其中两个部分，通过这两个部分，我们可以看出来，绘制是基于前面转换的数据再进一步生成坐标，在坐标间进行滑行实现绘制。输入的字母数越多，绘制的次数也越多，图形也就越复杂。

####小结
通过运行和上述对代码的解读，我们基本搞明白作者的想法：根据输入的内容长度来生成列表，根据字母在字母表中的位置来转换为数字，然后，根据得到的数字列表来生成绘图坐标。转换位置，实现镜像的重复绘制，得到最终的图形。

下一篇中，我将对这个项目进行重构，思路不变，但试图让代码更简洁，运行效率更高。敬请期待……

-------
热心的系列文集：
- [《春风小学堂字课》](http://www.jianshu.com/nb/19650121)
- [《语文英语读写能力》](http://www.jianshu.com/nb/8869173)
- [《语文同步说文解字》](http://www.jianshu.com/nb/6718880)
- [《数理思维及儿童编程》](http://www.jianshu.com/nb/10476879)
