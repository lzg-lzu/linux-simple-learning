# 此文档目的在于简介网络部分 #

## 什么是网络 ##

实际上，能够把不同的计算机连接起来，进行相互通信，就算构成了一个计算机网络。有个略显恶心的段子是这么讲的：当你坐在马桶上“畅快飞翔”时，你就接入了一个巨大的网络。这个说法其实是有偏差的，因为你只有输出没有输入。只有当你感受到“波塞冬之吻”时，才算是成功建立了一个网络</br></br>
我们可以直接把两台计算机连接起来，配置成功让两者能够相互通信，这样就建立了一个简单的计算机网络。</br>
你可能觉得有点奇怪，为什么我没有说那些IP、网关、DNS、路由之类的东西。因为在网络中，这些并不是必须存在的。</br>
那么，我们学网络学一些什么？当然是学IP、网关、DNS、路由这些了。</br>
冲突吗？并不冲突。在日常使用中，基于TCP/IP的网络占了绝大部分。掌握了TCP/IP，虽然不能说完全解决见到的所有网络问题，但也能解决日常遇到的90%以上的网络问题了。那我们马上就学习这些吗？不，我们先从硬件开始，先从不是那么底层的底层开始了解网络，了解的比较多了之后我们再从上层开始了解网络，最后再整体贯彻的了解网络的全貌。

## 网络硬件有什么 ##

在进入实际问题后，我们就需要有着软硬件结合的思维。首先就是要确认，出问题的地方是硬件范围还是软件范围还是软硬件结合的地方。这部分我们就旨在从硬件层面解释网络连接。</br>
常见的网络硬件有些什么？随口就能说出来的有哪些？ **网线？ 路由器？** 除了这些人尽皆知的设备外，还有一些不是那么明显但也是很重要的设备，还包括 **网卡、AP**等设备。下面我们分部分来进行说明。</br></br>

### 网线 ###

说到网线，你可能会说，欸，为啥你刚才没说光纤呢？其实，我们最常见的，带着一个 “凸” 型接头的网线指的其实是 **使用RJ45接口的双绞线**。而网线除了这种双绞线外，也包括光纤、同轴电缆等等不同外表，不同带宽的网线。我们在这里，主要讨论RJ45双绞线的一些问题，次要讨论光纤。对于像同轴电缆这种连接方式，我们就先不详细介绍了。</br></br>

#### **同轴电缆** ####

我们现在所说的数据，大多数时候说的仅仅就是使用数字信号传递的数据。对于数字信号，我们知道，它是由一串 **“0,1”** 组成的。我们自然就能够想到，用电压的高低来代替 **“0,1”** 不就可以用一根导线来传递数据了吗？我们将一根电线周围包上一层屏蔽层，这就形成了最简单的同轴电缆了。这里，自然也存在着不少问题。比如我们都知道，不存在完美的导体，导线总会有电阻的。那么，会不会有可能，一个高电压在传递很长的距离之后，电压就降低到了我们认为是低电压的区间呢？这是很有可能发生的。所以在之后的发展中，我们就不再用电平的高低来表示 **“0,1”** 了，而是改用电平的改变来表示 **“0,1”** 。如果大家对于电磁学还有所了解的话，夹着绝缘层的两个导体之间会构成什么？对的，就是电容。对于一个快速变化电压高低的电信号而言，电容的存在放大了噪音，也使得我们不可能将传输信号的频率无限制的提高的原因之一。同样，我们用的屏蔽层也不是完美的，如果被外界干扰了，我们数据的准确性和完整性也受到了很严重的考验。这也是我们选择其他硬件来传递网络数据的原因之一。

#### **双绞线** ####

如果你仔细观察过那个“凸”型接口比较平的一面，就会发现里面其实是有8根线或者是4根线。如果你再仔细看一看的话，就会发现，这些线实际上也是有颜色的。常见的序列就是 “橙白、橙、绿白、蓝、蓝白、绿、棕白、棕”。</br></br>
如果把库房里面的那些线拿出来，查看截面，我们能够看到中间具有一个十字骨架结构，把里面八根线分成了四组，每组有两根线相互拧起来，这就是“双绞线”。</br></br>
为什么我们用双绞线代替同轴电缆呢？所有新技术的诞生，都是用来解决旧技术中存在的问题的。这里我们要引入一个新的名词叫做 ***“差分信号”*** 。</br></br>
何为 ***“差分信号”*** ？差分信号指的是使用一对信号而不是一个信号来传递数据。比如我们约定，使用同轴电缆传递数据时，以+1.1V作为1，0V作为0；现在我们用两根线，其中一根线传输和同轴电缆的约定一致，另一根线里面，以-1.1V作为1，0V作为0；这样的话，我们只要让一个信号在两根线传播用时一致，那么我们在接收端通过简单的计算两根信号线的电压差，就能够通过这种方法将外界的干扰消除掉。（怎么搞出负电平？这个问题请去问大学物理老师）</br></br>
这样通过简单的办法，我们就消除了外界对于双绞线传输时的干扰……吗？不知道你有没有注意到一点，上文中写的是 ***只要让一个信号在两根线传播用时一致*** 。为什么要这么写？通过一个简单的案例就能看出来了。

|导线上电平正负|信号序列|
|:---:|:---:|
|+|……1010101010……|
|-|……1010101010……|

上文中提到的求电压差，在表中就是求和操作（仔细想想，是不是？）这个表就是理想情况，如果我们把其中一条信号线加一个延迟，只要造成一位的差别，结果是不是就如下表所示？

|导线上电平正负|信号序列|
|:---:|:---:|
|+|……1010101010……|
|-|…10101010101……|

再让我们进行求和计算……欸？怎么都成了零？这也就是双绞线的问题所在。需要尽量保证两根信号线的传递时间完全一致。这也是为什么主板上总会见到不少弯弯折折的线的原因。</br></br>
这里面还有一个问题我们没有提到。万一只有一根线受到干扰而另一根没有收到干扰，怎么办？我们就把要传递差分信号的两根信号线相互绞起来，这样外界的干扰也就能够同时干扰两根线，就相当于没有干扰了。</br></br>

#### **光纤** ####

传递电信号永远有一个问题，就是在传递距离较长的时候，导线电阻导致的压降将不能忽视。这时，我们就要寻找一种损耗较少的方式，进行长距离的信号传输。</br></br>
同样在物理学中，我们发现光有一种很神奇的性质，即在角度合适时，可以用几乎没有损耗的改变传递方向，这就是光的全反射。这也就是光纤的理论基础之一。</br></br>

### 网线部分先告一段落 ###

网线部分就先告一段落了，接下来我们去探索网络信号是怎么诞生并传递的。