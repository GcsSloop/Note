第一章：

操作系统的目标：方便性，有效性，可扩充性，开放性。

    操作系统的作用：
        1.OS作为用户与计算机硬件层系统之间的接口
        2.OS作为计算机系统资源的管理者
        3.OS实现了对计算机资源的抽象

        推动操作系统发展的主要动力：
            1.不断提高计算机资源的利用率
            2.方便用户
            3.期间的不断更新迭代
            4.计算机体系结构的不断发展
            5.不断提出新的应用需求

操作系统的发展过程：
    
    未配置操作系统的计算机系统：
        1.人工操作方式
        2.脱机输入输出方式

    单道批处理系统：
        满足的需求：
            解决IO速度和处理速度不匹配的问题。
        单道批处理系统过程：
            将一批作业以脱机方式输入到磁带上，并在系统中配置监管程序，在它的控制下，这批作业能一个接一个的处理。
        单道批处理系统缺点：
            系统中的资源得不到充分的利用。

    多道批处理系统：
        满足的需求：
            提高资源利用率和系统吞吐量。
        多道程序设计的基本概念：
            用户提交的作业在外存中排成一个队列，称为后备队列。然后作业调度按一定的算法，从后备队列中选择若干作业调入内存，使他们共享CPU和系统中的各类资源。多道程序交替运行。
        优点：  
            资源利用率高。
            系统吞吐量大。
                CPU和其他资源报纸忙碌状态。
                仅当作业完成或运行不下去时才进行切换，系统开销小。
        缺点：
            平均周转时间长。
            无交互能力。
        多道批处理系统需要解决的问题：
            1.处理机争用问题。
            2.内存分配和保护问题。
            3.IO设备分配问题。
            4.文件组织管理问题。
            5.作业管理问题。
            6.用户与系统的接口问题。

    分时系统：
        所满足的需求：
            人机交互，共享主机。
        分时系统中的关键问题：
            1.及时接收。
            2.及时处理。
                1.作业直接进入内存。
                2.采用轮转运行方式。
        分时系统特征：
            1.多路性。
            2.独立性。
            3.及时性。
            4.交互性。

    实时系统：
        满足需求：
            实时性，任务在规定时间内完成，所有实时任务协调一致的运行。
        实时系统类型：
            1.工业（武器）控制系统。
            2.信息查询系统。
            3.多媒体系统。
            4.嵌入式系统。
        实时任务类型：
            1.周期性实时任务和非周期性实时任务。
                周期性实时任务：周期性执行，以便周期性控制某外部设备。
                非周期性实时任务：无明显的周期性，但是具有一个截止时间：
                    开始截止时间：在某个时间之前必须开始执行。
                    完成截止时间：在某个时间之前必须完成执行。
            2.硬实时任务和软实时任务：
                硬实时任务：系统必须满足任务对截止时间的要求，否则可能出现难以     预测的后果，用于工业或武器控制系统。
                软实时任务：存在截止时间，但不严格，偶尔错过了时间，影响不大，     用于查询系统，多媒体系统。
            3.实时系统与分时系统的比较：
                1.多路性。
                2.独立性。
                3.及时性。
                4.交互性。
                5.可靠性。

微机操作系统的发展：

    单用户单任务操作系统：
        只允许一个用户上机，且只允许用户程序作为一个任务运行。
        代表操作系统：
            CP/M 和 MS-DOS

    单用户多任务操作系统：
        只允许一个用户上机，但允许用户把程序分为若干任务，是他们并发执行。

    多用户多任务操作系统：
        允许多个用户通过各自终端，使用同一台机器，共享主机系统中的各种资源。


操作系统的基本特性：
    
    并发：
        1.并行与并发：
            并行性：两个或多个时间在同一时刻发生。
            并发性：两个或多个事件在同一时间间隔内发生。
            程序执行：宏观并发，微观交替。
        2.引入进程：
            进程：系统中能独立运行，并作为资源分配的基本单位。由一堆机器指令，数据和堆栈构成，是一个能够独立运行的活动实体。

    共享：
        共享指资源的复用。
        1.互斥共享方式：
            某些资源，如打印机，磁带机等，虽然可以提供给多个进程使用，但同一时刻只允许有一个进程访问该资源。
        2.同时访问方式：
            系统中还有一类资源，允许在一段时间内由多个进行“同时”访问。宏观上是同时的，微观上实际是交替执行的。

    虚拟：
        最早在通信系统中的虚拟技术：利用空分复用和时分复用技术，将一条物理信道变为若干条逻辑信道。使得原先只能供一对用户使用的物理信道，变成可以供多个用户同时使用的逻辑信道。
        1.时分复用技术：
            1.虚拟处理机技术。
            2.虚拟设备技术。
        2.空分复用技术：
            利用存储器空闲的空间分区存放和运行其他多道程序。

    异步：
        进程以不可预知的速度向前推进，走走停停。


操作系统的主要功能：
    
    处理机管理功能：
        1.进程控制
        2.进程同步
            1.进程互斥方式：进程在对临界资源进行访问时，应采用互斥方式。
            2.进程同步方式：相互合作完成共同任务的各个进程间，由同步机构对它们的执行次序加一协调。
        3.进程通信
        4.调度

    存储器管理功能：
        为对到程序的运行提供良好的环境，提高存储器的利用率，方便用户的使用，并能从逻辑上扩充内存。为此，存储管理器应具有内存分配与回收，内存保护，地址映射和内存扩充等功能。
        1.内存分配：
            主要任务：
            1.为每道程序分配内存空间，使它们各得其所。
            2.提高存储器的利用率，尽量减少不可用的内存空间（碎片）
            3.允许正在运行的程序申请附加的内存空间，以适应程序和数据的动态增长需要。
            OS实现内存分配时有两种方式：
                1.静态分配方式。
                2.动态分配方式。
        2.内存保护：
            1.确保每道程序都仅在自己的内存空间内运行，彼此互不干扰。
            2.绝不允许用户程序访问操作系统的程序和数据，也不允许用户程序转移到非共享的其他用户程序中去。
        3.地址映射：
        4.内存扩充:
            1.请求调入功能，允许仅装入部分用户程序和数据的情况下便能启动程序运行，若运行过程中发现要继续运行所需的程序和数据未装入内存，可向OS发出请求，由OS从磁盘中将所需部分调入内屯，以便继续运行。
            2.置换功能：若发现内存中已无足够的空间来装入需要调入的程序和数据时，系统应能将内存中一部分暂时不用的程序和数值调至应按上，以腾出内存空间，然后再将所需调入的部分装入内存。


    设备管理功能：
        主要任务：
            1.完成用户进程提出的IO请求，为用户进行分配所需的IO设备，并完成指定    的IO操作。
            2.提高CPU和IO设备的利用率，提高IO速度，方便用户使用IO设备。
        1.缓冲管理：
        2.设备分配：
        3.设备处理

    文件管理功能：
        主要任务：
            对用户文件和系统文件进行管理一方便用户使用，并保证文件的安全性。
        1.文件存储空间的管理：
        2.目录管理：
        3.文件的读写管理和保护：
            1.文件的读写管理：根据用户请求，从外存中读取数据或将数据写入外存。
            2.文件保护：
                1.防止未经核准的用户存取文件。
                2.防止冒名顶替存取文件。
                3.防止以不正确的方式使用文件。

    系统与用户之间的接口：
        1.用户接口：
            1.联机用户接口。
            2.脱机用户接口。
            3.图形用户接口。
        2.程序接口：

    现代操作系统的新功能：
        1.系统安全：
            1.认证技术。
            2.密码技术。
            3.访问控制技术。
            4.反病毒技术。
        2.网络功能和服务：
            1.网络通信
            2.资源管理
            3.应用互操作
        3.支持多媒体：
            1.接纳控制系统
            2.实时调度
            3.多媒体文件的存储


