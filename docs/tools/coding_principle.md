SOLID

## 单一职责原则 single responsibility principle

任何一个软件模块都应该只对某一类行为者负责

来看一个正面例子，C标准库中的<math.h>模块就是用来处理数学相关的，<string.h>模块就是用来处理字符串相关的的，等等...，每个模块职责都比较明确。

模块化


## 开闭原则 open-closed principle

软件实体应当对扩展开放，对修改关闭（Software entities should be open for extension，but closed for modification）


## 里氏原则 LSP-Liskov Substitution Principle
 
使用基类对象指针或引用的函数必须能够在不了解衍生类的条件下使用衍生类的对象

> 任何基类可以出现的地方，子类一定可以出现

## 接口隔离原则 ISP-Interface Segregation Principle

不应强制客户端依赖于它们不使用的接口(Clients should not be forced to depend upon interfaces that they do not use.)

> 单一职责原则主要是约束类，它针对的是程序中的实现和细节；接口隔离原则主要约束接口，主要针对抽象和程序整体框架的构建

## 依赖倒置原则

高层次的模块不应该依赖低层次的模块，他们都应该依赖于抽象(High level modules should not depend upon low level modules. Both should depend upon abstractions)

抽象不应该依赖于具体实现，具体实现应该依赖于抽象(Abstractions should not depend upon details. Details should depend upon abstractions)

举例
![](https://i-blog.csdnimg.cn/blog_migrate/742ace05ed774b317ea02067f48343dd.png)

司机实现 driver 接口；这里的接口提供了一个依赖具体实现的方法 run(car:BMW)

后续变更，如果想要实现 能够开更多的车；在接口中增加每一个 依赖具体实现的方法 比如run(car:byd) 肯定是不合理；也违反开闭原则

因此，重新设计新加一个接口ICar 提供run接口，由不同的车来进行实现；后续再有其他类型 也只需实现接口扩展即可

![](https://i-blog.csdnimg.cn/blog_migrate/c32d993f14a55999291d8643d7dd0c36.png)

也即 代码要依赖于抽象的类，而不要依赖于具体的类；要针对接口或抽象类编程，而不是针对具体类编程

采用依赖倒置原则减少类间的耦合性，提高系统的稳定性，减少并行开发引起的风险，提高代码的可读性和可维护性