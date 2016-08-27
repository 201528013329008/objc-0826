# objc-0826
翻译－苹果官方文档《Objective-C语言编程》(简书)
http://www.jianshu.com/p/b6434c2997d1
关于Objective-C
Objective-C
是你编写OS X以及iOS软件所使用的主要语言。它是对C语言的极大扩展，为其添加了面向对象编程的能力以及一套动态运行时的机制。Objective-C
继承了C语言的语法，基础数据类型以及流程控制语句，并且在这些基础之上添加了定义类和类方法的语法。Objective-C还在语言层面上支持对象结构管理和对象字面解释，使得用户能够动态输入和绑定代码，使得诸多功能在运行时生效。

概览
本文档对Objective-C语言进行了介绍，并针对其功用给出了详尽的示例。你将学习如何通过描述对象去自定义类，同时还将了解如何利用Cocoa和Cocoa Touch框架提供的类。尽管框架内定义的类并没有内嵌在Objective-C中，但想要使用Objective-C编程，离不开这些类。而且，诸多语言层面的功能都需要依赖这些由框架提供的类去执行。

一个应用就是一组对象的有机结合
当你为OS X或iOS编写应用时，大部分时间都将用了同各种对象打交道。这些对象都是Objective-C中类的实例对象，一部分属于框架内定义的类，剩下的则是你自己定义的类。

如果你要创造自定义类，应该从编写描述该类的接口文件开始，其应该显示使用该类须知的相关信息。这个接口文件应由若干用来封装数据的属性，以及一个方法列表组成。方法的声明表明了对象所能接收的消息，以及发送消息时应该传入的属性的信息。同时需要编写的还有实现文件，其包含所有被声明的方法的具体实现代码。

相关章节：类的定义，使用对象，数据封装
范畴是对现有类的拓展
如果想为现有类添加一些自定义的功能，不必再去创建一个新类，只需为其定义一个范畴，就可以做到这一点。利用范畴，你可以为任意一个现有的类添加自定义方法，即使你不知道这些类原本的实现代码，例如由框架提供的NSString类。

如果你知道一个类的源代码，你大可以利用类扩展来添加新的属性以及修改现有属性的特征。类扩展一般用来隐藏私有属性或方法，可以是在一个源代码文件中，也可以在一个自定义框架中。

相关章节：修改现有类
协议定义了消息发送的规则
一个基于Objective-C编写的应用中的主要工作机制是各种对象之间互相发送消息。通常情况下，对象可以接收的消息都通过在接口文件中声明的方法来表示。但有时，你可以定义一组相关的方法，不绑定任何特定的类，这种方式有其特殊的作用。

Objective-C利用协议来定义一组相关的方法，例如对象可以借由这些方法来调用其代理，这些方法可以是必须实现的，也可以是可选的。任何类都可以明确声明其遵守相关协议，这意味着其必须对协议中的所有必需实现的提供实现代码。

相关章节：使用协议
数据值和集合通常利用Objective-C对象来表示
在Objective-C中，通常用Cocoa或Cocoa Touch框架内所提供的类来表示数据值。NSString类用了表示字符串，NSNumber类用来表示不同类型的数字，例如整数或浮点数，NSValue类用来表示其他类型的数值，如C结构体。你也可以使用C语言提供的各种基本数据类型，如int，float，char。

集合一般通过集合类的实例对象来表示，诸如NSArray，NSSet，或NSDictionary，都可以用来容纳其他Objective-C对象。

相关章节：数据值和集合
代码块可以简化编码任务
代码块是C，Objective-C以及C++中所引入的语言特性。它可以用来表示执行特定任务的一组代码。其是对一组代码的封装，这同其他语言中的closure很像。代码块通常被用来简化编码任务，例如数据枚举，归类和测试。代码块也使并发和异步执行变的简单，方便的使用例如CGD等技术。

相关章节：使用代码块
错误对象用来表示运行时故障
虽然Objective-C包含了处理异常的语法，但Cocoa 和 Cocoa Touch只在编程错误发生时使用异常（例如超过了数据检索的范围），这些异常需要在应用交货前解决。

其他类型的错误，包括运行时故障，例如磁盘空间不够，无法连接网络等——会通过NSError对象来表示。你的应用应该对这些错误有所准备，并提供相应的解决方案，以便在这些错误出现时提供更好的用户体验。

相关章节：错误更正
Objective-C编码有据可循
当编写Objective-C代码时，你应遵循一定的规则。以方法名为例，首字母小写，包含多个单词时应使用驼峰规则编写，例如doSomething以及doSomethingElse。不只要注意大小写，可读性也非常重要：你的代码应当尽量具备良好的可读性，即方法名应当恰如其分的表达其含义，但又不能太罗嗦。

除此之外，还有一些规则是你在使用框架是应遵守的。以属性的存取方法为例，为了使用KVC或KVO技术，你必需严格遵循属性的命名规则。

相关章节：编码规则

阅读前提
如果你刚刚接触OS X或iOS开发，在阅读文档之前，你应该通读Start Developing iOS Apps Today或Start Developing Mac Apps Today，以便对应用开发有一个初步的了解。此外，你对xcode
也应该具备一定的了解，因为本文档大部分章节的末尾都附有相关练习，需要使用xcode完成。xcode是用来创建iOS和OS X应用的开发环境。你讲使用它编写代码，设计应用的交互界面，测试应用，以及排除bug。

虽然读者最好具备一些C语言或基于C语言的其他编程语言的基础，如Java或C#，本文档还是包含了C语言基础特性的例子，如流程控制语句。如果读者拥有其他高级语言的知识，如Ruby或Python，那么就可以顺利阅读。

本文档将涉及到面向对象编程的相关概念，特别是适用于Objective-C语言的。本文档假定读者具备基本的面向对象编程的概念，如果你对这些概念还不够熟悉，请阅读相关章节：Concepts in Objective-C Programming。

相关拓展
本文档的内容适用于xcode4.4以以上，并假定应用的目标系统是OS X10.7以上或iOS 5以上。跟多关于xcode的信息，参见Xcode Overview。跟多语言版本方面的信息，参加Objective-C Feature Availability Index.

Objective-C应用利用引用计数来管理对象的声明周期。大多数情况下，编译器的ARC特性将为你解决这一问题。如果你无法使用ARC，或者需要转换或维护旧的代码，这些代码需要使用手动引用计数，请参阅Advanced Memory Management Programming Guide。

除了编译器，Objective-C利用运行时系统来使用它的动态和面相对象的特性。虽然一般读者无需担心Objective-C是怎样工作的，但还是有可能接触到运行时系统，请参阅Objective-C Runtime Programming和Objective-C Runtime Reference。

类的定义（2015.6.23）
当你为OS X / iOS 编写程序时，大部分时间都将与对象打交道。Objective-C中的对象同其他面相对象的编程语言一样：它们将自身所代表的数据同相关的行为整合起来。

一个应用是由诸多互相通讯的对象结合起来的有机整体，其目的是完成特定的功能。如显示人机交互界面，相应用户的输入，存储信息等。对于OS X / iOS 开发来说，你无需从零创建各种对象；相反你已经有Cocoa / Cocoa Touch 框架所提供的包含相当数量的对象的库，可供使用。

有些对象是利等可用的，例如字符串和数字等基本类型，又例如一些用户交互界面的元素，像按钮和表格视图。还有一些对象需要你亲自编写代码规定规定它们的行为。应用开发的过程牵涉到如何最优使用底层框架提供的对象，如何编写自定义对象，如何使二者协同工作，从而为应用带来其独特的优点和功能。

在面相对象编程的术语中，一个对象是一个类的实例。本章解释了如何在Objective-C中定义一个类，声明它的接口（包含类和其实例的使用方法）。接口文件含有一个类对象可以接收的消息列表，所以你还需要为类匹配相应的实现。实现包含对象接收到消息时所需执行的代码。

类是对象的蓝图
一个类是对所有类对象共同行为和属性的描述。对于一个字符串对象来说（在Objective-C中，这是NSString类的一个实例对象），类提供各种检验和转换对象内部字符的方式。类似的，用来描述代表数字的类（NSNumber）针对对象内部包含的数字提供了各种功能，例如将数字之转换为不同的类型。

正如根据同一个蓝图可以创建出许多外表不同的大楼，但其内部结构都是相同的。类的每个实例对象都共有某些同样的属性和行为。每个NSString实例对象都有相同的行为，不过它到底代表什么样的字符串数值。

任何一个对象自创建之初，其目的都是具有某个特定的功能。读者也许知道一个字符串对象代表了某个字符串，但无需知道它用来储存这些字符串的内部机制。读者对于它用来处理字符串的内部机制一无所知，但需要知道怎样使用这个对象去完成读者想要达成的功能，比如要求其返回特定的字符，或着完成对字符串大小写的转换，并返回全新的字符串。

在Objective-C中，类的接口文件详细描述了其他对象应如同类对象互动。换句话说，它是公开的，实例对象如何同外界联系的说明。

可变性决定了对象所代表的数值是否可以被更改
有些类规定其实例对象是不可变的。这意味着其内部数值必需在对象被创建之初就填入，随后不可以被其他对象更改。在Objective-C中，所有的基本NSString和NSNumber数据类型都是不可变的。如有读者需要一个对象来表示一个新的数值，那么就需要再创建一个NSNumber对象。

有些不可变类还拥有一个可变的版本。如果读者的确需要在运行时该表一个字符串的内容，例如在字符串后面添加从网络接收到的新的字符，那么就可以使用一个NSMutableString类的实例对象。这个类的实例对象同NSString类的对象具有相同的行为，除此之外，它还具备改变其所代表的字符串的功能。

尽管NSString和NSMutableString是两个不同的类，但它们有着许多相似之处。相比于分开编写这两个类，重复它们的相似之处，利用继承来编写它们是更好的选择。

继承自其他类的类
在自然世界中，生物分类学利用诸如种，属，族之类的字眼来讲不同种类的动物划分到相应的群组当中。这些群组具有层级结构，例如某些种都隶属于一个属，某些属都隶属于一个族。例如，人类，大猩猩，猿有着许多相似之处。虽然他们分属于不同的种，甚至不同的属，但它们在生物分类学上都从属于同一个族（称为“人科”），见表1-1.

在面相对象编程的世界里面，对象同样被划分为有层级之分的群组。虽然没有像动物分类学那样利用专门的术语去表示，但对象根据其所属的类被划分为不同群组。正如人类从“人科”那里继承了某些特征，一个类也可以从其父类那里继承某些功能。