OS设计结构：

    软件质量指标：功能性，有效性，可靠性，易用性，可维护性，易移植性。

    传统操作系统结构：
        1.无结构操作系统
        2.模块化结构OS
            1.模块化程序设计技术的基本概念：
                模块接口法，由上到下，逐层细分，每个模块只完成某一项特定的功能
            2.模块独立性：
                1.内聚性：模块内部各个部分间联系的紧密程度，内聚性越高，模块独立性就越强。
                2.耦合度，模块间相互联系和相互影响程度。耦合度月底，模块独立性越高。
            3.模块接口法的优缺点：
                优点：
                    1.提高了OS设计的正确性，可理解性和可维护性。
                    2.增强了OS的可适应性
                    3.加速了OS的开发过程
                缺点：
                    1.在OS设计是，对各模块间接口规定很难满足在模块设计完成后对接口的实际需求。
                    2.在OS设计阶段，设计者必须做出一系列的决定，每一个决定必须建立在上一个决定的基础上，但模块化设计齐头并进，无法寻找到一个可靠的决定顺序，造成各种决定的无序性，让程序然预案很难做到设计中的每一步决定都是建立在可靠的基础上。
        3.分层式操作系统：
            1.基本概念：
                将模块接口法中的决定顺序从无序变成有序，引入了有序的分层法。
            2.分层结构优缺点：
                优点：
                    1.易保证系统的正确性。自下而上的设计模式使得所有设计中的决定都是建立在较为可靠的基础上的，这样比较容易保证系统的正确性。
                    2.易扩充和易维护性。在系统中增加，修改，替换一个层次中的模块或者整个层次时，只要不改变层次间接口，就不会影响其他层次。使得系统维护和扩充变得更加容易。
                缺点：
                    1.系统效率低。


        客户/服务器模式
            1.客户服务器模式的由来组成和类型
                主要由三部分组成：
                    1.客户机：客户机是一个自主的计算机，具有一定的处理能力，客户进程在上面运行，平时处理一些本地业务，也可发送一个消息给服务器，请求某项服务。
                    2.服务器：通常是一台规模较大的机器，在其上驻留有网络文件系统，或数据库系统，他能为网上所有用户提供一种或多种服务，平时一直处于工作状态，被动的等待来自客户机的请求，一旦检查到客户提出的服务请求，便立即去完成可和的请求，并将结果返回客户。
                    3.网络系统：用于连接所有客户机和服务器的，实现他们之间的通信。
            2.客户服务器之间的交互步骤
                1.客户发送请求信息
                2.服务器几首信息
                3.服务器返回信息
                4.客户机接收消息
            3.客户服务器模式优点：
                1.数据分布处理和存储
                2.便于集中管理
                3.灵活性和可扩充性。
                4.易于改编应用软件。
   

    面向对象程序设计:
        1.基本概念
            1.对象：利用被封装的数据结构和一组对它操作的过程来表现系统中的某个对象
            2.对象类：类是对象的抽象，对则是类的实例。
            3.继承：子类可以用继承获得父类的方法和属性，并能对其修改。
        2.面向对象技术优点：
            1.通过重用提高产品质量好生产率。
            2.使系统具有根号的易修改性和易扩展性。
            3.更易于保证系统的正确性和可靠性。

    微内核结构：
        1.基本概念：
            操作系统被划分为微内核与多个服务器
            1.足够小的内核：
                内核是精心设计的，能够实现OS基本核心功能的小型内核，并非完整的OS，只是将操作系统最基本的部分放入微内核，通常包含有：
                    1.与硬件处理紧密相关的部分
                    2.一些较基本的功能
                    3.客户和服务器之间的通信。
            2.基于客户服务器模式：
            3.应用“机制和策略分类”原理
            4.采用面向对象技术。
        2.微内核基本功能：
            1.进程(线程)管理
            2.低级存储器管理
            3.中断和陷入处理
        3.微内核操作系统的优点：
            1.提高了系统的可扩展性
            2.增强了系统的可靠性
            3.可移植性强
            4.提供了分布式系统的支持
            5.融入了面向对象技术
        4.微内核操作系统存在的问题：
            1.效率有所降低


###############################################################################
*******************************************************************************
###############################################################################

第二章 进程的描述与控制。

前趋图和程序执行：
    
    前趋图：有向无环图，用于描述进程之间执行的先后顺序。

    程序顺序执行：
        1.程序的顺序执行：不论是程序还是程序段，都存在着顺序执行关系。
        2.程序顺序执行的特征：
            1.顺序性：处理机必须严格按照程序规定的顺序执行。即每一个操作必须在下一个操作开始之前结束。
            2.封闭性：程序在封闭环境下运行，即程序运行时独占全机资源，资源状态(初始状态除外)，只有本程序才能改变它，程序一旦开始执行，其执行结果不受外界因素影响。
            3.可再现性：只要程序执行时环境和初始条件相同，当程序重复执行时，不论他是从头到尾的执行还是走走停停的执行，都可获得相同的结果。

    程序并发执行：
        1.程序的并发执行：
            两个语句之间不存在前驱关系，相互没有依赖就可并发执行。
        2.并发执行特征：
            1.间断性：程序执行走走停停
            2.失去封闭性：系统中多个资源处于共享状态，这些资源状态由这些程序来改变，其中一个程序运行时，其环境必定会受到其他程序的影响。
            3.不可再现性：由于失去了封闭性，那么程序执行结果可能与运行速度和运行顺序相关。

进程的描述：
    
    进程的定义和特征：
        1.进程的定义：
            为了使参与并发执行的每个程序(包含数据)都能独立地运行，在操作系统中必须为之配置一个专门是数据结构,称为进程控制块(Process Control Block)PCB。 系统利用PCB来描述进程的基本情况和活动过程，进行控制和管理进程，这样，由程序段，相关数据段，PCB三部分便构成了进程的实体，一般情况下，我们把进程实体简称为进程。例如：创建进程实际上便是创建进程实体中的PCB，而撤销进程，实质上也是撤销进程的PCB。
            比较典型的定义：
                1.进程是程序的一次执行
                2.进程是一个程序极其数据在处理机上顺序实行时所发生的活动。
                3.进程是具有独立功能的程序在一个数据集合上运行的过程，它是系统进行资源分配和调度的一个独立单位。
            进程是进程实体的运行过程，是系统资源分配和调度的独立单位。
        2.进程的特征：
            1.动态性：进程是动态的，程序是静态的。
            2.并发性：多行进程同时存在于内存中，并且能在一段时间内同时运行。
            3.独立性：进程实体是一个能独立运行，独立获得资源和独立接收调度的基本单位。
            4.异步性：进程按异步方式运行，即各自按独立的，不可预知的速度香甜推进。

    程序和进程的区别：
        程序性是指令和数据的集合，静态的。
        进程有自己的生命周期，动态的。
        进程是资源分配的独立单位
        进程是处理机调度的基本单位，可以与其他进程并发进行。
        同一个程序在不同数据集合上属于不同的进程。


