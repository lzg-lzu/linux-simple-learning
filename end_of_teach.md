# 最后碎碎念 #

本文节选和改编自[提问的智慧](https://github.com/ryanhanwu/How-To-Ask-Questions-The-Smart-Way/blob/main/README-zh_CN.md)，除此之外包含了本人在IT部工作三年的经验。

## 为什么需要“正确的提问” ##

在日常使用和学习过程中，遇到问题是常态，遇不到问题是罕见情况。如何能够快速的寻找到解决自己问题的答案是一种需要培养的能力。</br>

## 什么叫做正确的提问 ##

不是所有的问题都是好问题，也不是所有的问题都值得去被解答。同样也不是所有的问题都能得到解答，能够得到别人解答问题是一种幸运而不是应得的。</br>
在提问前，需要注意以下几个问题：</br>

1. 将报错的全文记录出来。如果可以用复制粘贴就复制粘贴到文件里面，将文件作为提问的附件之后再提问；如果没办法复制粘贴就使用 *输出重定向* 符号将错误输出到处到文件中。
2. 提问前说明自己的配置，重点在于 系统版本 语言版本。比如MySQL 8.0 需要大于1G内存，用512M内存安装自然是不可行的。所以，在安装软件前，需要去软件官网去找最低的配置要求和系统要求。
3. 提问前请先在搜索引擎上进行搜索。搜索时候要选好搜索引擎。首选[Google](https://www.google.com)，如果你无法打开谷歌，请自行学习“科学上网”。次选是[必应](https://www.bing.com)。这个网站国内可以直接访问。不建议使用[百度](https://www.baidu.com)或者搜狗360之类的。
4. 使用Linux的时候，请首选英文(美国)作为系统语言。这样报错内容就是纯英文的内容，更方便在搜索引擎上寻找解答。

## 如何快速的找到需要的内容 ##

使用搜索引擎的时候，除了上文中所述的选择搜索引擎之后，还有几个需要注意的地方。</br>

1. 搜索时关键词需要选择正确。主要通过报错的内容进行搜索，但不要引入额外的关键词。最常见的问题是，报错的内容包含了你文件内的信息或者包含你路径的信息。如果直接复制粘贴进去，搜索到的信息可能有偏差。
2. 不同网站提供的回答质量也是不一样的。最为经典的是[Stack Overflow](https://stackoverflow.com/)。其次是[github](https://github.com)。国内的[博客园](https://www.cnblogs.com/)以及[CSDN](https://www.csdn.net/)的信息可能远落后于你要的版本，所以建议你谨慎使用这两个网站上提供的信息。
3. 记住使用恰当的搜索语句。比如 ```+``` 代表连接两个关键词，```""```代表着限定关键词，```-```代表着排除关键词，```site:```代表着在指定网站上搜索，```*``` 代表着任意长度的任意字符, ```?```代表着只有一位任意字符

## 未来方向 ##

随着时代发展，技术进步的速度越来越快，一个人很难完全彻底的掌握所有技术细节。所以需要大家能够快速准确的检索到自己需要的内容。但同时，有些技术是必须掌握的，必须熟练到像吃饭喝水那样。这些技术包括：

1. git的使用。git作为一项具有种种优点的技术，应当对于其基础操作较为熟练。在此处推荐使用廖雪峰老师的[教程](https://www.liaoxuefeng.com/wiki/896043488029600)
2. 对于以bash为代表的Linux shell的使用。此处可以参考阮一峰老师的文档[归档](https://github.com/ruanyf/free-books)中的[bash教程](https://wangdoc.com/bash/)。最起码需要了解常见的命令和操作结果。
3. 对于网络部分，需要对路由、IP、DNS等内容了解并熟悉，最好能够通过计算机三级的网络部分考试。IT部应该是有一本计算机三级的教程，希望大家能够多学习。
4. 对于常见的网络使用出现的问题，首先要根据HTTPcode来判断问题发生在哪里。有些浏览器不会直接放出HTTPcode，就需要你自己去查看无法访问的页面上的提示部分。
5. 建议大家除了Ubuntu这个Linux发行版之外，了解并学习一下kali这个Linux发行版。里面有不少的工具在网络维护中起到重要作用。
6. 需要掌握至少一门脚本语言（推荐python），一门高级编译语言（推荐java或者C#）；了解C语言以及C++ 的编译过程（此处推荐自行安装[lfs系统](https://www.linuxfromscratch.org/lfs/)以便于学习和了解）
7. 对于硬件部分，需要学习并掌握常见x86机器的故障及解决方案，能够熟练在x86机器上安装Windows并安装合适的驱动。需要学习掌握USB的集中定义以及最常见的问题，USB与wifi蓝牙之间的干扰以及解决办法。

以上内容大多数均可以在网络上找到对应内容，同时我也附带了大量的链接。上班时间除了维修别的实体的问题，最好多看一看我发的链接，多进行实战操作，熟练掌握问题所在。对于申请副经理的人选，除了上述之外，也要自己思考对应的拓展知识。徐汇IT经理会对你们的技术进行考核，包括但不限于我上文提到的内容。各位仍需要加强学习才能通过他的考核。