当一个类继承自另一个类，子类就继承了父类所定义的所有属性和行为。另外它还可以自定义自身所特有的行为或属性，甚至重新定义父类的行为。

以Objective-C的字符串类为例，NSMutableString的父类是NSString，见表1-2.NSMutableString具有NSString的所有功能，例如查找特定的自负，返回新的改变大小写的字符串等，但NSMutableString在此基础之上额外添加了一些方法，例如能够让用户在现有字符串末尾添加新的字符，替换或删除字符串或字符等。

根类提供基本功能
正如所有的生物都都具备某些声明特征，在Objective-C中所有的对象都具有某些基本功能。但一个Objective-C对象需要同一个来自其他类的实例对象协同工作时，它要求这个对象能够具备某些基本的特性和功能。为此，Objective-C为所有类指定了一个根类，被称为NSObject。当一个对象遇到另一个对象，它们就可以利用NSObject类所定义的基本行为进行互动。

当读者编写自定义类时，至少应该继承自NSObject。总的来说，自定义类应该继承自Cocoa / Cocoa Touch 框架内的能够提供最接近读者需求的类。

如果你想为一个iOS应用制作一个按钮，而现有的UIButton类无法满足你的需求，那么就应该创建一个继承自UIButton的自定义类，而非NSObject。如果继承自NSObject，你首先就需要复制所有UIButton的功能，跟别说UIButton以外的功能了。另外，通过继承自UIButton，你的自定义类讲自动获得未来针对UIButton的各种修复和改进。

UIButton类自身继承自UIControl，其定义了所有iOS界面控件的基本行为。UIControl又继承自UIView，使得其可以具备显示在屏幕上。UIView继承自UIResponder，允许其响应用户输入，如点击，手势和设备摇晃。最后，在继承树的最底层，UIResponder继承自NSObject，见表1-3.

继承链意味着任何继承自UIButton的自定义类不仅将继承UIButton的功能，还将得到继承链向上所有超类的功能。读者最后将得到一个具备按钮功能的对象，它可以将自己显示在屏幕上，响应用户输入，同其它对象互动。

时刻注意你所使用的类在继承链中的位置非常重要，这样才可以明确类的功能。通过帮助文档中的类参考，读者可以轻松找到继承链中的所有超类，如果你在类的接口文件，或参考中找不到某个属性或方法，那么它很可能定义在超类中。

接口文件定义了类对象的互动方式
面相对象编程的好处之一就是前面所提到过的——要使用一个类，读者只需知道如何与该类的类对象交互即可。更准确的说，一个对象应该将其内部实现细节隐藏起来。

举例来说，如果你在一个iOS应用中使用标准的UIButton对象，你无需担心当按钮出现在屏幕上时对象如何处理与像素的关系。你只需要知道通过改变对象某些特性，例如按钮的标题和颜色，按钮就可以在屏幕上正确的现实出来即可。

当读者定义自己的类时，要搞清楚哪些属性和行为应该公之于众。哪些特性是可以由其他对象访问的？这些特性可以被改变吗？其他对象如何同自定义类的实例对象沟通？

这些信息都被包含在接口文件中——它定义了读者想让其他对象如何同自定义类的实例对象互动。公共接口和内部行为，即实现文件的描述应该分开。在Objective-C中，接口代码和实现代码通常被放在不同的文件但中，需要公开的信息放在接口文件即可。

基本语法
Objective-C用来声明类接口的语法如下所示：

@interface SimpleClass: NSObject

@end
以上例子声明了一个名为SimpleClass的类，继承自NSObject。

公共属性和行为利用@interface声明。在本例中，除了父类之外，什么都没有声明，所以SimpleClass的实例对象的功能全部继承自NSObject。

属性是对象内部数据的入口
通常，对象都拥有属性以共外接访问其内部数据。如果读者定义一个类来记录联系人，那么可能就需要相应的字符串代表一个人的名和姓。

这些属性应该显示在接口文件中，如：

@interface Person : NSObject
@property NSString *firstName;
@property NSString *lastName;
@end
在本例中，Person类声明了两个公共属性，都是NSString类的实例对象。

这两个属性都是Objective-C对象，所以使用*表示它们是C指针。语句的写法也同C语言一样，末尾要有;作为结尾。

也许还需要再添加一个属性来作为一个人的出生年份，这样就可以根据年份统计而非姓名。添加一个代表数字的对象如下：

@property NSNumber *yearOfBirth;
可是如果只是简单的存储一个数值，对于NSNumber来说似乎有点大材小用。另一种方法是使用C语言提供的基本类型，保存一个整数：

@property int yearOfBirth;
属性的特性表明了数据存取和储存的限制
上面的例子中所有的属性都完全对外界开放。这意味着其他对象可以读取和改变属性所代表的数值。

而有些情况下，你也许需要声明一个不能被改变的属性。在真实的世界当中，一个人想要改名，必需完成办很多手续。如果读者编写的是一个官方的人事记录软件，就可能需要讲名字设定为只读。任何想要改变名字的请求都必须通过另一个中间对象来审核，包括批准或者拒绝。

Objective-C的属性声明可以包括特性。特性可以用来表示，包括但不限于，一个属性是否为只读。在官方的人事纪录软件汇总，Person类的接口类似于：

@interface Person : NSObject
@property (readonly) NSString *firstName;
@property (readonly) NSString *lastName;
@end
属性特性在括号中声明，紧跟@property关键字，详见章节为公开数据声明公共属性。

方法声明代表对象可以接收的消息
目前为止针对类的声明都是典型的模型对象，即用来封装数据的对象。在Perosn类的例子当中，也许除了存取属性声明的变量以外，不需要其他任何额外的功能。但对于大多数类来说，它们都包含访问自身属性意外的功能。

鉴于Objective-C应用是许多对象结合成的有机整体，可以知道这戏对象可以通过发送消息进行交互。在Objective-C术语中，A对象向B对象发送消息被称为调用B对象的方法。

Objective-C方法在概念上同C函数类似，而语法上却很不一样。一个C函数声明类似于：

void SomeFunction();
而对应的Objective-C方法声明则类似于：

- (void)someMethod;
在本例中，方法没有形参。位于头部的C语言括号内的void关键字表示当方法完成时其不返回任何值。

位于方法名开头的-（减号）表示这事一个实例方法，可以针对类的任意实例对象使用。与之相对的是类方法，可以针对类本身使用，详见章节Objective-C的类也是对象。

同C函数的原型类似，接口内的方法声明同C语言表达式一样，需要一个;结尾。

方法可以接收形参
如果读者需要声明一个可以接收一个甚至多个形参的方法，语法同C语言大不一样。

对于一个C函数来说，形参在括号内部声明：

void SomeFunciton(SomeType value);
而Objective-C方法则把形参作为其名称的一部分声明：

- (void)someMethodValue: (SomeType)value;
同返回类型一样，形参的类型放在括号里，正如一个标准的C语言类型转换符一样。

如果读者需要提供多个形参，语法形式同C语言也不相同。C函数的多个形参都放在括号里，由都好分隔；而在Objective-C中，接收两个形参的方法的声明类似于：

- (void)someMethodWithFirstValue: (SomeType)value1 secondValue: (AnotherType)value2;
在本例中，value1和value2的名称在方法被调用时指代传入的实参，就像使用变量那样。

有些编程语言允许函数通过所谓的命名实参来定义；然而在Objective-C中却不是这样。方法中形参的顺序必需同方法声明一致。事实上secondValue部分属于方法名的一部分，可以写作：

someMethodWithFirstValue:secondValue:
这是可以大大提升Objective-C语言可读性的众多特性之一。其原理是通过方法调用传入的值是方法的一部分，紧邻相关的方法名，详见章节你可以将对象传给方法作为形参。

注：value1和value2变量名并非是方法声明的一部分，这意味着在方法实现中不一定要使用完全一致的变量名。只需要记住方法的特征相符即可，包括方法名，形参类型和返回类型必需相同（以及方法类型——by 作者）。
例如，以下方法同上面的方法特征完全相符，是一个方法：

- (void)someMethodWithFirstValue: (SomeType)info1 secondValue: (AnotherType)info2;
以下这些方法同上面的方法特征不符：

- (void)someMethodWithFirstValue:(SomeType)info1 anotherValue:(AnotherType)info2;
- (void)someMethodWithFirstValue:(SomeType)info1
secondValue:(YetAnotherType)info2;
类名必需唯一
必需注意在一个应用当中每个类的名称都必须唯一，包括不能同框架所提供的现成类重名。如果在一个项目中读者创建了一个同已有类通明的自定义类，编译器将发出警告。

因此，对于读者自定义类，最好加上相应的前缀，不少于三个字母或更多。前缀可能同你目前所编写的应用相关，也可能是你以前写出的可以重复利用的代码，或者只是你名字的首字母缩写。

本文档给出的所有例子中类都带有前缀：

@interface XYZPerson : NSObject
@property (readonly) NSString *firstName;
@property (readonly) NSString *lastName;
@end
注（历史遗留）：如果你还对为什么这么多类都有NS作为前缀，这是因为Cocoa / Cocoa Touch 的一些历史原因。Cocoa最开始作为编写NeXTStep操作系统下的应用程序而生。1996年苹果公司并购了NeXTStep公司，并将NeXTStep融入OS X系统，其中就包括当时其所用的类名。Cocoa Touch 是Cocoa的iOS版本；有些类同时存在于Cocoa / Cocoa Touch 当中，同时也有很多类分别从属于这两个框架。两个字母的前缀NS和UI被苹果公司保留使用，读者不应该再去使用。
至于方法名和属性名，只需在其所被定义的类中唯一即可。

尽管应用中的每个C函数的名称都必须为一，而对于Objective-C类的方法来说，多个类拥有同一个名称的方法是完全可以接受的（同时也是比较方便的）。在一个类中同一个方法你只能声明一次，但是，如果你要覆盖父类已经定义的方法，就需要再次写出这个方法，重新声明。

关于方法，对象的属性以及实例变量（相关章节大多数属性都同实例变量有关），这些在类中具有唯一的名称即可。不过，如果读者要使用全局变量，那么其名称在整个应用或者项目中必需唯一。

更多有关命名的惯例和建议，详见惯例。

类的实现定义了其内部行为
当读者定义了类的接口之后，包括各项公开的属性和方法，接下来就需要编写代码实现类的行为。

正如早前所说的，类的接口代码通常被单独放在一个指定的文件当中，通常称为头文件，其扩展名是｀.h｀。读者应该在扩展名为.m的实现文件中编写类的实现代码。