进程的基本状态以及转换：
    
    进程的三种基本状态：
        1.就绪状态：不缺少除了CPU之外其他资源的状态。
        2.执行状态：不缺少任何资源，正在执行。
        3.阻塞状态：缺少除了CPU之外的其他资源。

    三种基本状态的转换：
        阻塞 -(取得资源)-> 就绪。
        就绪 -(进程调度)-> 执行。
        执行 -(时间片完)-> 就绪。
        执行 -(缺少资源)-> 阻塞。
        执行 -(执行完成)-> 终止。

    创建状态和终止状态：
        1.创建状态：完成PCB创建以及初始化工作，当完成PCB初始化之后，就从创建状态转化为就绪状态。
        2.终止状态：操作系统善后处理，将PCB清零兵归还给系统。

    挂起操作和进程状态转换：
        挂起与激活：
            挂起时进程处于静止状态，如果进程正在执行，则暂停执行，若处于就绪，则不接受调度。与挂起对应的是激活操作。
        1.挂起操作的引入原因：
            1.终端用户的需要。
            2.父进程的请求。
            3.负荷调节的需要。
            4.操作系统的需要。
        2.挂起原语操作后三个进程状态的转换：
            1.活动就绪 - 静止就绪
            2.活动阻塞 - 静止阻塞
            3.静止就绪 - 活动就绪
            4.静止阻塞 - 活动阻塞
        3.引入挂起操作后五个进程状态的转换：
            1.NULL - 创建
            2.创建 - 活动就绪
            3.创建 - 静止就绪
            4.执行 - 终止。


进程管理中的数据结构：

    1.操作系统中用于管理控制的数据结构。
        1.内存 - 内存表
        2.设备 - 设备表
        3.文件 - 文件表
        4.进程 - 进程x - 进程实体以及所用的资源表

    2.进程控制块PCB的作用：
        PCB作用：使得多道程序幻境下不能独立运行的程序(包含数据)成为一个能独立运行的基本单位，一个能与其他进程并发执行的进程。
        1.作为独立运行基本单位的标志
        2.能实现间断性运动方式
        3.提供远程管理所需要的信息
        4.提供进程调度所需要的信息
        5.实现了与其他进程的同步与通信。

    3.进程控制块中的信息：
        1.进程标识符
            1.外部标识符：方便用户对进程的访问，创建者提供，字母数字组成，描述了进程交租的关系。还有用户标识符指示拥有该进程的用户。
            2.内部标识符：方便系统对进程的使用，唯一的数字，通常是进程的序号.
        2.处理机状态:
            处理机状态也称处理机上下文，主要由各个寄存器和寄存器中的内容组成。
            1.通用寄存器：用户可是寄存器，用于残存信息，大多数处理机中有8-32个通用寄存器。
            2.指令寄存器：存放要访问的下一条指令地址。
            3.程序状态字PSW：包含状态信息，如：条件码，执行方式，终端屏蔽标志等
            4.用户栈指针：每个用户进程都有一个或若干个与之相关的系统栈。
        3.进程调度信息：
            1.进程状态
            2.进程优先级
            3.进程调度所需的其他信息
            4.事件：进程由执行状态转变为阻塞状态所等待发生的事件，即阻塞原因。
        4.进程控制信息：
            1.程序和数据的地址
            2.进程同步的通信机制
            3.资源清单
            4.连接指针

    4.进程控制块的组织方式：
        1.线性方式
        2.链接方式：静态链表
        3.索引方式

进程控制：

    处理机执行状态分系统态和用户态两种状态：
        系统态：又称管态或内核态，具有较高的特权，能执行一切指令，访问所有寄存器和存储区。传统的OS都在系统态运行。
        用户态：又称目态。具有较低特权的执行状态。仅能执行规定的指令，访问指定的寄存器和存储区.

操作系统内核:

    1.支撑功能:
        1.中断处理
        2.时钟管理
        3.原语操作: 原语特点:原子性,终端屏蔽性,不可分割
    2.资源管理功能:
        1.进程管理
        2.存储器管理
        3.设备管理
    3.进程的创建:
        1.进程的层次结构:
            子进程继承父进程可以拥有父进程所有的东西,包括权限与资源.
        2.进程图:
            用于描述进程间关系的一颗又向树.
        3.引起创建进程的事件:
            1.用户登录
            2.作业调度
            3.提供服务
            4.应用请求
        4.进程的创建
            1.申请空白PCB
            2.为新进程分配其运行所需的资源
            3.初始化进程控制块PCB
            4.如果进程就绪队列能够接纳新进程,便将新进程插入就绪队列.
    4.进程的终止:
        1.正常引起终止的事件:
            1.正常结束
            2.异常结束：
                1.越界错
                2.保护错
                3.非法指令
                4.特权指令错
                5.运行超时
                6.等待超时
                7.算术运算错
                8.IO故障
            3.外界干预
                1.操作员或操作系统干预
                2.父进程请求
                3.父进程终止
        2.进程的终止过程：
            1.根据被终止进程的标识符，从PCB集合中检索出该进程的PCB。从中读出状态。
            2.若被终止进程处于执行状态，应立即终止该进程的执行，并设置调度标志位真。用于指示该进程被终止后应重新进行调度
            3.若该进程还有子孙进程，应将其所有子孙进程都予以终止，防止他们成为不可控进程。
            4.将被终止进程所拥有的全部资源归还给其父进程或归还给系统。
            5.将被终止进程的PCB从所在队列中移除，等待其他程序来搜集信息。
    5.进程的阻塞与唤醒
        1.引起进程阻塞和唤醒的事件：
            1.向系统请求共享资源失败
            2.等待某种操作完成
            3.新数据尚未到达
            4.等待新任务的到达
        2.进程阻塞过程：
            执行过程中，如果发生了上述事件，进程便通过调用阻塞原语block将自己阻塞。
        3.进程唤醒过程：
            当被阻塞所期待的事情发生，获取所期待的数据已经到达，则由有关进程(比如提供数据的进程)调用唤醒原语wakeup，将等待该事件的进程唤醒。
            wakeup执行过程：先把被阻塞的进程从等待该事件的阻塞队列中取出，将其PCB中线性状态由阻塞改为就绪，然后将PCB插入就绪队列中。
    6.进程的挂起与激活：
        1.进程的挂起：
            系统中出现挂起事件时，OS利用挂起原语suspend将制定进程或处于阻塞状态的进程挂起。suspend的执行过程：首先检查被挂起进程的状态，若处于活动就绪状态，便将其改为静止就绪。对于活动阻塞状态就改为静止阻塞。
        2.进程的激活：
            当系统中发送激活进程的事件时，OS将利用激活原语active，将指定进程激活。
            静止就绪 - 活动就绪
            静止阻塞 - 活动阻塞


