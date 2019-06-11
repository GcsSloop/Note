# 第1章 编译概述

## 1.1 翻译程序与编译程序

类型     | 含义
---------|---------
翻译程序 | 从一种语言到另一种等价的语言
编译程序 | 从高级语言到低级语言，编译是翻译的一种


###  编译过程:

![](http://yuml.me/diagram/nofunky/class/
[源程序] 编译程序 -> [机器语言目标程序] 
(end).svg)


**如果程序最后生成的不是机器语言，而是汇编则增加一步:**


 ![](http://yuml.me/diagram/nofunky/class/
 [源程序]编译程序->[汇编语言],
 [汇编语言]汇编程序->[机器语言目标程序] 
 (end).svg)

### 运行过程:

 ![](http://yuml.me/diagram/nofunky/class/
 [机器语言目标程序] 初始数据-运行系统>[结果] 
 (end).svg")

### 编译运行综合过程：

 ![](http://yuml.me/diagram/nofunky/class/
 [源程序] 编译程序->[机器语言目标程序],
 [源程序] 编译程序->[汇编语言],
 [汇编语言] 汇编程序->[机器语言目标程序],
 [机器语言目标程序] 初始数据-运行系统>[结果]
 (end).svg)

*****

## 1.2 编译过程和编译程序的基本结构

### 编译程序的5个阶段：

序号 |     阶段     | 主要任务
:---:|--------------|--------------
  1  | 词法分析     | **对构成源程序的字符串从左到右进行扫描和分解**，根据语言的**词法规则**，识别出具有独立意义的单词(单词符号)。
  2  | 语法分析     | 在词法分析的基础是哪个，根据语言的**语法规则**从单词符号中识别出各种语法单位(表达式、说明、语句等)并进程语法检查，即检查各种语法单位在语法结构上的正确性。
  3  | 语义分析<br/>中间代码生成 | 首先对每种语法单位进行静态的语义审查，然后分析其含义，并用另一种语言形式(比源语言更接近目标语言的一种中间代码或直接用目标语言)来描述这种语义。
  4  | 代码优化     | 对上一阶段产生的中间代码进行等价交换或改造，以便获得更高效的(*节省时间和空间*)目标代码。 优化主要包括**局部优化和循环优化**。
  5  | 目标代码生成 | 将中间代码转换为特定机器上但绝对指令代码，或可重定位的指令代码，或汇编之类代码。

**PS: 在编译程序但各个阶段中，都要涉及表格管理和错误处理。**

编译模式 | 解释 | 优缺点
---------|------| -------
一遍扫描 | 将上述5个阶段工作结合到一起，对源程序从头到尾扫描一遍完成编译各项工作。 | 编译效率高但占用空间大
多遍扫描 | 多遍扫描，每一遍完成上述某一阶段但一部分，全部或多个阶段但工作。        | 编译效率低但占用空间小

**PS: 在主存可能的前提下，尽量减少遍数。**


## 1.3 编译程序的生成方法

要生成一个编译程序一般要考虑一下几个方面：

序号 |          方面          | 要点
:---:|------------------------|--------------
  1  | 对源语言的目标语言分析 | 1.熟悉源语言，要正确理解它的语法和语义。<br/> 2.要清楚目标语言和目标机的性质。
  2  | 设计编译算法           | 着重考虑如何使编译程序具有**易读性、 易改性 和 易扩充性**。
  3  | 选择语言编制程序       | 从20世纪80年代开始，几乎所有的编译程序都是用**高级语言**来编写，这样可以**提高开发效率**，且构造出来的编译程序增加了**易读性、 易改性 和 易扩充性**。
  4  | 调试编译程序           | 通过大量的实例对编好的程序进行调试，调试过程中不断修改、完善编译程序。
  5  | 提交相关文档资料       | 为了方便用户，需要提交一本有关编译程序的文档资料，内容包括源语言的文法、目标机器的指令系统、编译程序结构和所采用的具体策略、错误信息表及使用说明。

**几个概念：**

概念 | 释义
-----|-----------
编译程序产生器 | 根据源程序定义和机器语言描述自动生成该语言的编译程序。

生成编译程序的方法：

概念 | 释义
-----|-----------
自编译方式 | 先用目标机的汇编语言对源语言的核心部分构造一个小小的编译器(可手工实现)，再以它为工具构造一个能够编译更多语言成分的较大编译器，像滚雪球一样，越滚越大，最后生成人们所期望的整个源语言编译程序。
移植方式   | 把某机器上已有的编译程序移植到另一台机器上去。
交叉编译   | 一个源语言，在宿主机（运行编译程序的计算机）上，经过编译产生目标机的机器语言或汇编代码。

## 1.4 编译技术在软件开发中的应用

虽然只有少数人从事构造会维护程序语言编译器的工作，但大部分系统软件和应用开发，通常要用到编译原理和技术。

## 本章小结

本章重点介绍什么是编译程序以及编译程序的结构。

![](http://yuml.me/diagram/nofunky/class/
[源程序] -> [词法分析程序],
[词法分析程序] -> [语法分析 程序],
[语法分析 程序] -> [语义分析和中间代码生成程序],
[语义分析和中间代码生成程序] -> [代码 优化 程序],
[代码 优化 程序] -> [目标程序],
(end).svg)

## About Me

<a href="https://github.com/GcsSloop/SloopBlog/blob/master/FINDME.md" target="_blank"> <img src="http://ww4.sinaimg.cn/large/005Xtdi2gw1f1qn89ihu3j315o0dwwjc.jpg" width=300 height=100 /> </a>

<br/><br/><br/><br/><br/><br/><br/><br/>