当接口代码被放在接口文件中时，读者应该在编写实现文件之前告诉编译器读取接口文件。Objective-C提供一个预编译指令，#import来完成这一任务。这个指令同C语言的#include很类似，但不同之处在于其可以确保相同的文件在编译器期间只被读取一次。

请注意预编译指令跟C语言指令不同，其末尾没有;.

基本语法
类的实现的基本语法如下：

#import "XYZPerson.h"
@implementation XYZPerson
@end
如果你在接口中声明了方法，那么就必须在此文件中实现它们。

方法实现
对于简单的，只有一个方法的类接口来说，实现如下：

@interface XYZPerson : NSObject
- (void)sayHello;
@end
其实现类似于：

#import "XYZPerson.h"
@implementation XYZPerson
- (void)sayHello {
    NSLog(@"Hello, World!");
}
@end
这个例子使用了NSLog()函数来向控制台发送一条文字消息。这个函数同C语言库中的pritf()函数很类似，可以接受任意数量的形参，其中第一个形参必需是一个Objective-C字符串对象(NSString)。

方法的实现代码同C函数的定义很相似，都是用大括号将实现代码括起来。其中，方法名，返回值和形参的类型必需和在接口文件中的声明一致。

Objective-C同C语言一样，区分大小写，所以以下方法：

- (void)sayhello {
}
同上面的sayHello方法相比，将被编译器当作两个完全不同的方法来处理。

总的来说，方法名应该由小写字母开头。相较于C函数，Objective-C的命名惯例跟多的使用描述性的名称了给方法取名。如果一个方法名包含多个单词，则使用驼峰拼写来保证可读性。

请注意空行在Objective-C中的使用很多。可以将代码块利用tab或space进行适当的缩进，读者将经常看到半个括号独占一行，例如：

- (void)sayHello
{
    NSLog(@"Hello, World!");
}
作为OS X / iOS 的整合开发环境，Xcode会自动帮读者缩进代码。详见Xcode Workspace Guide。

Objective-C中的类也是对象
在Objective-C中，类本身就是一个模糊的对象类型，称为类对象。类对象不能像普通对象那样声明属性，但是却可以接受消息。

类对象的典型应用是一种类方法，叫做工厂方法。是除了通过内存分配和初始化来以外的创建类的实例对象以外的一种方法（详见章节对象是动态创建的）。以NSString类为例，其具有多个创建空字符串对象或带初始化字符串对象的工厂方法，包括：

+ (id)string;
+ (id)stringWithString:(NSString *)aString;
+ (id)stringWithFormat:(NSString *)format, ...;
+ (id)stringWithContentsOfFile:(NSString *)path encoding:(NSStringEncoding)enc
  error:(NSError **)error;
+ (id)stringWithCString:(const char *)cString encoding:(NSStringEncoding)enc;
根据以上例子可知，类方法通过+（加号）表示，同实例方法的-有所区分。

类方法的原型可能会在接口中声明，正如实例方法的原型一样。类方法同实例方法一样都需要在@implementation中实现。

使用对象
在一个Objective-C应用中，大部分工作都发生在诸多对象之间互相发送消息的基础上。有些对象属于Cocoa / Cocoa Touch 框架所提供的类，有些则由读者的自定义类创建。

第一章讨论了定义接口和实现的语法，包括为了能够回应所接收的消息而实现相关方法的语法。本章将讲解如何向对象发送消息，还会涉及到一些Objective-C的动态特征，包括动态输入以及运行时方法的调用机制。

在创建一个可用的对象之前，必需首先利用一套内存分配技术为其属性分配内存，必要时还需要为其内部数值附上合适的初始值。本章将讲解如何运用消息嵌套技术为对象分配内存，进行初始化。

对象发送和接收消息
尽管在Objective-C中对象之间发送消息的方法不止一种，但目前来说，最常用的发送消息的基本语法是用方括号，如：

[someObject doSomething];
左边的指代物，即someObject，是消息的接收者。右边的消息，doSomething，是被调用的接收者的方法的方法名。换句话说，当以上代码被执行时，someObject将会被发送doSomething消息。

上一章曾讲过如何为类创建接口，如下：

@interface XYZPerson : NSObject
- (void)sayHello;
@end
另外还讲过如何创建实现，如下：

@implementation XYZPerson
- (void)sayHello {
    NSLog(@"Hello, world!");
}
@end
注：本例使用了Objective-C的字符串@"Hello, world!"。字符串是Objective-C中允许通过字符串语法创建的类的实例对象之一。需要特别指出@"Hello, wordl!"即是一个代表Hello, world!字符串的Objective-C字符串对象。字符串对象的创建会在稍后在本章讲解，详见对象是动态创建的。
假设想在有一个XYZPerson对象，你可以向其发送sayHello消息，如下：

[somePerson sayHello];
发送Objective-C消息从概念上来说同调用C函数很相似，表1-2表示对象在收到sayHello消息后的流程。

为了弄清对象如何接受消息，就必须知道在Objective-C中指针是怎样指代对象的。

利用指针追踪对象
C和Objective-C都利用变量来追踪数值，这根大多数编程语言一样。

在标准C语言中有一组基础标量变量，包括整数，浮点数，字符，它们的声明和赋值如下所示：

int someInteger = 42;
float someFloatingPointNumber = 3.14f;
本地变量，即在一个方法或函数内声明的变量，如下所示：

- (void)myMethod {
    int someInteger = 42;
}
它们的作用范围被限制在声明它们的方法/函数之内。

在本例中，someInteger是myMethod内的本地变量；一旦程序执行到了最后的大括号，someInteger就不再能够被访问了。当一个本地的标量变量（如int或float）消失，它所代表的值也随之消失。

Objective-C对象，相反，在内存分配方面却略有不同。对象的声明周期通畅要比一个方法的作用范围要长。特别需要指出的是，对象的声明周期通常要比用来指代它的变量的声明周期更长。所以，关于对象的内存的释放和回收是动态的。

注：如果你知道栈和堆，那么可以说本地变量是分配在栈中的，而对象是分配在堆中的。
这就要求读者利用C指针（其保存内存地址）来追中对象在内存中的地址，例如：

- (void)myMethod {
    int someInteger = 42;
}
虽然指针变量myString的作用域仅限于myMedthod，但它指向的字符串对象却能够在内存中有着更长的声明周期。它可能早就被创建出来，又或者你需要调用其它方法来将它传至另一个指针。

你可以将对象作为形参床给方法
如果发送消息时需要传递对象，那么读者应该在形参的位置填入指向该对象的指针。前面章节讲解了声明带有一个参数的方法的语法：

- (void)someMethodWithValue:(SomeType)value;
因此声明接受一个字符串对象的方法的语法应该类似于：

- (void)saySomething:(NSString *)greeting;
你可以为saySomething方法做出以下实现：

- (void)saySomething:(NSString *)greeting {
    NSLog(@"%@", greeting);
}
指针greeting的作用范围仅限于saySomething方法，即使它指向的字符串对象在方法被调用之前就已经存在，并且其在方法执行完毕之后还将继续存在。

注：NSLog()函数利用格式说明符来指代转换说明的顺序，这点同C语言的printf()函数一样。控制台输入的文字是通过在格式化字符串（第一个实参）中插入替换值（其它实参）实现的。在Objective-C中，还有一个额外的转化说明%@，用来指代一个对象。在运行时，这个说明符将通过向其所指代的对象发送descriptionWithLocale:消息或者description消息来完成对其的替换。description方法由NSObject类实现，将返回对象所属的类以及其在内存内的地址，但许多Cocoa / Cocoa Touch框架的类都覆盖了这一方法，代之以提供给更有用的信息。对于NSString类来说，description方法将返回其代表的字符串数据。若需要了解 更多关于NSLog()函数和NSString的格式化说明符的内容，请参见String Format Specifiers。
方法可以返回一个值
既然可以向方法的形参传入数值，那么方法也可以返回数值。目前为止本章节的所有方法的返回值都是void。C语言void关键字意味着方法不会返回任何值。

返回值类型是int的方法表示其会返回一个int型的标量值：

- (int)magicNumber;
方法的实现代码利用C语言的return语句表示其返回一个值。这个值在方法执行完毕后被传回到调用方，例如：

- (int)magicNumber {
    return 42;
}
读者可不不去理会方法的返回值。正如在本例中，magicNumber方法并没有任何事情，只是返回了一个值，但待用方法本身不存在任何问题：

[someObject magicNumber];
如果读者需要追中方法的返回值，那么可以声明一个变量，然后将方法调用的返回值付给它，例如：

int interestingNumber = [someObject magicNumber];
当然方法也可以返回一个对象。以NSString类为例，它有一个uppercaseString方法：

- (NSString *)uppercaseString;
它的用法同返回标量值的方法一样，唯一的区别是你需要哟过一个指针来追踪其返回的结果（对象）：

NSString *testString = @"Hello, world!";
NSString *revisedString = [testString uppercaseString]
当这一方法执行完毕并返回时，reviseString指针将指向一个NSString对象，其代表代表字符串HELLO WORLD!。

要记住当一个方法执行完毕，并返回一个对象是，例如：

- (NSString *)magicString {
    NSString *stringToReturn = // create an interesting string...
    return stringToReturn;
}
字符串对象将在方法执行完毕后继续存在（已经被传走），尽管指向它的指针stringToReturn已经消失。

在这种情况下，读者需要考虑一些内存管理的问题：一个被方法返回的独享（在堆上创建）的声明周期需要足够长，以便方法的调用者能够使用它，但是，这并非意味着其永远不会消失，因为这样会带来内存泄露的问题。大多数情况下，Objective-C编译器的ARC特性将替你处理这些问题。

对象可以向自身发送消息
当你编写实现代码时，你可以使用一个重要的隐藏值，self。理论上来说，self用来指代：接受此消息的对象。它是一个指针，正如上面用到的greeting一样。另外它还可以用来向当前接受消息的对象发送消息。

你可能觉得应该重构XYZPerson类的实现代码，在sayHello方法中调用saySomething方法，这样的话就可以只将NSLog()函数放到一个独立的方法中。这意味着你有可以在此基础之上创造更多的方法。如sayGoodbye，这会调用saySometing方法，来处理真实的问候过程。如果随后还想在用户界面的文本框里展示各种问候用语，你只需要改变saySomething方法即可，而不需要去单独调整每个问候方法。

新的实现代码利用self来向当前对象发送消息，例如：

@implementation XYZPerson
- (void)sayHello {
    [self saySomething:@"Hello, world!"];
}
- (void)saySomething:(NSString *)greeting {
    NSLog(@"%@", greeting);
} @end
如果读者利用更新过后的实现代码向一个XYZPerson对象发送sayHello消息，那么程序流程图应该如图2-2所示。