进程同步：

    1.进程同步的基本概念：
        1.两种形式的制约关系：
            1.间接相互制约关系：
                多个程序并发执行时，由于共享系统资源，知识这些执行的程序之间形成相互制约的关系。
            2.直接相互制约关系：
                某些应用程序，为了完成某项任务而建立了两个或多个进程。这些进程将为完成统一任务相互合作，他们之间的制约关系，就是源于他们之间的相互合作关系。
        2.临界资源：
            临界资源在诸进程间应采用互斥方式，实现对这种资源的共享。
        3.临界区：
            每个进程中访问临界资源的那段代码被称为临界区。
            访问临界资源的循环进程描述：
                while(TRUE){
                    进入区
                    临界区
                    退出区
                    剩余区
                }
        4.同步机制应遵循的规则：
            1.空闲让进
            2.忙则等待
            3.有限等待
            4.让权等待

    2.硬件同步机制：
        1.关中断
            实现互斥最简单的方法，即进入锁测试之前关闭中断，知道完成锁测试并上锁之后才能打开中断。这样在临界区便不会发送调度。
            缺点：
                1.滥用关中断权利可能导致严重的后果
                2.关中断时间过长会影响效率，限制处理器交叉执行程序的能力
                3.关中断方法不适用于多CPU系统
        2.利用 Test-and-Set指令实现互斥：
            借助一条硬件指令-“测试并建立”指令TS事项互斥方法， 现代很多计算机中投提供这种指令：
            boolean TS(boolean *lock){
                boolean old;
                old = *lock;
                *lock = TRUE;
                return old;
            }
            利用TS实现互斥的循环进程结构如下：
            do{
                while TS(&lock);    //skip
                //执行
                lock = FALSE;
            }while(TRUE);
        3.利用Swap指令实现进程互斥：
            该指令成为对称指令，用于交换两个字的内容。
            过程描述：
            void swap(boolean *a, boolean *b){
                boolean temp;
                temp = *a;
                *a = *b;
                *b = temp;
            }
            互斥过程：
            do{
                key = TRUE;
                do{
                    swap(&lock,&key);
                }while(key!=false);
                //临界区操作
                lock = FALSE;
            }while(TRUE);
            该方式不符合让权等待原则。

    3.信号量机制：
        1.整形信号量：
            定义为一个用于表示资源数目的整形量S，他与一般整形量不同，处理促使花之外，仅能通过两个标准的原子操作 wait(S) 和 signal(S)来访问。长久以来，这两访问被称作P，V操作。
            描述如下：
            //P(S) 申请
            wait(S){ 
                while(S<=0);
                S--;
            }
            //V(S) 释放
            signal(S){
                S++;
            }
            缺陷：未遵循让权等待原则。
        2.记录型信号量：
            相比整形信号量，多了让权等待原则。
            除了一个用于代表资源数目的整形变量value之外，还应增加一个进程链表指针list。
            数据项描述：
                typedef struct{
                    int value;
                    struce process_control_block *list;
                }semaphore;
            PV操作：
                wait(semaphore *S){
                    S->value--;
                    if(S->value<0)
                        block(S->list);     //如果资源不足，挂起进程
                }
                
                signal(semaphore *s){
                    S->value++;
                    if(S->value<=0)
                        wakeup(S->list);    //说明还有进程被阻塞，唤醒进程
                }
        3.AND型信号量：
            基本思想：
                将进程在整个运行过程中多需要的所有资源，一次性全部地分配给进程，待进程使用完成后再一起释放。即对进程所申请的资源要么全部满足，要么一个也不分配。
        4.信号量集：
            对AND信号量扩充：即对一个进程资源类型不同的所有进程，在一次PV操作中全部申请和全部释放。

    4.信号量的应用：
        1.利用信号量实现进程互斥
        2.利用信号量实现前趋关系

    5.管程机制：
        1.管程的定义：
            系统中各种硬件资源和软件资源均可用数据结构抽象的描述其资源特性，即用少量的信息和对资源执行的操作来表征该资源，而忽略他们内部结构的实现细节。
            管程由四部分组成：
                1.管程的名称
                2.局部于管程的共享数据结构说明
                3.对该数据结构进行操作的一组过程
                4.对局部于管程的共享数据设置初始值的语句
            管程的特征：
                1.模块化
                2.抽象数据类型：不仅由数据，还有对数据的操作
                3.信息掩蔽：管程内部数据对外部不可见，仅供管程调用
        2.条件变量：

经典的进程同步问题：
    生产者消费者问题
    哲学家进餐问题
    读者写者问题

进程通信：
    
    低级进程通信缺点：
        1.效率低
        2.对用户不透明
    OS该机通信工具优点：
        1.使用方便
        2.高效地传递大量的数据

    进程通信类型：
        共享式存储器系统
        1.基于共享数据结构的通信方式
        2.基于共享存储区的通信方式

    管道通信系统：
        为了协调双方通信。管道机制必须协调一下三方面的能力：
            1.互斥
            2.同步
            3.确定对方是都存在

    消息传递系统：
        直接通信方式
        间接通信方式

    客户服务器系统：
        1.套接字
            1.基于文件类型
            2.基于网络型
        2.远程过程调用和远程方法调用
            1.本地过程调用者以一般方式调用远程过程在本地关联的客户存根，将控制权转交给客户存根。
            2.客户存根执行
            3.略

    消息传递通信的实现方式：
        1.直接消息传递系统
            1.直接通信原语
                1.对称寻址方式
                2.非对称寻址方式
            2.消息格式
            3.进程同步方式
            4，通信链路
        2.信箱通信
            1.信箱结构
                1.信箱头
                2.信箱体
            2.信箱通信原语
                1.邮箱的创建和撤销
                2.消息的发送和接收
            3.信箱的类型
                1.私用邮箱
                2.公用邮箱
                3.共享邮箱


