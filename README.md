# Game Programming Patterns 笔记
## 第一章 Introduction
### 设计模式的必要性
+ 当项目达到一定规模，会变得难以维护。 
+ 代码中时常存在许多可复用的精华（？），要避免重复发明(reinvent)解决方案。 
### 设计模式为什么十分适用于游戏编程
+ 时间和次序是游戏架构的核心  
+ 游戏循环中有许多游戏行为需要处理  
+ 各游戏行为相互有联系，需要组织  
+ 游戏最终的表演效果决定了游戏质量  
### 好的代码
+ 通常十分便于修改、改进。 
+ de-couping。即两块代码之间相对独立，修改其中的一个不必修改另一个。可以单独理解其中一个的原理。  
+ 在开发效率、运行性能、代码可读性之间寻找一个平衡。  
+ 临时性的代码永远是临时性的，正式性的代码必须要将临时性的代码重写(rewrite)。一个好的方法是用别的语言来书写临时性的代码。  
+ 简洁很重要。  
+ 在没有自信未来会需要代码那么灵活的话，不要浪费过多时间在设计Abstraction和decoupling上。  
## 第二章 Design Patterns Revisited  
多少都有接触过,没系统地理清概念  
### Command
将某些具体或不具体的函数（游戏行为）封装成类。  
### Flyweight
一些多个游戏对象使用的资源（元件）只创建一个实例，每个游戏对象以指针的方式调用它。  
### Observer
当游戏对象的某些状态发生改变时，对其Subject组件的多个Observer发出通知以响应改变。    
![ObserverImage](https://github.com/CurryPseudo/GameProgrammingPatterns-PersonalNote/blob/master/image/Observer_Achievement.png)  
### Prototype
以一个对象作为原型，生成该对象的克隆。（Unity中Prefab-Instantiate）    
对Self语言有了一定了解（基于原型的面向对象程序设计语言）  
### Singleton
当游戏中某个类只需要一个实例时(例如AudioPlayer)  
有两个方式应用Singleton：  
1. 类定义一个static类实例的指针，static方法instance在已创建实例的情况下返回实例指针，没创建实例的情况下创建实例。    
2. 类定义一个static flag以标记实例是否创建，若执行instance时已创建则警告。   
Singleton Pattern的目的是保证该类在整个过程只创建一个实例。  
### State 
+ 将状态定义成一个类，对象具有的每个状态能根据不同输出切换成另一个状态，对象根据当前状态执行不同行为。这么做可以简化代码中冗杂的逻辑判断。     
+ 在一些情况下需要对象有多个状态机。   
+ 状态可分层    
+ 状态机作为简单AI的应用。复杂AI用行为树~~还有机器学习~~。   