对象可以调用父类实现的方法（2015.6.24）
在Objective-C中，还有一个读者可以使用的重要的关键字，super。向super发送消息可以调用调用相应的由继承链上一级的父类实现的方法。super最常见的用法是覆盖父类的方法。

假设你需要创建一个全新的类，名称为shouting person，它的所有问候语都将用大写字母显示。你可以完全复制XYZPerson类，然后将每个方法内的字符串都改成大些字母，但最简单的方法是创建一个继承自XYZPerson类的子类，然后覆盖saySomething方法，这样就可以以大写字母显示所有问候，例如：

@interface XYZShoutingPerson : XYZPerson
@end
@implementation XYZShoutingPerson
- (void)saySomething:(NSString *)greeting {
    NSString *uppercaseGreeting = [greeting uppercaseString];
    NSLog(@"%@", uppercaseGreeting);
}
@end
上面的例子声明了一个额外的字符串指针uppercaseGreeting，然后将向原来的greeting对象发送uppercaseString消息后返回的值赋给它。正如读者前面看到的，通过这样的方法可以获得一个全新的字符串，其是在原字符串单基础之上将所有字母变成大写后得到的。

由于XYZPerson类实现了方法sayHello，而且XYZShoutingPerson是XYZPerson的子类，所以你也可以向XYZPerson类的实例对象发送sayHello消息。当你调用XYZShoutingPerson类的sayHello方法时，[self saySomething:...]消息用将会调用覆盖后的方法，即将所有字母转换成大写，如流程图2-3所示。

然后新的实现方法并不完美，因为如果你稍后想要修改XYZPerson类中的saySomething方法的实现的话（在用户界面显示问候语，而非控制台），你就需要同时在XYShoutingZPerson类中修改实现。

一个较为理想的方法是修改XYZShoutingPerson类的saySomething方法实现，通过调用父类（XYZPerson）的实现去处理问候语：

@implementation XYZShoutingPerson
  - (void)saySomething:(NSString *)greeting {
     NSString *uppercaseGreeting = [greeting uppercaseString];
    [super saySomething:uppercaseGreeting];
  }
@end
现在如果想一个XYZShoutingPerson类对象发送sayHello消息，其流程图如图2-4所示。

对象是动态创建的
正如本章前面所介绍的，对于一个Objective-C对象来说，其内存分配是动态的。创建对象的第一步是分配内存，不仅要确保一个类中所定义的属性得到了妥善的内存分配，还有确保其所有父类的属性也得到了妥善的分配。

根类NSObject提供了一个方法，可以为读者完成这一步骤：

+ (id)alloc;
要注意这一方法的返回类型是id。在Objective-C中，这是一个特殊的关键词，表示某种类型的对象。它是一个指向对象的指针类似于NSObject *，但它的使用不加*（星号）。在章节Objective-C是一门动态语言中有更详细的描述。

alloc方法还有一个重要的任务，就是将分配给对象属性的内存晴空，将值设为0。这避免了由于内存曾经储存的数据所引发的错误，但若要初始化对象，这是不够的。

读者需要将alloc方法的调用和init方法的调用结合起来，init是另一个NSObject类所定义的方法：

- (id)init;
init方法被用来在对象创建之初将一个类的所有属性设置为合适的初始值，下一张将会对它有更详细的讨论。

注意init方法的返回值类型是id。

如果一个方法返回一个指向对象的指针，那么就可以将调用这个方法的消息嵌入到另一个消息中，这个方法返回的对象将作为外围消息的接收者。正确的内存分配和初始化潜逃顺序如下：

NSObject *newObject = [[NSObject alloc] init];
上面的例子将newObject指针指向一个新创建的NSObject类的实例对象。

最内部的调用被首先执行，所有NSObject类收到了alloc消息，然后返回一个内存分配好的新的NSObject对象实例。这个被返回的对象然后被用做init消息的接收者，这又将返回一个对象，指针newObject将指向它，如表2-5所示。

注：init方法有可能返回一个同alloc方法所创建的对象相比完全不同的对象，所以最好的方法是将两个方法嵌套发送。任何被初始化的对象都必须分配指针。例如，以下代码是错误的：
NSObject *someObject = [NSObject alloc];
[someObject init];
如果对init方法的调用返回了一个一个其它的对象，那么读者将得到一个指向内存分配过，但并没有被初始化。

初始化方法可以接收实参
有些对象必须被初始化为指定的值。以一个NSNumber对象为例，其被许被初始化为它所能代表的数字值。

NSNumber类包含若干初始化方法，包括：

- (id)initWithBool:(BOOL)value;
- (id)initWithFloat:(float)value;
- (id)initWithInt:(int)value;
- (id)initWithLong:(long)value;
带实参的初始化方法同原本的init方法使用方法一样——一个NSNumber对象的内存分配和初始化过程如下：

NSNumber *magicNumber = [[NSNumber alloc] initWithInt:42];
工厂方法是内存分配和初始化这一过程的补充
正如前面章节所述，一个类也可以定义工厂方法。工厂方法是内存分配和初始化这一过程的另一种选择，这样就不用再潜逃两个方法。

NSNumber类定义了若干工厂方法来对应相应的初始值类型，包括：

+ (NSNumber *)numberWithBool:(BOOL)value;
+ (NSNumber *)numberWithFloat:(float)value;
+ (NSNumber *)numberWithInt:(int)value;
+ (NSNumber *)numberWithLong:(long)value;
工厂方法的使用方法如下：

￼NSNumber *magicNumber = [NSNumber numberWithInt:42];
这个工厂方法同前面的alloc] init]作用完全一样。工厂方法会直接调用alloc和相应的init方法，从而使对象创建变得简单。

使用new方法创建不需要初始化不需要实参的对象
另外，同样可以使用'new'方法创建实例对象。这个方法有NSObject类提供，而且不用在子类的实现中覆盖。

以下方法同不需要任何实参的alloc和init过程效果相同：

XYZObject *object = [XYZObject new];
// is effectively the same as:
XYZObject *object = [[XYZObject alloc] init];
使用简便字面量语法创建对象
有些类允许读者使用更简单的字面量语法去创建实例对象。

例如，你可特殊的字面标记来创建一个NSString实例对象，例如：

NSString *someString = @"Hello, World!";
以上方法同使用alloc + init的组合，或者工厂方法的效果完全相同：

NSString *someString = [NSString stringWithCString:"Hello, World!"
                                          encoding:NSUTF8StringEncoding];
NSNumber类同样可以使用许多字面量语法：

NSNumber *myBOOL = @YES;
NSNumber *myFloat = @3.14f;
NSNumber *myInt = @42;
NSNumber *myLong = @42L;
再次重申，这些例子中字面量语法的同使用初始化方法或工厂方法的效果完全相同。你还可以利用括号表达式来创建复杂的NSNumber对象：

NSNumber *myInt = @(84 / 2);
在上面的例子中，括号内的表达时先被计算，计算的结果将被用来创建一个NSNumber对象。

Objective-C也支持用字面量语法创建不可变的NSArray对象和NSDictionary对象；将在相关章节值和集合中做进一步讨论。

Objective-C是一门动态的语言
如前所述，读者需要一个指针来追踪内存中的对象。由于Objective-C的动态本质，追踪对象所使用的指针类型其实并不重要——当向一个指向特定类型对象的指针发送消息时，不管指针的类型如何声明，程序总是会调用符合对象类型的正确的方法。

id类型定义了一个指向通用类型对象的指针。完全可以在声明一个指针变量时使用id作为其类型定义，但这样的话编译器就不能根据指针类型提供相应的信息。

请思考下面的代码：

id someObject = @"Hello, World!";
[someObject removeAllObjects];
在上面的例子中，someObject将直线一个NSString实例对象，但编译器出了知道这个实例对象术语某个类，其它的一无所知。removeAllObjects方法是由某个Cocoa / Cocoa Touch框架内的类定义的，因此编译器不会发出警告，即使在程序运行时这段代码会由于NSString对象无法相应removeAllObjects方法而产生异常错误。

使用静态类型重写以上代码：

NSString *someObject = @"Hello, World!";
[someObject removeAllObjects];
现在编译器将会及时发出警告，因为它已经知道someObject对象的类型是NSString，不能相应removeAllObject方法。

由于一个对象的类型只能等到运行时才能确定，所以当读者为对象分配指针是，指针的类型并没有什么作用。若要使用XYZPerson或XYZShoutingPerson类，你可以编写以下代码：

XYZPerson *firstPerson = [[XYZPerson alloc] init];
XYZPerson *secondPerson = [[XYZShoutingPerson alloc] init];
[firstPerson sayHello];
[secondPerson sayHello];
尽管firstPerson和secondPerson都被声明为指向XYZPerson类实例对象的指针，但是，在运行时，secondPerson将会指向一个XYZShoutingPerson实例对象。当sayHello消息被分别发送给两个对象时，程序会各自调用正确的实现方法；对于secondPerson来说，意味着XYZShoutingPerson类内所定义的实现。

判断对象是否相等
如果读者需要判断一个对象是否同另一个对象相同，要注意所有的对象都是由指针追踪的。

标准的C语言使用==（相等运算符）来判断两端的标量所代表的值是否相等，如：

if (someInteger == 42) {

// someInteger has the value 42
      }
在处理对象时，==用来判断两个不同的指针是否指向同一个对象：

if (firstPerson == secondPerson) {
    // firstPerson is the same object as secondPerson
}
如果读者需要判断两个对象是否代表相同的数据值，就需要使用由NSObject类定义的方法isEqual:

if ([firstPerson isEqual:secondPerson]) {
    // firstPerson is identical to secondPerson
}
如果读者需要比较一个对象所代表的数据大于或者小于另一个对象，不能简单的使用C语言的比较操作符<和>。而是应该使用一些foundation框架所提供的基本类型，如NSNumber，NSString和NSDate类，这些类提供一个compare方法：

if ([someDate compare:anotherDate] == NSOrderedAscending) {
    // someDate is earlier than anotherDate
}
使用nil
这声明标量变量时就直接对其赋值，是比较好的做好。否则的话它们的初始值会受到以前处于栈内的内容的污染，从而产生错误：

BOOL success = NO;
int magicNumber = 42;
然而对于指向对象的指针来说就不需要，因为如果读者在声明指针时没有给它们赋初始值，编译器会自动将它们标记为nil：

XYZPerson *somePerson;
// somePerson is automatically set to nil
如果你暂时还没有对象可以作为初始值赋给指针，那么nil值是最安全的选择。因为在Objective-C中可以向nil发送消息。如果读者向nil发送了消息，什么都不会发生。