线程的基本概念：

    线程的引入：
        1.进程的两个基本特性：
            1.进程是一个可拥有资源的独立单位，一个进程要能独立运行，它必须拥有一定的资源，包括用于存放程序的正文，数据的磁盘和内存地址空间。
            2.进程同时又是一个可独立调度的基本单位。
        2.程序并发执行所需付出的程序开销：
            1.创建进程
            2.撤销进程
            3.进程切换
        3.线程 - 作为调度和分配的基本单位：

    线程与进程比较：
        线程可以称作轻型进程
        1.调度的基本单位：
            在同一进程中，线程切换不会引起进程的切换
            在不同进程中，线程切换会引起进程切换。
        2.并发性：
            同一进程中多个线程可以并发执行。
        3.拥有资源：
            进程可拥有资源，并作为系统中拥有资源的一个基本单位。
            线程本身并不拥有系统资源，而是仅有一点必不可少的，能保证独立运行的资源。
        4.独立性：
            统一进程中的不同线程要比不同进程之间的独立性要低得多
        5.系统开销：
            线程的开销较小。
        6.支持多处理机系统：
            传统进程只能运行在一个处理机中，多线程进程可以运行在不同处理机上。

    线程状态和线程控制块：
        1.线程运行的三个状态：
            执行 就绪 阻塞
        2.进程控制块TCB
        3.多线程OS中的进程属性
            1.进程是可拥有资源的基本单位
            2.多线程可以并发执行
            3.进程已不是可执行的实体

    线程的实现：
        1.线程的实现方式
            1.内核支持线程KTS（Kernel Support Thread）
            2.用户级线程ULT （User Level Thread）
                优点：
                    1.线程转换不需要转换到内核空间
                    2.调度算法可以是进程专用的
                    3.用户级线程的实现与OS平台无关
                缺点:
                    1.系统调用的阻塞问题
                    2.在单纯用户级线程实现方式中，多线程应用不能利用处理机多重处理的优点。
            3.组合方式：
                多对一
                一对一
                多对多
        2.线程的实现：
        3.线程的创建和终止


###############################################################################
*******************************************************************************
###############################################################################

第三章 处理机调度和死锁

    处理机调度层次：
        1.高级调度
        2.低级调度
        3.中级调度

    处理机调度算法的目标：
        1.处理机调度算法的共同目标：
            1.资源利用率：
                CPU利用率= CPU有效工作时间/(CPU有效工作时间+CPU空闲等待时间)
            2.公平性：
                各个进程都获得合理的CPU时间，不会发生进程饥饿现象
            3.平衡性：
                保持系统资源使用的平衡性
            4.策略强制执行：
                对于指定的策略，只要需要就必须强制执行，即使会造成某些工作延迟也要执行。
        2.批处理系统目标：
            1.平均周转时间
            2.系统吞吐量高
            3.处理机利用率高
        3.分时系统目标：
            1.响应时间快
            2.均衡性
        4.实时系统目标：
            1.截止时间的保证
            2.可预测性

作业与作业调度：

    批处理系统中的作业：
        1.作业和作业步：
            1.作业：不仅包含了程序和数据，还应有作业说明书，系统根据说明书来对程序进行控制。
            2.作业步：通常，在作业期间，每个作业都必须经过若干相对独立又相互关联的顺序加工步骤才能得到结果。
                编译 连接 运行
        2.作业控制块JCB：
        3.作业运行的三个阶段和三种状态
            三个阶段：后备状态，运行状态，完成状态
            三个阶段：
                1.收容阶段：建立PCB并放入作业后备队列
                2.运行阶段：当作业被作业调度选中后，便为它分配必要的资源和建立进程，并将它放到就绪队列。一个作业从第一次进入就绪状态开始到运行结束之前，均处于运行态。
                3.完成阶段：当作业完成或发生异常情况而提前结束时，作业便进入完成阶段，响应的状态为完成状态。

    作业调度的主要任务；
        1.接纳多少个作业
        2.接纳哪些作业

    先来先服务FCFS和短作业优先SJF调度算法：
        1.先来先服务(First-come First-served FCFS)调度算法
            这是最简单的调度算法，既可以用于作业调度，也可用于进程调度。
        2.短作业优先(Short Job First SJF)调度算法：
            以作业的长短来计算优先级，作业越短，优先级越高。
            缺点：
                1.必须预知作业运行时间
                2.对长作业非常不利
                3.采用SJF算法时，人机交互无法实现
                4.该调度算法完全为考虑作业的紧迫程度，不能保证紧迫性作业及时完成。

    优先级调度算法和高响应比优先调度算法：
        1.优先级调度算法(priorty-scheduing algorithm PSA)
            系统从后备队列中选取若干个优先级最高的作业装入内存.
        2.高响应比优点调度算法(Highest Response Ratio Next HRRN)
            优先权 = (等待时间 + 要求服务时间)/要求服务时间
            优先权 = (响应时间)/要求服务时间
            1.若作业等待时间相同，则要求服务时间越短，优先权越高
            2.要求服务时间相同，作业优先权又取决于等待时间
            3.对于长作业优先级，可以随等待时间增加而提高，当其等待时间足够长时，也可获得处理机。


进程调度：

    进程调度的任务 机制 方式：
        1.进程调度的任务：
            1.保存处理机的现场信息
            2.按某种算法选取进程
            3.把处理器分配给进程
        2.进程调度机制
            1.排队器：
                为了提高进程调度的效率，应事先将系统中所有的就绪队列按照一定的策略排成一个或多个队列，以便调度程序能最快的找到它。每当有一个进程转变为就绪状态时，排队器便将他们插入对应的就绪队列。
            2.分派器：
                依据进程调度所选定的程序将其从就绪队列中取出，然后进行从分派器到新选出进程间的上下文切换，将处理机分派给新选出的进程。
            3.上下文切换器：
                1.第一对上下文切换：保存当前进程的上下文，再装入分派程序的上下文，以便分派程序运行。
                2.第二对上下文切换：移除分派程序的上下文，把新选程序的CPU现场信息装入到处理机各个寄存器中，以便新选程序运行。
        3.进程调度方式：
            1.非抢占方式：
                一旦处理机分配给某个进程之后，就一直让它运行下去，直至该进程完成或发送某事件阻塞才把处理机交给其他进程。
                这种模式下，可能引起程序调度的因素有：
                    1.正在执行的进程执行完毕，或因为某时间无法继续执行下去
                    2.正在执行的性质提出IO请求，暂停执行。
                    3.在进程通信或同步过程中执行了某种原语操作。
                非抢占式优点：
                    实现简单，系统开销小，适合大部分批处理系统。
                缺点：
                    不能用于分时系统和大多数实时系统。
            2.抢占式：
                允许调度程序根据某种规则，去暂停某个真正执行的进程，将已分配给该进程的处理机重新分配给另一进程.
                优点:
                    防止一个进程长期占用处理机,以保证更加公平的服务.
                    在分时系统中,只有抢占式才可能实现人机交互
                缺点：
                    抢占方式复杂，所付出的系统开销比较大。
                抢占必须遵循的原则：
                    1.优先权原则
                    2.短进程有限原则
                    3.时间片原则

    轮转调度算法：(Round Robin RR)
        1.轮转法基本原理：
            系统将所有进程按FCFS策略排成一个就绪队列。每隔一个时间片就切换一次。保证就绪队列中所有进程都能在确定的时间段内获得一个时间片的处理机时间。
        2.进程切换机：
            1.时间片未用完，但任务完成，就立即激活地调度程序，将它从就绪队列中删除，再调度就绪队列的队首的进程运行，并启动一个新的时间片
            2.在一个时间片用完时，计时器中断处理程序被激活，如果进程尚未运行完毕，调度程序就把它送向队列的末尾。
        3.时间片大小的确定：
            时间片不宜过短也不易过长。

    优先级调度算法：
        1.有限调度算法的类型：
            1.非抢占式优先级调度算法。
            2.抢占式优先级调度算法
        2.优先级的类型：
            1.静态优先级
                在进程创建时就确定，在进程运行整个期间保持不变。确定优先级的依据如下：
                    1.进程类型 - 系统高于用户
                    2.进程对资源的需求 - 需求小的优先
                    3.用户要求
                特点：简单易行，系统开销小，但不够精确，可能出现低优先级的进程长期没有被调度的情况。
            2.动态优先级：
                在进程创建之初就赋予了一个优先级，随着进程的推进或等待时间增加而改变，以便获得更好的调度性能。

    多队列调度算法：
        将就绪队列从一个拆分为多个，不同类型或性质的就绪队列放在不同的队列中，不同的队列采取不同的调度算法，一个就绪队列中的进程可以设置不同的优先级，不同就绪队列本身也可设置优先级。

    多级反馈队列(multileved feedback queue)调度算法
        1.调度机制：
            1.设置多个就绪队列。
            2.每个队列都采用FCFS算法。
            3.按队列优先级调度。
        2.调度算法性能：
            1.终端型用户。
                终端用户提交的作业属于交互型作业，通常较小，将其放在第一队列规定的时间内完成，便可使终端用户满意。
            2.批处理短作业用户：
                对于这类作业，如果再第一队列完成，便可获得与终端用户同样是响应时间，对于稍长的作业，在第二，第三队列中各执行一段时间，仍然可以获得较短的周转时间。
            3.长批处理用户：
                对于长作业，依次在 1 - n 的各队列中按轮转的方式运行，用户不必担心作得不到处理。


    基于公平原则的调度算法：
        1.保证调度算法：
            该算法可以做到调度的公平性。如系统中有n个相同类型的进程同时运行，为公平起见，须保证每个进程都获得相同的处理时间1/n
            试试公平调度算法需要具有这样一些功能：
                1.跟踪计算每个进程子创建以来已经执行的处理时间。
                2.计算进程应获得处理机的时间，即自创建以来的时间除以n
                3.计算进程获得处理机时间的比率，即进程实际执行的处理时间和应获得的处理机时间之比。
                4.比较各路进程获得时间的比率。
                5.调度程序应选择比率较小的进程将处理机分哦给他，并让该进程一直运行，知道超过最接近它的进程比比率为止。
        2.公平分享调度算法：


