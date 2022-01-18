# Chapter 14 详细设计Component-Level Design

软件体系架构图中各个部分（每一个类）组件的细化设计。以**分析类为依据**，对分析类进行细化补充

组件级(Component-Level)设计定义了分配给每个软件组件的数据结构，算法，接口特性和通信机制。

进行设计评审。检查设计以确定数据结构，接口，处理序列和逻辑条件是否正确。

![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled.png)

## 14.1 组件

（要看）

(面向对象的角度来说）组件不仅包含自己本身，而且还涉及一组合作类

要点：

1. Attributes——类的属性的详细定义
2. Operation——对内部方法进行定义（Activity Diagram→对

案例：打印商店

![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled%201.png)

2个接口：computeJob调用内部4个方法计算各个属性；initJob要进行建立工作，工作顺序排序等

![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled%202.png)

![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled%203.png)

## 14.3 进行组件级别设计

（重点重点！这章最重要的部分）

你必须将需求requirements和架构模型architectural model的信息转化为设计表示，以提供足够的细节来指导构建（coding和testing）活动。

**详细设计步骤：**

1. P认定与问题域Problem Domain对应的所有**设计类**（**根据分析类完善业务类的设计**）
2. I认定与基础域Infrastructure Domain对应的所有设计类(业务功能)——e.g: GUI类，操作系统有关的组件，数据管理有关的类(对数据库访问，比如软件架构图中连接数据库组件和其他子系统的数据库连接子系统的组件）

> 一些Infrastucture Domain相关的类的知识：①只有方法没有组件的类——接口类(没有内部结构，也没有associations)；②只有属性没有方法的类——全局变量初始化类，只定义常量的类；③与业务无关的类——界面类
> 
1. 详细阐述未获得作为可重用组件的所有设计类(对不用复用的业务类进行细化）——包括该类所需的所有接口，属性，操作，还得启发式设计（高内聚低耦合）
    1. 在类或组**件协作时，指定消息**详细信息(message details）
        
        ![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled%204.png)
        
        ![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled%205.png)
        
    2. 定义每个**组件的接口**(先定义消息message，再定义接口interface)
        
        ![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled%206.png)
        
    3. 定**义属性，数据的类型，和需要的数据结构**
        
        ![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled%207.png)
        
        ![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled%208.png)
        
    4. **详细描述每个类每个方法的处理流程**（利用**UML Activity Diagram**或**伪代码**）
        
        ![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled%209.png)
        
    
    1. 描述持久层的**数据源**（数据库或文件）并定义**数据管理类**(是在概要设计中进行的）——对概要设计中的数据进行review (持久的数据和相关的类）
    2. **Review**一下每个类的状态图是否合理，对设计类进行**行为建模**
        
        ![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled%2010.png)
        
        ![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled%2011.png)
        
    3. 画**部署图**，提供额外的实现细节(基于架构图）
    4. **重构**每个**组件级设计表示**(component-level design representation)，考虑备选方案。进行Review
    
    ![Untitled](Chapter%2014%20%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1Component-Level%20Design%20773b02d5513548fe811ce52375e9a92c/Untitled%2012.png)