注：如果读者想更确切的知道向nil发送消息的返回值，如下：对于返回值类型为对象的消息来说，其返回值为nil；数字类型的是0；布尔类型的是NO；结构体类型的全部结构成员都会被设置为0；
如果你需要确保一个指针不是指向nil（即指向内存中的对象），你可以使用C语言的!=（不等运算符）：

if (somePerson != nil) {
    // somePerson points to an object
}
或者利用if表达式的条件控制语句直接验证：

if (somePerson) {
    // somePerson points to an object
}
如果somePerson变量指向nil，它的逻辑值是0（假 / false）。如果它指向一个地址，那么它的逻辑值就是非0，逻辑判断结果会是真。

类似的，如果你要判断一个变量是否指向nil，你可以使用相等运算符：

if (somePerson == nil) {
    // somePerson does not point to an object
}
或者直接利用逻辑非运算符：

if (!somePerson) {

 // somePerson does not point to an object
      }
封装数据
除了上一章介绍的首发消息，对象还会通过属性封装数据。

本章将讲解Objective-C用语声明对象属性的语法，并将深入剖析这些属性在默认情况下是怎样合成存取方法的。如果一个属性由一个实例变量构成，那么在任何一个初始化方法中，这个变量的值必需的到正确的设置。

如果一个对象需要通过属性保持同另一个对象的联系，那么就要洞悉两个对象之家的关系本质。尽管Objective-C的内存管理在大多数时候都有ARC完成，但明白如何避免诸如强引用循环（会导致内存泄漏）等内存管理问题还是很重要的。本章将讲解一个对象的声明周期，以及如何如果组织对象的关系图。

属性封装着对象的值
为了完成任务，大多数对象都必须记录一些信息。有些对象在设计之初就会被要求储存一个或更多的值，例如NSNumber类会保存一个数字值，一个自定义的XYZPerson类会模拟一个人，储存其姓和名。有些对象在用法方面会比较抽象，例如处理用户交互界面和界面所显示信息之间的关系，但即使是这些对象也需要记录交互界面和模型对象的相关信息。

为可裸露数据声明公共属性
Objective-C属性是类封装相应的信息的一种方法。正如读者在相关章节属性控制在对象数据值的入口中所看的，属性的在接口文件中声明，如：

@interface XYZPerson : NSObject
@property NSString *firstName;
@property NSString *lastName;
@end
在这个例子中，XYZPerson类声明了字符串属性来保存一个人的姓和名。

鉴于面向对象编程中的基本原则之一就是对象应该在接口文件以外隐藏自身的内部工作机制，所以在访问对象的属性时，要使用对象公开的行为，而非直接试图获取内部的数据值。

利用存取方法得到或设置属性值
读者可以通过存取方法设置一个对象的属性：

NSString *firstName = [somePerson firstName];
[somePerson setFirstName:@"Johnny"];
默认情况下，这些存取方法是由编译器自动合成的，所以在接口文件中利用@property关键字声明属性即可，其它不需要做。

合成的存取方法遵循以下命名惯例：

获取属性值的方法（取方法getter method）同属性的名称相同。

设置属性值的方法（存方法setter method）以set开头，其后加上首字母大写的属性名。属性名为firstName的属性的存方法应为setFirstName。

如果你不想不想让属性被通过存方法更改，你可以在声明属性时为其添加一个只读read-only特性：

@property (readonly) NSString *fullName;
特性不仅可以明确表示属性同其他对象的互动关系，还规定了编译器如何合成相应的存取方法。

在上面的例子中，编译器将会合成一个名为fullName的取方法，但没有setFullName存方法。

注：与readonly相对的是readwrite。无需特别声明读写特性，因为它是默认值。
如果如果读者相对存取方法取其他的名字，可以通过特性重新给存取方法命名。如果属性类型是BOOL（YES或NO值），习惯上将取方法的第一个单词改为is。例如，有一个类型为布尔值的名为finished的属性，它的取方法名为isFinished。

再次申明，读者可以为属性添加特性。

@property (getter=isFinished) BOOL finished;
如果需要声明多个特性，可以利用逗号将特性隔开：

@property (readonly, getter=isFinished) BOOL finished;
在上面的例子中，编译器智慧合成名称为isFinished的去方法，而不会合成setFinshed去方法。

注：一般来说，属性的群去放啊放应该遵循KVC，也就是它们会遵循特定的命名惯例。更多信息详见，KVC编程指南。
点语法是调用存取方法的便捷语法
除了明确使用存取方法，Objective-C还提供一种点语法以便访问对象的属性。

点语法允许读者这样访问属性：

NSString *firstName = somePerson.firstName;
somePerson.firstName = @"Johnny";
点语法纯粹是一种存取方法的便捷写法。当读者使用点语法时，程序仍然调用存方法或取方法来读取或改变对象的属性：

读取属性时使用somePerson.firstName就等同于使用[somePerson firstName]