实时调度：
    
    实现实时调度的基本条件：
        1.提供必要的信息
            1.就绪时间
            2.开始截止时间和完成截止时间
            3.处理时间
            4.资源需求
            5.优先级
        2.系统处理能力强：
            提供系统处理能力的途径有二：
                1.采用单处理机系统，但须增强其处理能力，显著的减少对每一个任务的处理时间。
                2.采用多处理机系统。
        3.采用抢占式调度机制：
        4.具有快速切换机制。
            1.对中断的快速响应能力。
            2.快速的任务派发能力。

    实时调度算法分类：
        按不同方式分类：
            1.根据实时任务性质，可将实时调度的算法分为硬实时调度算法和软实时调度算法。
            2.按调度方式，可分为非抢占式调度算法和抢占式调度算法。
        1.非抢占式调度算法：
            1.非抢占式轮转调度算法
            2.非抢占式优先调度算法
        2.抢占式调度算法：
            1.基于始终中断的抢占式优先级调度算法
            2.立即抢占的优先级调度算法

    最早截止时间优先EDF(Earliest Deadline First)算法：
        截止时间越早，优先级越高。
        1.非抢占式用于非周期实时任务。
        2.抢占式用于周期实时任务。

    最低松弛度优先LLF(Least Laxity First)算法.

    优先级倒置：
        1.优先级倒置的形成
        2.优先级倒置的解决方法

死锁概述：

    1.资源问题：
        1.可重用性资源和消耗性资源：
            1.可重用性资源：
                可重用资源具有以下性质：
                1.每一个可重用资源的单元只能分配给一个进程使用，不允许多个进程共享。
                2.进程在请求使用可重用资源必须按照这样的顺序：
                    1.请求资源，请求失败则会倍阻塞或者循环等待。
                    2.使用资源
                    3.释放资源
                3.系统中对每一类可重用资源的单元数目是相对固定的，进程在运行期间不能创建也不能删除.
            2.可消耗性资源：(临时资源)
                是程序运行期间动态创建的资源，具有如下性质：
                    1.数目才程序运行期间可变
                    2.进程可不断的创造这些资源。
                    3.进程可以申请这些资源，消耗后不再归还，通常是生产者创建，消费者消耗。最典型的就是进程间通信的信息。
        2.可抢占性资源和不可抢占性资源：
            1.可抢占性资源：
                这种资源不会引发死锁，常见的有CPU和主存均为可抢占性资源。
            2.不可抢占性资源：
                分配给进程之后不能强制收回，只能等进程用完之后自行释放。是引起死锁的条件之一。

    2.计算机系统中的死锁：
        死锁通常源于多个进程对资源的争夺。
        1.竞争不可抢占性资源引起死锁
        2.竞争可消耗资源引起死锁
        3.进程推进顺序不当引起死锁
            推进顺序合法
            推进顺序不合法

    3.死锁的定义，必要条件和处理方法：
        1.死锁的定义：
            进程各自占有资源，但是都在等待其他进程释放资源引起死锁。
        2.产生死锁的必要条件：
            1.互斥条件：
                进程占有资源后该资源不能被其他进程使用。
            2.请求和保持条件：
                进程已经请求了一个资源，但有提出了新的请求，所请求资源被其他进程占有，此时进程阻塞，但对自己已获得的资源不释放
            3.不可抢占条件：
                进程以获得的资源在未使用完之前不能被抢占，只能由完成时自己释放
            4.循环等待条件：
                发送死锁时，必然存在一个进程-资源的循环链。
        3.处理死锁的方法：
            1.预防死锁：
                通过设置某些限制条件去破坏产生死锁的四个必要条件中的一个或几个来预防死锁，预防死锁是一种易实现的方法，已被广泛使用。
            2.避免死锁：
                统一采用实现预防，但不是采取限制破坏死锁产生的必要条件，而是在资源动态分配过程中，采用某种方法防止系统进入不安全状态，避免发生死锁。
            3.检测死锁：
                这种方法不加任何限制，运行运行过程中产生死锁，但可通过检测机构检测出死锁的发送，通过采取适当的方式，把这些进程解放出来。
            4.接触死锁：
                常用方法就撤销一些进程，回收他们的资源，将他们分配给已处于阻塞状态的进程，使其能够运行。
            四种方法从上之下，防范程度依次减弱。



预防死锁：

    1.破坏 请求保持 条件：
        为了达到这种目的，有一下两种协议可以实现：
        1.第一种：进程运行之前必须一次性申请整个运行过程中的全部资源。
            优点：
                简单 易行 安全。
            缺点：
                资源被严重浪费。
                进程经常会发生饥饿现象
        2.第二种：允许一个进程只获得初期运行所需的资源后便开始运行。在运行过程中再逐步释放已分配给自己的，且已经用完毕的全部资源，然后再请求所需资源

    2.破坏 不可抢占 条件:
        该方法实现比较复杂，而且付出代价很大。

    3.破坏 循环等待 条件：
        规定每个用户按序号递增的顺序申请资源。


