## zExpression 句法编译器+解释器，脚本引擎内核


## 技术体系解释：
- 在编译原理的技术体系中，凡是处理文本化的代码前，都需要做一次预处理，其中我们常说的语法，语法糖，都是一种预处理程序
- 词法：词法是对文本关键字，数字，符号，进行分类整理，最后形成词法树，并且严格遵循顺序化处理原则
- 申明：在预处理代码中，申明部分，叫做申明树，申明树又依赖于词法顺序预处理，因为对词法预处理是一种简化手段
- 句法：在经过了申明预处理以后，是对代码表达式的单行逻辑操作进行处理，这一步叫句法，取为zExpression句法编译器是我从曾经撰写的编译器中特意剥离出来的解决方案，它可以独立出来分发和使用，可以实用数字化预处理，图形图像，科学计算等等领域，也可以作为学习提高自己的手段



## 核心思路
实现zExpression采用的是对等复杂化原则，面向解决编译器问题而编写，复杂度相比于常规程序会高许多，因为解决了最终问题，代码在命名和堆结构上也看不出漏洞，所以它是成熟句法解释器方案

## zExpression特点
- 完整的单步原子化操作
- 完整的符号优先级后处理
- 能预处理字面错误，并反馈错误发生在哪
- 能识别浮点和整数的自然数写法
- 支持函数调用
- 支持自定义脚本语法
- 逆波兰2.0符号优先级处理
- 支持安卓和苹果各型号手机
- 完整的功能Demo，完整性能和解析准确性评估框架
- 在编译以后，能形成原子化op代码，可以通过stream高速载入并运行，不限制cpu类型
- OP代码框架可以轻松译码成ARMv7 ARMx64 x64 x86等平台的机器码


## 更新日志

2018-4-12

修复内核中的内存越界bug：该bug的症状为无故提示内存无法访问，通过正常debug很难排除，这是是内存越界时所造成的bug


2018-3-1

在TPascalString内核中新增模糊字符串对比函数（SmithWaterman），优化与测试完成

该算法属于生物基因工程学科 Smith-Waterman的维基百科地址 https://en.wikipedia.org/wiki/Smith%E2%80%93Waterman_algorithm

2018-2-28

修复c转义字符buf，感谢阿木qq345148965

将charPos的参数命名更改成了cOffset，并且加入const修饰符


2018-2-26

修复使用Release模式无法编译问题

修复zExpression的切割分段不正确问题

小幅提升字符探头的切割性能(splitToken,splitChar)

因为底层重写了一个原子锁，在很多record申明前加入了packed修饰符


2018-2-25

新增自定义表达式符号支持

新增自定义表达式符号的演示


2018-2-25

修复嵌套函数参数不能正确展开接口的问题

修复解析引擎的数字探头不能识别16进制自然数和函数问题

新增一个赋值的demo范例，包含变量申明，静态复用，动态复用，总共三部曲，请在范例演示中自行研究

修复字符串和数字匹配联合的问题

支持c代码风格0x16进制语法


2018-2-6

重写了一次解析器内核，支持函数调用，从现在起，zExpression会不断更新


----------


**首发代码创建 于2004年** 

最后更新于2014年 可以兼容fpc编译器和最新的delphi xe，包括ios,osx,android,linux,win32


----------

## 捐赠


**如果你支持zExpression开发，请向作者捐款，希望捐赠后能留下真实姓名和联系方式，开发建议请发至作者邮箱** [600585@qq.com](mailto:600585@qq.com "600585@qq.com")

![](alipay.jpg)

请不要直接联系作者

使用zExpression有疑问请加互助qq群490269542，