设置属性时使用somePerson.firstName = @"Johnny"就等同于使用[somePerson setFirstName:@"Johnny""]

这意味着通过点语法存取属性同样受到属性特性的影响。如果一个属性被标记为只读，那么当读者视图利用点语法改变它的值的时候，编译器会发出错误警告。

大多数属性都是实例变量
默认情况下，一个可读写的属性都是一个实例变量，编译器在合成属性时会生成这个变量。

实例变量是一个能够在对象声明周期内存在，并保存数值的变量。系统在对象创建之初就会为其实例变量分配内存（通过alloc方法），并在对象被收到dealloc方法时释放这些内存。

除非读者做出额外的声明，被合成的实例变量的名称同属性名相同，但是实例变量名前有一个_下划线前缀。对于一个叫做firstName的属性来说，它的由编译器自动合成的实例变量的名称为_firstName。

尽管，即使对于对象本身来说，访问属性的最佳方式也是通过存取方法，但在类方法的实现中，通过实例变量名称直接访问也是可以的。通过下划线读者可以非常直观的表明这是在访问一个实例变量，而非，例如，本地变量。

- (void)someMethod {
    NSString *myString = @"An interesting string";
    _someString = myString;
}
在上面的例子中，很明显可以看出myString是一个本地变量，_someString是一个实例变量。

总的来说，你应该使用存取方法或点语法来访问属性，即使你是在对象的类的自身的实现中访问的，这时应该搭配self使用：

- (void)someMethod {
    NSString *myString = @"An interesting string";
    self.someString = myString;
  // or
    [self setSomeString:myString];
}
这一规则的例外是出了在编写初始化，取消对象内存分配或自定义存取方法时，本章稍后将讲解。

可以自定义合成的实例变量的名称
如前所述，对于一个可写入的属性来说其默认的实例变量名称是_propertyName。

如果你希望让一个实例变量拥有一个默认值意外的名称，你需要在实现代码中使用以下的语法告诉编译器：

@implementation YourClass
@synthesize propertyName = instanceVariableName;
...
@end
例如：

@synthesize firstName = ivar_firstName;
在上面的例子中，属性名仍然为firstName，而且让然可以通过firstName和setFirstName的存取方法以及点语法访问，但其背后运行机制中的实例变量的名称将为ivar_firstName。

重要：如果读者直接使用@synthesize + 属性名，其后不加任何实例变量名，如：
@synthesize firstName;
那么实例变量将会和属性名同名，没有下划线。在上面的例子中，实例变量名是firstName，没有下划线。

可以定义不通过属性定义实例变量
当需要追踪一个值或其他对象的时候，最好是使用属性。

如果读者的确需要在不通过属性的情况下定义自己的实例变量，那么可以在类的接口文件或实现文件中，在大括号内添加实例变量，如：

@interface SomeClass : NSObject {
    NSString *_myNonPropertyInstanceVariable;
  }
... @end
  @implementation SomeClass {
      NSString *_anotherCustomInstanceVariable;
} ... @end
注：读者同样可以在类扩展中添加实例变量，详见相关章节类扩展扩展了内部实现。
直接通过初始化方法访问实例变量
存方法可能会带来一些副作用。它们可能会出发KVC通知，或没有按照读者所定义的实现完成特定的任务。

在初始化方法中，读者应该总是直接访问实例变量，因为在初始化的过程中，属性准备完毕时，对象的其他部分可能还为初始化完毕。即使在自己编写的类中不自定义任何存取方法，或者能够确保不会产生任何副总用，但是，这个类的子类也很可能覆盖相应的行为，从而产生某些错误。

一个典型的初始化方法看起来类似于：

- (id)init {
    self = [super init];
    if (self) {
        // initialize instance variables here
}
    return self;
}
在一个init方法中，在开始任何自身的初始化工作前，应该调用超类的初始化方法的并将其返回值赋给self。超类的初始化方法有可能未能成功初始化对象，并返回nil，所以读者应该在进行自身的初始化工作之前，总是检查self是否为nil。

通过调用[super init]作为方法的第一行 ，从这个对象的类的根类开始，程序会按顺序依次调用这个类的每一个父类的初始化方法。初始化一个XYZPerson对象的过程如图3-1所示。

正如读者在前面章节所见到的，一个对象可以通过调用init方法，或某些带有初始值的方法来初始化。

以XYZPerson为例，最好能够创建一个能够设置人的姓和名的初始化方法：

- (id)initWithFirstName:(NSString *)aFirstName lastName:(NSString *)aLastName;
方法的实现应该类似于：

 - (id)initWithFirstName:(NSString *)aFirstName lastName:(NSString *)aLastName {
      self = [super init];
      if (self) {
          _firstName = aFirstName;
                  _lastName = aLastName;
      }
      return self;
  }
指定初始化方法是基础的初始化方法
如果一个对象声明了一个或多个初始方法，读者应该决定哪个方法是指定初始化方法。这个方法通常应该拥有最多的可能性的初始化方法（例如拥有最多的参数），并且可以方便的被其他初始化方法调用。读者还应该利用指定初始化方法代入合适的初始值覆盖init方法。

如果XYZPerson类有一个作为生日的属性，那么这个类的指定初始化方法应该是：

- (id)initWithFirstName:(NSString *)aFirstName lastName:(NSString *)aLastName
                                            dateOfBirth:(NSDate *)aDOB;
这个方法将设置相关的实例变量。如果读者仍然希望仅仅为姓和名专门提供一个便捷的初始化方法，那么可以利用指定初始化方法来实现这个方法，如：

- (id)initWithFirstName:(NSString *)aFirstName lastName:(NSString *)aLastName { return [self initWithFirstName:aFirstName lastName:aLastName dateOfBirth:nil];
}
当然还可以实现一个标准的init方法，以提供合适的默认值：

- (id)init {
    return [self initWithFirstName:@"John" lastName:@"Doe" dateOfBirth:nil];
}
如果读者要为一个具有多个init方法的类编写一个子类，那么要么需要覆盖负累的指定初始化方法，替换为你自己的初始化方法，要么额外的初始化方法。不管用哪种方式，在进行自己的初始化工作之前，你都应该首先调用超类的初始化方法（代替[super init]）。

实现自定义的存取方法
属性并不一定总是要有实例变量作为支持。

例如，XYZPerson类可能为一个人的全名定义了一个只读属性：

@property (readonly) NSString *fullName;
相较于每次改变姓和名时都要更新fullName属性，利用自定义的存取方法来设置字符串会是更好的选择：

- (NSString *)fullName {
    return [NSString stringWithFormat:@"%@ %@", self.firstName, self.lastName];
}
这个简单的例子通过格式化字符串和转换说明符（上一章的内容）来构建一个含有姓和名的字符串，中间用空格隔开。

注：尽管这只是一个简单的例子，但需要注意姓名的格式是因地区而异的。
如果读者需要在自定义的存取方法中使用一个实例变量，那么在方法的实现内必须直接访问实例变量。例如，直到属性被请求时再对其进行初始化，这是一种很常见的做法，通常被称为lazy accessor，例如：

￼￼￼￼@property (readonly) NSString *fullName;
￼
- (NSString *)fullName {
    return [NSString stringWithFormat:@"%@ %@", self.firstName, self.lastName];
}
￼￼
- (XYZObject *)someImportantObject {
    if (!_someImportantObject) {
        _someImportantObject = [[XYZObject alloc] init];
    }
    return _someImportantObject;
}
返回返回值之前，方法首先判断_someImportantObject实例实例变量是否为空；如果是，则为其创建一个对象，并赋给它。

注：在至少需要合成一个存取方法的情况下，编译器就会自动合成实例变量。如果对于一个可读写的属性同时手动实现了存取方法，或对于一个只读属性实现了取方法，那么编译器就会认定读者接管了属性的实现，不会自动合成实例变量。
如果你仍然使用一个实例变量，就需要主动要求编译器合成实例变量：

@synthesize property = _property;
属性默认是多线程的
默认情况下，一个Objective-C属性是多线程的：

@interface XYZObject : NSObject
@property NSObject *implicitAtomicObject;          // atomic by default
@property (atomic) NSObject *explicitAtomicObject; // explicitly marked atomic
@end
这意味着编译器合成的存取方法可以被完全检索和设置，即使存取方法被多线程同时调用。

由于多线程的内部实现和并发性是私有的，所以无法将合成的存取方法和读者自定义的存取方法结合在一起。这样的话会受到编译器的警告。例如
为一个多线程的，可读写的属性自定义了一个存方法，与此同时又要求编译器自动合成取方法。

读者可以使用nonatomic单线程特性来明确编译器自动合成的存取方法只单纯设置或返回一个值，如果同一个值同时被多个线程访问，可能会发生意外。
因此，访问单线程特性的属性速度会更快，并且，例如，读者可以将自定义的存方法和编译器合成的取方法结合起来使用，例如：

@interface XYZObject : NSObject
@property (nonatomic) NSObject *nonatomicObject;
@end
@implementation XYZObject
- (NSObject *)nonatomicObject {
      return _nonatomicObject;
  }
  // setter will be synthesized automatically
  @end
注：属性的线程特性并不意味着对象的线程安全性。假设一个XYZPerson对象的姓和名这两个属性在一个线程里发生了改变。如果另一个线程在同一时刻也访问了姓名这一属性，那么多线程的取方法将会返回完整的字符串，但是却不能保证这些值是正确的。如名在改变之前就受到了访问，但姓却在改变之后受到了访问，那么最终将得到一个错误的姓名。这个例非常简单，但线程的安全性在考虑到整个对象网络全局时会变的非常复杂，详情请参考Concurrency Programming Guide。
通过所有权和负责制管理对象图关系图
正如读者已经见到的，Objective-C对象的内存是在堆上分配的，这意味着你必需使用指针来追踪对象的地址。同标量值不同，很难用指针变量的声明周期去判定一个对象的生命周期。相反，只要其他对象还需要一个对象，这个对象就必须活跃在内存当中。

不用去考虑单个对象的声明周期管理问题，读者应该去考虑对象之间的关系。

在XYZPerson对象的例子当中，两个字符串属性firstName和lastName都被XYZPerson的实例对象所拥有，这意味着只要XYZPerson对象存在于内从中，它们就应该存在于内存中。

当一个对象以这种方式依赖于其它对象存在，拥有其他对象，那么就可以说第一个对象对其他对象拥有强引用。在Objective-C中，只要一个对象还拥有来自另一个对象的强引用（即至少被一个对象拥有），那么它就要一直存在下去。XYZPerson对象和两个NSString对象的关系如图3-2所示。

当一个XYZPerson对象在内存中被撤销时，两个字符串对象也随之被撤销，前提是没有其他的强引用指向它们。

为了给例子增加一点难度，请试着思考如图3-3的一个应用的对象关系图。

当用户点击Update键，徽章预览将会跟新响应的信息。

第一次输入个人信息，并点击Update键后，简易的关系图如图3-4所示。

当用户改动了人的名，对象关系图入图3-5所示。

显示徽章的视图仍然对字符串对象@"John"维持着强引用，即使在XYZPerson对象那里字符串firstName已经改变了。这意味着@"John"将会继续停留在内存里，徽章视图用它来进行显示。

一定用户第二次点击Update键，徽章视图会被告知更新它的内部属性来和person对象同步，所以对象关系如图3-6所示。

此时，原来的@"original"对象已经没有强引用指向它了，所以它被移除了内存。

默认情况下，Objective-C中的属性和变量对其他对象的引用都是强引用。这在大多数情况下没有问题，但的确会有形成潜在的强引用循环的可能性。

避免强引用循环
尽管强应用对于对象之间的单向关系来说没有问题，但当程序中有多个互相关联的对象读者要小心。如果一组对象由强引用相互联系，那么即使所有的对象都没有来自外界的强引用，那么这些对象还是会因为彼此之间的强引用而一直存在下去。

一个很明显的关于强在强应用循环的例子是：一个列表视图对象和它的代理对象。为了让一个通用的列表视图对象能够适应多个场合，它就要指派一个代理代替其完成某些任务。也就是说，视图对象将依赖另一个对象决定其显示的内容，用户交互时的反应等。

一个常见的场景是列表视图有指向代理的强引用，而其代理也有指向列表视图的强引用，如图3－7所示。

此时如果其他对象放弃了指向列表视图和其代理的强应用，那么就会出现一个问题，如图3-8所示。

即使此时这两个对象已经没有来自外界的强引用，应该被释放了，但是由于他们内部之间存在互相指向对方的强引用，这两个对象还是不会被释放，而会一直存在于内存之中，这就是强引用循环。

解决这个问题的方法是将其中一个强引用替换为弱引用。一个弱引用不会产生所有权，也不会负责释放被指向的对象，所以不会保留被指向的对象。

如果列表视图对象经过修改，使用弱引用指向它的代理（这也是UITableView和NSTableView实际的解决方法），那么一开始的对象关系如图3-9所示。

当关系图中的其他对象放弃指向列表视图和其代理的强引用后，此时左边的代理对象已经没有指向它的强引用，如图3-10所示。

这意味着代理对象的内存将被撤销，因此指向列表视图对象的强引用也将消失，如图3-11所示。

一旦代理对象的内存被撤销，也就没有了指向视图对象的强引用，所以视图对象也被撤销了。

在属性中声明强弱特性来管理所有关系
默认情况下，对象的属性都是这样声明的：

@property id delegate;
属性默认合成的实例变量会对指向的对象拥有强引用特性。为了声明一个弱引用，需要为属性添加一个特性，如：

@property id delegate;
注：与弱引用特性相对的是强引用特性。没有必要专门声明强引用特性，因为它是默认值。
本地变量（以及不经过属性声明的实例变量）同样在默认情况下对所指向的对象拥有强引用。这意味着以下的代码工作方式会同读者的预期一样：

NSDate *originalDate = self.lastModificationDate;
self.lastModificationDate = [NSDate date];
NSLog(@"Last modification date changed from %@ to %@",
                    originalDate, self.lastModificationDate);
在上面的例子中，本地变量originalDate对一开始的lastModificationDate对象（实例变量）拥有强引用。当名为lastModificationDate的属性改变时，属性就不再对原本的日期对象保持强引用，但是本地变量originalDate仍然对其保持强引用。

注：一个指针变量将再其作用域内对一个对象保持强引用，直到它指针消息，或者指针被赋予另一个对象或者指向nil。
如果读者不想让一个变量拥有强引用，那么可以用__weak关键字加以声明，如：

NSObject * __weak weakVariable;
由于弱引用并不会维持一个对象的激活状态，所以就可能出现在对象还在处于使用状态时，就被释放了。为了避免悬垂指针（dangling pointer）的情况发生（即指针指向了在内存中原本存在，但突然被撤销了的对象），弱引用的指针将在对象被撤销时自动被设置为nil。

这意味着在上述的日期例子中，如果你使用如引用的变量：

NSDate * __weak originalDate = self.lastModificationDate;
self.lastModificationDate = [NSDate date];
原本的orginalDate变量可能会被设置为nil。当self.lastModificationDate会指向新的对象时，那么属性就不会再对以前的日期对象维持强引用。如果没有其他的强引用，原本的日期对象会被撤销，originalDate变量也会指向nil。

弱引用变量可能会早以下的代码中造成误解：

NSObject * __weak someObject = [[NSObject alloc] init];
在上面的代码中，由于新创建的对象没有任何强引用指向它，所以它被创建之初就会被撤销，然后someObject变量将会指向nil。

注：weak相对的是strong。读者无需专门声明__strong，因为它是默认值。
还需要考虑到如果在一个方法的实现中，需要访问若干次弱引用属性，例如：

- (void)someMethod {
    [self.weakProperty doSomething];
    ...
    [self.weakProperty doSomethingElse];
}
在这种情况下，你需要使用本地变量临时指向弱引用属性，以便利用强引用保存对象，确保在方法实现的过程中对象不会突然消失：

- (void)someMethod {
    NSObject *cachedObject = self.weakProperty;
    [cachedObject doSomething];
    ...
    [cachedObject doSomethingElse];
}
在上面的例子中，cacheObject变量对原本的弱引用属性施加了一个强引用，这样对象就不会在cacheObject的作用于中被撤销（当然这个指针也不能被重新赋给另一个对象）。

要记住读者需要确保一个弱引用属性指向的对象在其被使用的时候不会被撤销。如果只是做到以下的代码是不够的：

if (self.someWeakProperty) {
    [someObject doSomethingImportantWith:self.someWeakProperty];
}
因为在一个多线程应用中，属性指向的对象可能在条件判断和方法调用之间的过程中被撤销掉，从而使条件控制失去作用。相应的，所以读者必需给要使用的对象施加一个强引用，例如：

NSObject *cachedObject = self.someWeakProperty;         //1 
if (cachedObject) {                                     //2 
    [someObject doSomethingImportantWith:cachedObject]; //3 
}                                                       //4 
cachedObject = nil;                                     //5
在上面的例子中，第一行创造了一个强引用，意味着确保对象在条件控制和方法调用之家存活。第五行，cachObject被设置为指向nil，因此指向对象的强引用小时。如果原本的对象此时没有任何强引用指向，它将被撤销，而someWeakProperty属性（实例变量）将被设置为nil。

对某些类使用Unsafe Unretained特性
在Cocoa / Cocoa Touch中有一些类还不支持弱引用，这意味着你无法通过声明弱引用的属性或本地变量来追中这些类的对象。这些类包括NSTextView，NSFont和NSColorSpace；要获取完整信息，详见相关文章Transitioning to ARC Realease Notes。

如果这着需要用弱音用指向这些类，那么就必须使用unsafe来引用。对于一个属性来说，这意味着使用unsafe_unretained特性家：

@property (unsafe_unretained) NSObject *unsafeProperty;
对于变量来说，你需要使用__unsafe_unretained来声明变量：

NSObject * __unsafe_unretained unsafeReference;
一个不安全的引用类似类似于一个弱音用（不会维持所指向对象的激活状态），但是若其指向的对象被以外撤销，这个指针又不会被自动设置为nil。这意味着你会获得一个悬垂指针，因为是不安全。向悬垂指针发送消息会引发程序崩溃。

对属性进行复制会产生属性的副本
在有些情况下，一个对象可能会希望对任何设置为其属性的对象，都复制一个只属于它自己的副本。

例如，XYZBadgeView类的接口如图3-4，代码类似于：

@interface XYZBadgeView : NSView
@property NSString *firstName;
@property NSString *lastName;
@end
上面声明了两个NSString属性，都对所指向的对象有着隐形的强引用。

现在思考一下如果有一个代表字符串的对象被创建出来，并被设置为徽章视图的属性，如：

NSMutableString *nameString = [NSMutableString stringWithString:@"John"];
self.badgeView.firstName = nameString;
这是完全合法，因为NSMutableString是NSString的子类。虽然徽章视图认为它是在处理一个NSString对象，但它其实是在处理一个NSMutableString对象。

这意味着字符串可以随时被修改：

[nameString appendString:@"ny"];
这样，尽管对于徽章视图的firstName属性原本设置的值是"John"，由于字符串可变的缘故，现在变成了"Johnny"。

读者可以让徽章视图拥有一份firstName和lastName属性指向的实例变量的拷贝，这样也就相当于在属性被设置之时，字符串对象会被及时保存下来。通过向属性添加copy特性重新声明这两个变量：

@interface XYZBadgeView : NSView
@property (copy) NSString *firstName;
@property (copy) NSString *lastName;
@end
现在视图对象拥有了只属于它自己的两个字符串拷贝。即使可变字符串在城市设置之后随后又被改变了，徽章视图仍然拥有内容为可变字符串初始值的字符串对象。例如：

NSMutableString *nameString = [NSMutableString stringWithString:@"John"];
self.badgeView.firstName = nameString;
[nameString appendString:@"ny"];
此时，徽章视图的firstName属性仍然是未受可变字符串改变影响的“John”字符串。

copy特性下的属性拥有强引用，因为属性必须控制复制生成的对象。

注：若想把带有copy特性的属性指向一个对象，则这个对象壁纸支持NSCopying协议。协议在相关章节协议定义了消息发送的规则。若想了解更多关于NSCopying的信息，参见NSCopying参考或相关文章Advanced Memory Management Programming Guide
如果读者需要直接设置带有copy特性的属性的实例变量，例如在一个初始化方法中，不要忘记对初始的对象进行复制操作：

- (id)initWithSomeOriginalString:(NSString *)aString {
    self = [super init];
    if (self) {
        _instanceVariableForCopyProperty = [aString copy];
    }
    return self;
}
自定义现有类
对象应该被赋予明确的任务，例如容纳特定的信息，显示视图内容或者控制信息流。正如读者所见，类的接口文件定义了其他对象如何与一个类对象互动，从而帮助其完成这些任务。

有时，你可能会发现你希望对现有类进行扩张，增加它的在某些情况下适用的行为。例如，你觉得你的应用经常需要在交互界面上显示一个字符串。相比于专门创建一个能够绘制字符串在屏幕上的对象，倒不如给现有的NSString类添加功能，让其可以在屏幕上绘制出自己。

诸如这样的情况，并不总是需要向现存基本类的源代码里面整合进新的功能。以NSString对象为例，绘图功能对于大多数字符串对象来说都不是必须的，并且，你无法更改框架提供的类的接口和实现。

更进一步讲，你可能也不想创建现存类的子类，因为你希望绘图功能不仅能够在NSString类上实现，也能在它的子类里实现，例如NSMutableString。并且，尽管NSString类能够在OS X / iOS 上使用，但绘图代码在不同平台上是不同的，这就导致在不同平台上你需要创建不同的子类。

万幸的是，Objective-C允许读者在现存类的基础之上通过范畴和类扩展添加自己的方法。

利用范畴想现有类添加方法
如果读者需要想一个现有类添加方法，或许是为了添加某些功能以便能够在读者自己的应用里能够更方便的使用，最简单的方法就是使用范畴。

声明范畴的语法是使用@interface关键字，这同标准的Objective-C类描述一样，但不包括继承的父类。而是应该在原本标明父类的位置写上范畴名，入：

@interface ClassName (CategoryName)

@end
可以给任何一个类声明范畴，即使你不知道这个类的实现源代码（例如为标准的Cocoa / Cocoa Touch 类声明）。任何一个在范畴内声明的方法对于其所在的类来说都是可用的，并且对于这个类的子类来说也都是可用的。在运行时，通过范畴添加的方法和类原本实现的方法没有任何区别。

现在思考一下上一章的XYZPerson类，其有姓和名的属性。如果读者要编写一个记录软件，那么就会需要频繁的现实一个人名列表，如：

Appleseed, John
Doe, Jane
Smith, Bob
Warwick, Kate
不需要每次都编写代码产生合适的姓名字符串，读者可以给XYZPerson类添加一个范畴，如：

#import "XYZPerson.h"
@interface XYZPerson (XYZPersonNameDisplayAdditions)
- (NSString *)lastNameFirstNameString;
@end
在这个例子中，范畴XYZPersonNameDisplayAdditions声明了一个额外的方法，以返回所需的字符串。

范畴通畅被声明在一个淡出的.h文件中，并在一个单独的.m文件中实现。对于XYZPerson类来说，读者可以在一个名为XYZPerson+XYZPersonNameDisplayAdditions.h的文件中来声明。

即使由范畴添加的任何方法对于所有的类对象和子类对象都适用，但是如果读者向在其他源代码文件中使用范畴内声明的方法，还是要将范畴的头文件添加进源代码文件，否则会收到编译器的警告。

范畴的实现代码类似于：

#import "XYZPerson+XYZPersonNameDisplayAdditions.h"

@implementation XYZPerson (XYZPersonNameDisplayAdditions)
  - (NSString *)lastNameFirstNameString {
      return [NSString stringWithFormat:@"%@, %@", self.lastName, self.firstName];
  }
@end
一旦读者声明了范畴，并实现了方法，就可以针对类的任何对象使用范畴内的方法，就好像类本身的方法一样：

#import "XYZPerson+XYZPersonNameDisplayAdditions.h"
@implementation SomeObject
- (void)someMethod {
    XYZPerson *person = [[XYZPerson alloc] initWithFirstName:@"John"
                                                    lastName:@"Doe"];
    XYZShoutingPerson *shoutingPerson =
                        [[XYZShoutingPerson alloc] initWithFirstName:@"Monica"
                                                           lastName:@"Robinson"];
NSLog(@"The two people are %@ and %@",
[person lastNameFirstNameString], [shoutingPerson lastNameFirstNameString]);
} @end
除了向现存类添加方法以外，读者还可以利用范畴来分割复杂类的实现，将多个方法按照使用目的和场合不同安置在多个原文件当中。例如，但一个类含有多种类型的方法时，比如几何图形计算，颜色调控，渐变控制等，非常复杂，此时就可以将一部分实现代码（例如专门用来绘图的那部分代码）利用范畴单独放置在一个文件中。而且，你可以利用范畴区分不同种类的实现代码，例如同个代码的OS X 和ISO版本。

范畴可以声明类方法和实例方法，但很少会声明额外的属性。从语法上来讲在范畴内声明属性是可行的，但声明实例变量是行不通的。这意味着编译器不会为声明在范畴内的属性合成实例变量，也不会合成存取方法。读者可以在范畴内编写自己的存取方法，但是除非属性的值在类的原文件中被声明，读者无法追踪这个属性的值。

唯一能够像现存类添加属性（含有实例变量的属性）的方法是类扩展，详见章节类扩展扩展了内部实现。

注：在Cocoa / Cocoa Touch中，许多基础类都有不止一个类扩展。事实上，本章介绍的字符串自我绘制功能，在OS X 中，已经有NSString的NSStringDrawing范畴实现，包括drawAtPoint:withAttributes: 和 drawInRect:withAttributes:方法。在iOS中，由UIStringDrawing实现，包括drawAtPoint:withFont: 和 drawInRect:withFont:方法。
避免范畴方法名冲突
由于范畴所声明的方法会被添加至现有类，所以读者要小心方法名冲突。

如果范畴内一个方法的名称同类中原油的方法相同，或者说类不止有一个范畴，一个范畴中的一个方法的名称和另一范畴内的一个方法的名称相同（甚至说和一个子类的范畴的方法同名），在运行时哪个方法将会被调用就变的不确定。这在读者针对自定义类使用范畴时发生的几率很小，但如果是针对Cocoa / Cocoa Touch
的类时，就会造成问题。

例如，有一个应用需要用到网页的远程服务，就需要对字符串进行基于Base64的编码。可以针对NSString添加一个范畴，里面定义一个可以返回Base64编码版本的字符串，所以这个方法的名称可以叫做base64EncodedString。

这是如果另有一个框架内定了NSString类的范畴，恰巧还有一个名为base64EncodedString的方法。在运行时，这两个同名方法中，只有一个会被调用，但具体是哪一个并不明确。

另一个问题是如果读者向Cocoa / Cocoa Touch内的类添加了便捷方法，在随后的版本更新中，Apple将这些便捷方法正式加入了框架所提供的类中。以NSSortDescriptor类为例，这个类描述了一个结合内的对象是怎样排列的，一直有一个名为initWithKey:ascending:的初始化方法，但在早期的OS X和ISO版本中，一直没有提供相对应的工厂方法。

根据惯例，工厂方法应该被叫做sortDescriptorWithKey:ascending:；所以此时读者可能选择利用范畴自行为其添加一个工厂方法。这在早期的OS X和iOS版本中没有问题，但是随着OS Xversion 10.6 and iOS 4.0的发布，sortDescriptorWithKey:ascending:方法被添加到了NSSortDescriptor类的源代码中，这意味着当你在这些平台运行程序时，会发生冲突。

为了避免这一现象发生，最好的解决方法是为范畴内的方法名添加前缀，就好像给自定义的类添加前缀一样。读者可以选择同自定义一样的三个字母的前缀，但字母要小写，以便遵循方法命名的惯例，然后在前缀和正式的方法名之间添加一个下划线。以NSSortDescriptor为例，自定义的范畴类似于：

@interface NSSortDescriptor (XYZAdditions)
+ (id)xyz_sortDescriptorWithKey:(NSString *)key ascending:(BOOL)ascending;
@end
这样就可以保证方法在运行时能够被正确调用。命名冲突的可能性被消除了：

NSSortDescriptor *descriptor =
[NSSortDescriptor xyz_sortDescriptorWithKey:@"name" ascending:YES];
类扩展扩展了内部实现
类扩展同范畴的作用类似，但只能用在编译时已知源代码的类上（类扩展和类将被一同编译）。由类扩展声明的方法将在类的@implementation部分被实现，所以你无法为框架类声明类扩展，诸如Cocoa / Cocoa Touch的NSString类。

声明类扩展的语法同声明范畴的语法相似，类似于：

@interface ClassName ()
@end
由于括号内总是为空，所以类扩展又被称为匿名范畴.

同一般范畴不同，类扩展可以向类添加属性和实例变量。如果你在类扩展中声明了一个属性，如：

@interface XYZPerson ()
@property NSObject *extraProperty;
@end
编译器将会，在类的实现部分里，自动合成相应的存取方法以及实例变量。

如果读者向类扩展添加方法，则这些方法一定要在类的实现部分进行实现。

可以使用类扩展添加自定义的实例变量。这些实例变量要声明在类扩展的大括号里：

@interface XYZPerson () {
    id _someCustomInstanceVariable;
} ... @end
使用类扩展来隐藏私有信息
类的基础接口是用来定义其他对象同类对象的互动方式的。换言之，它是类的公共接口。

类扩展通常被用来向类的公共接口添加额外的私有方法和属性，这些方法和属性仅供类的实现使用。例如，通常会在公共接口中将一个属性定义为只读，而在实现代码的上方的类扩展中将其定义为读写。这是为了让内部方法可以直接修改属性值。

以XYZPerson类为例，可以向其添加一个名为uniqueIdentifier的属性，用来追踪像社会保障号这样的信息。

在现实世界中，给一个人分配一个社会保障好需要登记大量的档案，所以XYZPerson类的公共接口就将其特定定义为只读，并且还要提供某个方法来为对象分配识别符，如：

@interface XYZPerson : NSObject
  ...
@property (readonly) NSString *uniqueIdentifier;

- (void)assignUniqueIdentifier;
@end
这就意味着不能直接设置uniqueIdentifier的值。如果一个人还没有识别符，就需要请求这个方法赋给其一个。

为了能够让XYZPerson类在内部修改这个属性，就可以在类扩展中再次声明这个属性（类扩展在实现代码上部）：

@interface XYZPerson ()
@property (readwrite) NSString *uniqueIdentifier;
@end
@implementation XYZPerson
...
@end
注：可以不用特意声明可读写属性，因为它是默认值。但为了强调期间，读者可以将它明确的写出。
这意味着编译器将会自动合成存方法，所以XYZPerson类实现文件内的任何一个方法都可以利用存方法或点语法来直接设置这个属性的值。

通过声明在源代码文件内部的类扩展，信息只在XYZPerson类内部流通，保持了私有。如果外部的其他类型的对象试图直接设置属性值，编译器就会报错。

注：通过添加上面的类扩展，重新将属性uniqueIdentifier声明为可读写属性，这样，在运行时，一个名为setUniqueIdentifier的存方法对于所有的XYZPerson类对象就会处于可用状态，不管其它源代码文件是否知晓这个类扩展的存在（即是否将含有类扩展的.m文件导入了其它源代码文件）。

如果在其它源代码文件中，有代码试图调用私有方法或直接设置只读属性，编译器会发出警告。有办法避免编译器的警告，并且切可以利用运行时的动态特性来调用这些私有方法，例如使用NSObject类定义的performSelector方法。但是，在设计类的结构之初，读者应该避免这种情况发生；总的来说，类的基础接口所定义的内容应该总是被遵守。

如果读者打算让私有化方法或属性可以被其他类所用，例如同一个框架中其它相关的类，可以在一个单独的头文件中声明类扩展，，并在需要使用这些方法和属性的源代码文件中导入。对于一个类来说，很少会同时使用两个头文件，例如一个XYZPerson.h和一个XYZPersonPrivate。当你放出可用的框架头文件时，只需要放出XYZPerson.h即可。
自定义现有类的其它方式
范畴和类扩展使得为现有类添加行为变的简单，但是有些这并不是最佳的方式。

面向对象编程的基本要求之一是编写可重复使用的代码，这意味着类应该在各种环境下都能够重复使用。如果读者要编写一个视图类来描述一个能够在屏幕上显示显示信息的对象，就应该思考一下这个类是否能够满足多个场合的需要。

与其绞尽脑汁去思考代码的布局和内容，不如利用继承，将这些问题交给子类，用覆盖方法的方式来为特定的问题专门编写代码。不过这样虽说让类的使用变的简单，但是读者可能需要每次都相应的子类。

另一个解决方法是使用代理。任何会对类的适用性产生限制的功能都交由代理在运行时实现。一个常见的例子是标准的列表视图类（NSTableView for OS X and UITableView for iOS）。为了让一个通用的列表视图（一个可以利用行和列显示信息的对象）具备可用性，可以让视图对象的代理来控制在运行时它所显示的内容。代理机制将在下一张详细介绍使用代理。

利用Objective-C运行时的特性
Objective-C通过其运行时系统来实现它的动态特性。

许多决议，例如在发送消息时哪个方法会被调用，并不是在编译时决定的，而是在应用运行的过程中决定的。Objective-C不仅仅只是一个可编译至机器语言的编程语言。相反，它需要一个运行时系统来执行自己的代码。

可以直接同运行时系统互动，例如想一个对象加入关联引用associative reference。同类扩展不同，关联引用并不影响类原本的声明和扩展，这意味着你可以在不知晓源代码的框架类上使用它们。

一个关联引用将一个对象同另一个联系起来，它们之间的关系同属性和实例变量的关系类似。要了解更多信息，参见关联引用。学习更多关于Objective-C运行时的内容，参加相关文章Objective-C Runtime Programming Guide。

使用协议
在真实的世界里，政府部门在办事时通畅会遵循一系列非常严格的程序。以执法部门为例，正调查或收集证据时就必须遵守“章程“。

在面相对象编程的世界里，定义一组一个对象在某个特定的情况下能够执行的行为是非常重要的。例如，一个列表视图可以同一个数据元对象沟通，这样它就可以得到要显示的内容。这意味着数据源米需能够回应一组由视图对象发送的特定的消息。

数据源可以是任何类的实例对象，例如视图控制器类（NSViewController的子类 on OS X or UIViewController的子类 on iOS），或者一个继承自NSObject类的专门作为数据源的类。为了让列表视图对象知道一个对象是否适合作为数据源，这个对象就必须能够实现必须的方法。

Objective-C允许读者自定义协议，其中声明的方法被指定用于一个特定情况。本章讲讲解定义正式语法的语法，以及怎样在一个类的接口中让其遵守协议，这意味着这个类必需实现协议中的必要方法。

协议定义了消息发送的规则
类接口中声明的方法和属性同这个类相关。而一个协议，相反，是用来声明一组独立于任何类的方法和属性。

定义个一个协议的基本语法类似于：

@protocol ProtocolName
// list of methods and properties
@end
协议可以包括实例方法，类方法以及属性的声明。

例如，想象一个自定义的视图子类，用来显示一个饼状图，如图5-1所示。

为了尽可能的重复使用视图，所有关于显示信息内容的决议都被交由另一个对象负责，即数据源。这意味着同一个视图类的多个对象可以显示完全不同的内容，因为他们的数据源各不相同。

显示饼状图所需的最基本信息包括每个部分的数字，每个部分的相对大小，以及各自的标题。因此，饼状图的数据源协议，应该类似于：

@protocol XYZPieChartViewDataSource
- (NSUInteger)numberOfSegments;
- (CGFloat)sizeOfSegmentAtIndex:(NSUInteger)segmentIndex;
- (NSString *)titleForSegmentAtIndex:(NSUInteger)segmentIndex;
@end
注：上面的协议中使用NSUInteger来表示整数标量的值。这个类型将在下一章做进一步的讨论。
饼状图的视图类的接口需要一个属性了追踪数据源对象。这个对象可以属于任意类，所以基本的属性类型应该是id。关于这个对象唯一已知的是它遵守相关的协议。

声明数据源属性的语法类似于：

@interface XYZPieChartView : UIView
@property (weak) id <XYZPieChartViewDataSource> dataSource;
...
@end
Objective-C用尖括号来表示所遵守的协议。这个例子中声明对一个指向通用类型对象的指针声明了一个弱引用，并且其遵守XYZPieChartViewDataSource协议。

注：出于对象关系管理的需要，指向代理和数据源的属性通畅都被声明为弱引用。详见章节避免强引用循环。
通过声明属性时指名其所遵守的协议，如果读者视图将属性指向一个不遵守协议的对象，就会受到编译器的警告，即使基本的属性类型为通用。属性所指向的对象是UIViewController类还是NSObject类的实例对象并不重要。只要其遵守协议即可，这样饼状图视图就知道它可以请求需要显示的信息。

协议可以有可选方法