避免死锁：

    1.系统安全状态：
        系统进入不安全状态，可能发生死锁。
        1.安全状态： 
            允许程序动态的申请资源，但系统分配资源之前会先计算资源分配的安全性，若不会导致不安全，则分配，否则让进程等待。
        2.安全状态之例：
            判断是否存在安全序列，安全序列肯不唯一。
        3.由安全状态向不安全状态的转变：
            进行安全计算，只有安全时ceiling分配资源。

    2.利用银行家算法避免死锁：
        新进程进入系统之后，必须申明在运行过程中，可能需要每种资源类型的最大单元数目，其数目不应超过系统所拥有资源总量。
        当进程请求一组资源时，首先确定是否有足够的资源分配给该进程，若有，再进一步计算资源分配后系统是否会处于不安全状态，如果不会，才会分配资源，否则，进程等待。
        1.银行家算法数据结构：
            1.可利用资源向量 Available
            2.最大需求矩阵 Max
            3.分配矩阵 Allocation
            4.需求矩阵 Need  Need[i, j] = Max[i, j] - Allocation[i, j];
        2.银行家算法：
            设Reguest 是进程 P 所请求的向量，如果Request[j] = K, 表示进程P需要K个Rj类型资源，请求发出后，按一下步骤检测：
                1.检测申请数量是否超过所宣布的最大数量，若超过直接报错，否则下一步。
                2.如果请求数量小于等于可分配数量，则下一步，否则等待
                3.试分配
                4.执行安全算法
        3.安全算法：
            1.设置两个向量：
                1.Work 表示系统可供给给进程继续运行所需的资源数目，包含有m个元素，在执行算法之初，Work = Available
                2.Finish 表示系统有足够的资源分配给进程，使之运算完成。 开始时Finish[i]=false,当有足够的资源分配给进程时， 再令Finish=true；
            2.从进程集合中找到一个能满足下述条件的进程
                1.Finish[i]=false;
                2.Need[i,j] <= Work[i,j];
                若找到执行步骤3 否则步骤4
            3.当进程Pi获得资源之后，可顺利执行，直至完成，并释放出分配的资源,故应该：
                Work[j] = Work[j] + Allocation[i, j];
                Finish[i] = true;
                回到步骤2
            4.如果所有的进程Finish[i]都能满足，则表示系统处于安全状态，否则处于不安全状态。



死锁的检测与解除：
    
    如果不采取死锁预防措施也没有避免死锁的算法，系统很可能发生死锁，这种情况下，系统应提供两个算法：
        1.死锁检测算法
        2.死锁解除算法

        1.死锁的检测：
            为了能对系统中是否已经发生了死锁进行检测，在系统中必须：
                1.保存有相关资源的请求分配信息。
                2.提供一种算法检测系统是否已经进入死锁状态
            1.资源分配图：略
            2.死锁定理：
                S为死锁状态的充分条件是：
                    当期人晋档S状态的资源分配图是可以完全化简的。

    2.死锁的解除：
        常用解除死锁方法：
            1.抢占资源，从一个或多个进程中抢占足够数量的资源，分配给死锁进程，以解除死锁状态。
            2.终止或撤销进程： 终止系统中一个或多个死锁进程。
        1.终止进程的方法：
            1.终止所有死锁进程
            2.逐个终止进程
                终止顺序所考虑的因素：
                    1.进程优先级
                    2.进程已执行的时间，还需要的时间
                    3.进程在运行过程中已使用的资源，还需的资源
                    4.进程的性质是交互式的还是批处理式的
            2.付出代价最小的死锁解除算法：
                略



###############################################################################
*******************************************************************************
###############################################################################

第四章 存储器管理


存储器的层次结构：

    1.多层结构的存储器系统
        1.存储器多层结构 P120
            通用计算机其存储层次至少三层
            最高层：
                CPU寄存器
            中间： 主存
                高度缓存
                主存储器
                磁盘缓存
            底层： 辅存
                固定磁盘
                移动磁盘
            高层：容量小 速度快 价格高
            底层：容量大 速度慢 价格低
    2.可执行存储器
            寄存器和主存储器为可执行存储器。

    2.主存储器与寄存器
        1.主存储器
            简称内存或主存，用于保存进程运行时的程序和数据，也称可执行存储器。
        2.寄存器
            具有与处理机相同的速度，但价格昂贵，容量比较小。

    3.高速缓存和磁盘缓存
        1.高速缓存：介于寄存器和主存之间。主要用于备份主存中教常用的数据，以减少对主存的访问次数，这样可大幅度提高执行速度。
        2.磁盘缓存：介于主存和磁盘之间。主要为了缓解主存和磁盘之间的速度匹配。


程序的装入和链接：

    程序运行一般要经过一下步骤：
        1.编译：对源程序编译成为若干模块
        2.链接：将编译后形成的一组目标模块以及他们所需要的库函数链接在一起，形成一个完成的装入模块。
        3.装入：将装入模块装入内存。

    1.程序的装入：
        1.绝对装入方式：
            当计算机系统很小，且仅能运行单道程序是，完全有可能知道程序驻留在内存的什么位置，此时可采用绝对装入。
        2.可重定位装入：
            根据内存具体状况将装入模块装到内内存的合适位置。
        3.动态运行时装入：
            在运行时才将逻辑地址转换为物理地址。

    2.程序的链接：
        1.静态连接： 
            1.对相对的地址进行修改
            2.变换外部调用符号
        2.装入时动态链接：
            1.便于修改和更新
            2.便于实现对目标模块的共享。
        3.运行时动态链接：
            1.加快装入过程
            2.节省大量内存空间

连续分配存储管理方式：

    1.单一连续分配

    2.固定分区分配
        1.划分分区的方法：
            1.分区大小相等：
                缺点是缺乏灵活性，造成大量内存空间浪费。
            2.分区大小不等：
                增加了一点灵活性。
        2.内存分配：
            为了便于分配，通常将分区按大小排队，并建立一张分区使用表。
            其中各个表项包括每个分区的其实地址，大小，状态。

    3.动态分区分配
        1.数据结构：
            常用数据结构有以下两种形式：
                1.空闲分区表
                2.空闲分区链
        2.动态分区算法：
            略
        3.分区分配操作：
            1.分配内存
            2.回收内存
                区分回收区前后是否存在空闲区，有则合并


    4.基于顺序搜索的动态分区算法：
        1.首次适应算法(First Fit FF)  每次都从头查，第一个合适的
        2.循环首次适算法(Next Fit NF) 从上一次停下来的地方查，第一个合适的
        3.最佳适应算法(Beat Fit BF)   寻找刚好适合的
        4.最坏适应算法(Worst Fit WF)  寻找最大的

    5.基于索引搜索的动态分区分配算法：
        1，快速适应算法：
            分类搜索法，将空闲分区根据容量大小分类，每一类具有相同容量的所有分区。单独设立一个空闲分区链表，这样系统中就存了多个空闲分区链表。同时建立一张管理索引表。
            使用方法：
                1.根据长度从索引表中找到一块最小的适合空间
                2.从链表中去下第一块进行分配
            缺点：在合并有效分区时比较麻烦
        2.伙伴系统:
        3.哈希算法：

    6.动态可重定位分区分配：
        1.紧凑：将零碎分区合并成为大分区
        2.动态重定位：
        3.动态重定位分区分配算法

对换

    1.多道程序环境下的对换技术：
        1.对换的引入：    
            把内存中暂时不使用的程序和数据交换到外存上。
        2.对换的类型：
            1.整体对换
            2.页面(分段)对换

    2.对换空间的管理：
        1.对换空间管理的主要目标：
            1.对文件去管理的主要目标
            2.对对换空间管理的主要目标
        2.对换区空闲盘块管理中的数据结构：  
        3.对换空间的分配与回收
            考虑回收分区前后分区空闲情况

    3.进程的换入与换出：
        1.当内核因执行某操作而发现内存不足时，便调用对换进程。
        2.进程的换出：
            1.选择被换出的进程
                优先选择阻塞和睡眠状态的进程
            2.进程换出的过程：
                略
        3.进程的换入


分页存储管理方式：

    1.分页式存储管理
    2.分段式存储管理
    3.段页式存储管理

    1.分页存储管理的基本方法：
        1.页面和物理块：
            1.页面：
            2.页面大小 一般为2-8 Kb
        2.地址结构：
            31-12 ：页号P
            11-0  ：位移量W
        3.页表 页号到物理块号的映射地址

    2.地址变换机构：   
        将逻辑地址换换为物理地址
        1.基本地址变换机构
        2.具有快表的地址变换机构

    3.访问内存的有效时间

    4.两级和多级页表
        大页表解决方案
            1.对于页表所需空间可采用离散分配方式，以解决难以找到一块连续空间的问题
            2.只将当前所需页表部分调入内存，其余仍在磁盘上，需要时再调入
        1.两级页表
        2.多级页表

    5.反置页表：
        1.反置页表的引入：
            为每一个物理块设置一个表项，并将他们按物理块的编号排序，其内容则是页号和其所隶属的进程标识符


分段式存储：

    1.分段存储方式的引入    
        为什么要引入分段存储：
            1.程序都可分为若干段
            2.实现和满足信息共享，信息保护，动态链接，以及信息的动态增长，等需要。都要以段为单位。
        1.方便编程：
            将程序划分为若干段之后，只需要知道程序的段名和段内偏移地址即可，直观方便。
        2.信息共享：
            在实现程序和数据共享时，是以信息逻辑单位为基础的。
        3.信息保护：
            信息保护同样是以信息逻辑单位为基础的。
        4.动态增长。
        5.动态链接

    2.分段存储系统的基本原理：
        1.分段
            作业地址空间被划分为若干段，每段定义了一组逻辑信息。
            段号 + 段内地址
        2.段表
        3.地址变换
        4.分页和分段的主要区别：
            1.页是信息的物理单位
            2.页的大小固定且由系统决定
            3.分页的用户程序地址空间是一维的

    3.信息共享：
        1.分页系统中的信息共享
        2.分段系统中的程序好信息共享

    4.段页式存储管理方式：
        1.基本原理，先分段，后分页
            结构：段号 段内页号 业内地址
        2.地址变换过程：


###############################################################################
*******************************************************************************
###############################################################################

第五章 虚拟存储器
    
虚拟存储器概述：
    
    1.左右很大，其所要求的内存空间超过了内存中容量，作业不能全部装入内存，导致程序无法运行。
    2.有大量作业要求运行，但是内存容量不足以容纳这些作业，只能将少数作业调入内存先运行，其余仍在外存等待。

    1.常规存储管理方式和局部性原理
        1.常规存储管理器方式特征：
            1.一次性，作业一次性全部装入内存才能开始运行
            2.驻留性，作业装入内存后，就一直驻留在内存中
        2.局部性原理：
            1.程序执行时，除了少部分的转移和过程调用情况外，大部分是顺序执行的
            2.过程调用将会是程序的执行轨迹由一部分区域转向另一部分区域
            3.程序中存在很多循环结构，这些将被循环执行
            4.程序中还包括对很多数据结构的处理，这些处理往往在很小的范围内
            局限性又表现在一下两个方面：
                1.时间局限性：
                2.空间局限性
        3.虚拟存储器的基本工作情况：
            载入部分执行，如果要执行的部分为载入，则申请载入，如果内存已满，则置换暂时不用的进程。

    2.虚拟存储器的定义和特征：
        1.虚拟存储器的定义：
            用户感觉到的内存容量比实际的大。
        2.虚拟存储器的特征：
            1.多次性：作业呗分段多次载入内存
            2.对换性：置换暂时不用，调用要运行的
            3.虚拟性：从逻辑上扩充容量，使用户看到的内存容量远大于实际容量。 

    3.虚拟存储器的实现方法：
        1.分页请求系统：
            1.硬件支持：
                1.请求分页的页表机制
                2.缺页中断系统
                3.地址变换机构
            2.实现请求分页的软件
        2.请求分段系统：
            1.硬件支持：
                1.请求分段的段表机制
                2.缺页中断机构
                3.地址变换机构
            2.软件支持


请求分页存储管理方式：

    1.请求分页中的硬件支持
        1.请求页表支持，页表应包括：
            页号 物理块号 状态位P 访问字段A 修改位M 外存地址
            1.状态位；指示该页是否被调入内存
            2.访问字段：记录本页在一段时间内被访问次数
            3.修改位：标识该页调入内存后是否被修改过
            4.外存地址：通常是物理块号
        2.缺页中断机构：
            1.在指令执行期间产生和处理中断信号
            2.一条指令在执行期间可能产生多次缺页中断
        3.地址变换机构：   

    2.请求分页中内存分配：
        进程分配内存时，涉及三个问题：
            1.保存进程能正常运行，所需要的最小物理块数决定
            2.分配策略：可分配的物理块是固定的还是可变的
            3.为不同进程分配物理块数采用什么分配方法：平均分配还是按比例分配
        1.最小物理块数决定：
            能保证程序运行的做少物理块数
        2.内存分配策略：
            1.固定分配局部置换
            2.可变分配全局置换
            3.可变分配局部置换
        3.物理块分配算法：
            1.平均分配算法：
            2.按比例分配算法
            3.考虑优先权的分配算法

    3.页面调入策略：
        面临问题：何时调入，何处调入，如何调入。
        1.何时调入页面：
            1.预调页策略
            2.请求调页策略
        2.何处调入：
            1.外部对换区
            2.文件区
            3.UNIX方式
        3.调入过程

页面置换算法：

    1.最佳置换算法(Optimal):
        淘汰在未来最少使用的页面。
    2.先进先出算法(FIFO)
        淘汰最先进来的
    3.Lru算法(最近最少使用)：
        淘汰最近使用次数最少的
        硬件支持：
            1.寄存器
            2.栈
    4.LFU 最少使用
    5.NRU 最近未用





































