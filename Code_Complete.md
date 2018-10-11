
## Chapter 1 ##
**软件开发过程中的活动**
- 定义问题 problem definition
- 需求分析 requirement development
- 规划构建 construction planning
- 软件架构 software architecture
- 详细设计 detailed design
- 编码与调试 coding and debugging
- 单元测试 unit testing
- 集成测试 integration testing
- 集成 integration
- 系统测试 system testing
- 保障维护 corrective maintenance

**构建的具体任务**
- 验证有关的基础工作已经完成；
- 确定任何测试所写的代码；
- 设计并编写类class和子程序routine；
- 创建并命名变量variable和具名常量named constant；
- 选择控制结构control structure， 组织语句块；
- 对你的代码进行单元测试和集成测试，并排除其中的错误；
- 评审开发团队其他成员的底层设计和代码，并让他们评审你的工作；
- 润饰代码，执行进行代码的格式化和注释；
- 将单独开发的多个软件组件集成为一体；
- 调整代码tuning code，让它更快，更省资源


## Chapter 2 ##
**软件开发常用的隐喻**
- 写作代码
- 培植系统
- 系统生长
- 建造软件

## Chapter 3 ##
软件开发的前期工作的中心目标就是降低风险，倾向于集中改进需求分析和项目规划

架构师吃掉需求，设计师吃掉架构，程序员则消化设计。

如果你正在为某个高度迭代的项目做计划，那么在开始构建活动之前，你需要针对将要构造的每一片段，先弄清哪些是最关键的需求和架构要素。

发现错误的时间要尽可能接近引入该错误的时间。

计划好预先对大约80%的需求做出详细的说明，并给稍后在进行详细说明的额外需求分配一定的时间。然后在项目进行过程中，实施系统化的变更控制措施-只接受那些最有价值的新需求。另一种替代方案是预先只对最重要的20%的需求做出详细的说明，并且计划以小幅增量开发软件的剩余部分，随着项目的进行，对额外的需求和设计做出详细说明。

**适合序列化开发的场景**
- 需求相当稳定
- 设计直截了当，并理解透彻
- 开发团队对于该应用领域非常熟悉
- 项目的风险很小
- 长期可预测性很重要
- 后期改变需求，设计和代码的代价较昂贵

**适合迭代开发的场景**
- 需求并没有被理解透彻
- 设计很复杂
- 开发团队不熟悉该应用领域
- 项目包含许多风险
- 长期可预测性不重要
- 后期改变需求，设计和编码的代价较低

**问题定义 problem definition**： 对这个系统要解决的问题做出清楚的陈述。问题定义在具体的需求分析工作之前，而需求分析是对所定义的问题的深入调查

**需求分析 requirement development**: 详细描述软件系统该做什么。

**在构建期间处理需求变更**
- 使用需求核对表来评估需求的质量
- 确保每一个人都知道需求变更的代价
- 建立一套变更控制程序
- 使用能适应变更的开发方法
- 放弃这个项目
- 注意项目的商业案例

**软件架构 software architecture**： 软件设计的高层部分，用于支撑更细节的设计的框架。

### 架构的典型组成部分 ###
- 程序组织 Programma Organization： 系统架构首先要以概括的形式对有关系统做一个综述。
	- 在架构中，发现对那些曾经考虑够的最终组织结构的替代方案的记叙，找到之所以选用最终的组织结构，放弃其他选择的理由。
	- 架构应该定义程序的主要构造块building blocks。每个构造块可以是单个类，也可以是一组协同工作的类和子程序，共同实现一种高层功能。每条在需求中的功能特性都应该被至少一个构造块覆盖。如果多个构造块实现同一个功能，他们应该是相互配合而不是互相冲突。
	- 应该明确定义各个构造块的责任。每个构造块应该负责某一个区域的事情，并且对其他构造块负责的区域知道的越少越好，将设计的信息局限于各个构造块之内。
	- 应明确定义每个构造块的通信规则。对于每个构造块，应描述它能直接使用哪些构造块，能间接使用哪些构造块，不能使用哪些构造块。
- 主要的类 Major Classes： 详细定义所用的主要的类，每个主要的类的责任，以及该类如何与其他类交互。还应该包括对类的继承体系，状态转换，对象持久化等的描述。如果系统够大，还应该描述如何将这些类组织成一个个子系统。但无须说明系统中的每一个类，可以遵守80/20原则：只对那些构成系统80%的行为的20%的类进行详细说明。
- 数据设计 Data Design：描述所使用到的主要文件和数据表的设计。数据通常只应该有一个子系统或一个类直接访问，例外的情况是通过访问器类(access class)或访问器子程序(access routine)，以受控切抽象的形式来访问数据。架构应该详细定义所用数据库的高层组织结构和内容，指出与其他访问同一数据的程序的可能交互方式，会创建那些数据视图(view)，等等 。
- 业务规则 Business Rules：详细描述所依赖的特定的业务规则以及这些规则对系统设计的影响。
- 用户界面设计 User Interface Design：用户界面常常在需求阶段进行详细说明，如果没哟，则应该在软件架构中进行详细说明。应该详细定义Web页面格式，GUI，命令行接口等元素。
- 资源管理 Resource Management：描述一份管理稀缺资源的计划，包括数据库连接，线程，句柄(handle)等。架构应该估算在正常情况和极端情况下的资源使用量。
- 安全性 Security：描述实现设计层面和代码层面的安全性的方法，建立威胁模型。制定编码规范时应考虑处理缓冲区的方法，处理不信任数据（用户输入的数据，cookies，配置数据文件和其他外部接口输入的数据）的规则，加密，错误消息的细致程度，保护内存中的秘密数据以及其他事项。
- 性能 Performance：详细定义性能目标。可以包括资源的使用（此时应详细定义资源如速度，内存，成本之间的优先顺序）。架构应该提供估计的数据，并解释为什么架构师相信能达到性能目标。如果部分存在无法达到性能目标的风险，架构也应该指出来。如果为了满足性能目标，需要在某些部分使用特定的算法或数据类型，架构也应该说明清楚。架构中也可以包括各个类和各个对象的空间和时间预算。
- 可伸缩性 Scalability：系统增长以满足未来需求的能力。描述系统如何应对用户数量，服务器数量，网络节点数量，数据库记录数，数据库记录的长度，交易量等的增长。如果预计系统不会增长，而且可伸缩性不是问题，那么架构中应该明确列出这一假设。
- 互用性 Interoperability：描述如何与其他软件或硬件共享数据或资源。
- 国际化/本地化 Internationalization/Localization：架构中应该描述已经考虑过的典型的字符串问题和字符集问题，如何无须更改代码就能维护这些字符串，如何将这些字符串翻译为另一种语言而又尽量不影响代码和用户界面。
- 输入/输出 Input/Output：详细定义读取策略（reading scheme）是先做（look-ahead），后座（look-behind）还是及时做（just-in-time）。而且应该描述在哪一层（字段，记录，流，文件）检测I/O错误。
- 错误处理 Error Handling：在架构中应该清楚说明一种一致处理错误的策略。以下是需要考虑的问题：
	- 错误处理是纠正还是仅仅进行检测。纠正可以让程序尝试从错误中恢复过来；检测可以让程序继续运行或退出。但都应该通知用户检测到错误。
	- 错误检测是主动的还是被动的。前者减少隐患，后者清除混乱。
	- 程序如何传播错误。程序一旦检测到错误，它可以立刻丢弃引发该错误的数据，也可以进入错误处理状态，或者等到所有处理完成，再通知用户在某个地方发现了错误。
	- 错误消息的处理如何约定。
	- 如何处理异常。架构应该规定代码在何时能够抛出异常，在什么地方捕获异常，如何记录（log）这些异常，以及如何在文档中描述异常等等。
	- 程序中在什么层次上处理错误。可以在发现错误的地方处理，可以把错误传递到专门处理错误的类进行处理，或者沿着方法调用链向上传递错误。
	- 每个类在验证其输入数据的有效性方面需要付何种责任。是每个类自己负责验证自己的数据的有效性，还是有一组类专门负责验证整个系统的数据的有效性。
	- 是希望用运行环境中內建的错误处理机制，还是想建立自己的一套机制。
- 容错性 Fault Tolerance：详细定义所期望的容错种类。
- 架构的可行性 Architectural Feasibility：架构应该论证系统的技术可行性。
- 过度工程 Overengineering：健壮性（robustness）是指系统在检测到错误继续运行的能力。架构应该清楚指出程序员应该遵守的工程的尺度。
- 买还是造 Buy-vs.-Build Decisions
- 复用的决策 Reuse Decisions：架构应该说明如何对复用的软件进行加工，使之符合其他架构目标。
- 变更策略 Change Strategy：架构应该清楚地描述处理变更的策略。列出已经考虑过的可能会有所增强的功能，并说明最有可能增强的功能同样也是最容易实现的。架构应该指出延迟提交（delay commitment）所用的策略
- 架构的总体质量 General Architectural Quality：优秀的架构规格书的特点在于，讨论了系统的类，讨论了每个类背后的隐藏信息，讨论了采纳或排斥所有可能的设计替代方案的根本理由。加固的目标应该清楚地表述。架构应该描述所有主要决策的动机。优秀的软件架构很大程度上是与机器和编程语言无关的。架构应该在对系统欠描述（underspecifying）和过度描述（overspecifying）之间找到平衡点。架构应该明确地指出有风险的区域。架构应该包含多个视角/视图。

### 花费在前期准备上的时间长度 ###
一般来说，一个运作良好的项目会在需求，架构以及其他前期计划方面投入10%-20%的工作量和20%-30%的时间。 

## Chapter 4 关键的构建决策 ##

### 常见编程语言 ###
Cobol(COmmon Business-Oriented Language):面向商业的通用语言
Fortran(FORmular TRANslation):公式翻译
Perl(Practical Extraction and Report Language):实用摘要及报告语言
PHP(PHP:Hypertext Processor)超文本处理器
SQL(Structured Query Language)结构化查询语言
Visual Basic(Beginner's All-purpose Symbolic Instruction Code):初学者通用符号指令码

###  编程约定 ###
在构建开始之前，应该讲清楚使用的编程约定。大多数重要的编程原则并不依赖特定的语音，而依赖于你是用的语言的方式。

## Chapter 5 软件构建中的而设计 ##

### 设计中的挑战 ###
险恶的（wicked）问题是那种只有通过解决或部分解决才能明确的问题。
设计的要点，一部分是在床罩可能发生的事情，另一部分是在限制可能发生的事情。
### 关键的设计概念 ###
本质的（essential）属性是一件事情必须具备，如果不具备就不再是该事物的属性。如汽车必须有引擎，车门；
偶然的（accidental）属性是一件事物碰巧拥有的属性，有没有这些属性并不影响这件食物本身。如汽车可以有v8发动机，v4发动机，双门或者四门等。
在软件架构的层次上，可以通过把整个系统分解成多个子系统来降低问题的复杂度。

**管理复杂度的方法：**

- 把任何人在同一时间需要处理的本质复杂度的量降到最少；
- 不要让偶然性的复杂度无谓地快速增长。

软件开发中的任何技术目标都不如管理复杂度重要。

**理想的设计特征**

- 最小的复杂度 minimal complexity
- 易于维护 ease of maintenance
- 松散耦合 loose coupling 让系统的各个组成部分之间关联最小
- 可扩展性 extensibility 可以增强系统的功能而无须破坏其底层结构
- 可重用性 reusability 系统的组成部分可以在其他的系统中重复使用
- 高扇入 high fan-in 让大量的类使用某个给定的类
- 低扇入 low fan-out 一个类少量或适中地使用其他的类。
- 可移植性 portability 系统可以很方便地移植到其他环境
- 精简性 leanness 系统中没有多余的部分
- 层次性 stratification 保持系统各个分阶层的层次性，能在任意的层面上观察系统，并得到某种具有一致性的看法。
- 标准技术 standard techniques  

#### 一个程序中的设计层次 ####
1. **系统**
2. **系统被组织为子系统**
	- 确定如何把程序分为主要的子系统，并定义清楚允许的各子系统如何使用其他子系统。
	- 应该通过限制子系统之间的通信来让每个子系统更有存在意义。实际设计时可以先对子系统之间的通信加以限制，等日后需要的时候再放松。
	- 尽量简化子系统之间的交互关系。
		- 最简单的交互关系是让一个子系统去调用另一个子系统中的子程序；
		- 稍微复杂的是在一个子系统中去包含另一个子系统中的类
		- 最复杂的是让一个子系统中的类继承另一个子系统中的类
	- 一条很好的设计原则是程序中不应该有任何环形关系，即A类使用了B类，B类又使用了C类，C类又使用了A类。
	- 常见的子系统：
		- 业务规则：那些在计算机系统中编入的法律，规则，政策以及过程。
		- 用户界面：应创建一个子系统，把用户界面组件和其他部分隔离开，以便使用户界面的演化不会破坏程序的其余部分。
		- 数据库访问：把数据库进行访问的实现细节隐藏起来，让程序的绝大部分都可以不必关心处理底层结构的繁琐细节，并能像在业务层次一样处理数据。
		- 对系统的依赖性：把对操作系统的依赖因素轨道一个子系统里，就如同把对阴间的依赖因素封装起来一样。
3. **子系统被分解为类**
	当定义子系统中的类时，也就同事定义了这些类与系统的其他部分打交道的细节。把所有的子系统进行适当的分解，并确保分解出的细节都能恰到好处地用单个类实现。

4. 类被分解为子程序
	细化出类的私有子程序
	
5. 子程序内部设计
	为每个子程序布置详细的功能。包括编写伪代码，选择算法，组织子程序内部的代码块，以及用编程语言编写代码。
	
### 设计构造块：启发式方法 ###
使用对象设计的步骤：
	- 辨识对象及其属性
	- 确定可以对每个对象进行的操作
	- 确定各个对象能对其他对象进行的操作，最常见的关系是包含和继承
	- 确定对象的哪些部分对其他对象可见，即哪些部分是可以公开的，哪些部分是私有的
	- 定义每个对象的公开接口

#### 信息隐藏 ####
- 隐藏复杂度
- 隐藏变化源

信息隐藏的障碍：
- 信息过度分散
- 循环依赖
- 把类内数据误以为全局数据
- 过度在意性能损耗

在设计的所有层面上，都可以通过询问该隐藏些什么来促成好的设计决策。

#### 找出容易变化的区域 ####
如何找出易变化的区域
1. 找出看起来容易变化的项目
2. 把容易变化的项目分离出来
3. 把看起来容易变化的项目分离出来。尽量设计好类之间的接口，使其对潜在的变化不敏感。

容易变化的区域：  
- 业务规则
- 对硬件的依赖性
- 输入和输出
- 非标准的语言特性。如果使用了编程语言非标准扩展，应该把这样的扩展单独隐藏在一个类里；如果使用了并非在所有环境下都能使用的子程序库，应该把这样的子程序库都隐藏在一个接口后面。
- 困难的设计区域和构建区域
- 状态变量：状态变量用于表示程序的状态。
	- 使用枚举类型而不是布尔变量作为状态变量
	- 使用访问器子程序取代对状态变量的直接检查
- 数据量的限制

预料不同程度的变化，让这些变化的影响或范围与发生该变化的可能性成反比。如果一种变化很可能发生，那么要确保系统能够很容易对他做出响应。只有那些极不可能发生的变化才能导致系统中多于一个类发生明显的变化。应该把精力放在特别容易发生而又容易做出计划的变化上，而不是那些不太可能发生而且又很难做出计划的变化上。

找出容易发生变化区域的一个好方法：首先找出程序中可能对用户有用的最小子集。这一子集构成了系统的核心，不容易发生改变。接下来，用最小的步伐扩充这个系统。这些潜在的改进区域就构成了系统中的潜在变化。按照信息隐藏的原则来设计这些区域。

#### 保持松散耦合 ####
尽量使创建的模块不依赖或者很少依赖其他模块。

**耦合标准**
- 规模：模块之间的连接数
- 可见性：两个模块之间的连接的显著程度
- 灵活性：模块之间的连接是否容易改动。一个模块越容易被其他模块所调用，他们之间的耦合关系就越松散

创建系统架构时，按照尽可能缩减相互连接的准则来分解程序。

**耦合种类**
- 简单数据参数耦合 simple-data-parameter coupling：当两个模块之间通过参数来传递数据，并且所有的数据都是简单数据类型primitive data type。这种耦合关系是正常的，可以接受的。
- 简单对象耦合 simple-object coupling： 一个模块实例化一个对象。
- 对象参数耦合 object-parameter coupling： 如果object1要求object2传统给他一个object3，那么这两个模块之间就是对象参数耦合 。
- 语义上的耦合：一个模块不仅使用了另一个模块的语法元素 syntactic element，还是用了有关那个模块内部工作细节的语义知识 semantic knowledge。

#### 设计启发的总结 ####
- 寻找现实世界的对象
- 形成一致的抽象
- 封装实现细节
- 在可能的情况下继承
- 信息隐藏
- 找出容易改变的区域
- 保持松散耦合
- 探寻通用的设计模式

其他启发式方法
- 高内聚性
- 构造分层结构
- 严格描述类契约
- 分配职责
- 为测试而设计
- 避免失误
- 有意思地选择绑定时间
- 创建中央控制点
- 考虑使用蛮力
- 画图
- 保持设计模块化

### 设计实践 ###
自上而下策略和自下而上策略的区别在于，前者是一种分解 decomposition 策略， 后者是一种合成 composition 策略。前者从一般性的问题出发，把问题分解成可控的部分。后者从可控的部分出发，构造一个通用的方案

#### 建立试验性原型 prototyping ####
写出用于回答特定问题的，量最少且能够随时扔掉的代码。如果开发人员没有把握住用最少代码回答提问的原则，或者当有关设计的问题不够特殊的时候，原型都会失效。开发人员必须把原型代码当做是可以抛弃的代码。可以用与产品代码不同的技术开发原型，或者在原型中的类或包前面加上prototype。

#### 做多少设计才足够 ####
最大设计问题往往来自于认为是很简单，而没有做出任何设计的区域，而不是那些认为是很困难啊并在其中做出了不好的设计的区域

#### 记录设计成果 ####
- 把设计文档插入到代码中，在代码注释中写明关键的设计决策。
- 用Wiki来记录设计讨论和决策。
- 写总结邮件
- 使用数码相机
- 保留设计挂图
- 使用CRC（Class, Responsibility, Cooperator）卡片
- 在适当的细节层创建UML图


## Chapter 6 ##
高效开发的关键在于，当开发程序任一部分的代码时，都能安全第一忽视程序中尽可能多的其余部分

### 抽象数据类型 ADTs ###
**抽象数据类型 Abstract Data Types**：一些数据以及对这些数据所进行的操作的集合。这里的数据不是编程中常说的数据，而是现实世界中各种实体，以及由此抽象出来的更上层的数据概念。

使用ADT的益处：
- 可以隐藏实现细节
- 改动不会影响到整个程序
- 让接口能提供更多的信息
- 更容易提高性能
- 让程序的正确性更显而易见
- 程序更具有自我说明性
- 无须在程序内到处传递数据
- 可以像在现实世界中那样操作实体，而不用在底层实现上操作它

如何使用ADT：
- 把常见的底层数据类型创建为ADT并使用这些ADT，而不再使用底层数据类型。也就是说要尽可能选择最高的抽象层次。
- 把像文件这样的常用对象当成ADT。在某一层次用ADT来提供数据结构的操作，也可以在这个抽象层次上在创建一个针对现实世界中的问题的抽象层次。
- 简单的食物也可当做ADT
- 不要让ADT依赖于存储介质，尽量让类和访问器子程序的名字与存储数据的方式无关，并只提及抽象数据类型本身。

### 良好的类接口 ###
高质量的类最重要的就是创建一个好的接口，包括创建一个可以通过接口来展现的合理的抽象，并确保细节被隐藏在抽象的背后。

类的接口应能提供一组明显相关的子程序。

创建类的抽象接口的建议：
- 类的接口应该能够展现一致的抽象层次。每一个类应该实现一个ADT，并仅能实现这个ADT。不要为了编码的便利性而使抽象变得混乱复杂。
- 一定要理解类所实现的抽象是什么。根据抽象的目的控制抽象时的复杂度。
- 考虑提供成对的服务。
- 把不相关的信息转移到其他类中。
- 尽可能让接口可编程，而不是表达语义。每个接口都都由一个可编程 programmatic 部分和一个语义 semantic 部分组成。可编程部分有接口中的数据类型和其他属性构成，编译器能强制性地要求他们。而予以部分则由本接口将会被怎样使用的假定组成，无法通过编译器来强制实施。语义接口应该通过注释说明，但尽可能让接口不依赖于这些说明。一个接口中任何无法通过编译器强制实施的部分，就是一个可能被误用的部分。要尽量把语义接口的元素转换为编程接口的元素。比如用断言 Assert 或其他技术。另一种理解方式是把语义部分作为接口的使用条件 pre-condition 和 post-condition。
- 谨防在修改是破坏接口的抽象
- 不要添加与接口抽象不一致的公用成员
- 同时考虑抽象性和内聚性

### 良好的封装 ###
- 尽可能地限制类和成员的可访问性
- 不要公开暴露成员数据
- 避免把私用的的实现细节放入到类的接口中
- 不要对类的使用者做出任何假设。减少对外部pre-condition的依赖，内部检查pre-condition
- 避免使用友元类
- 不要因为一个子程序里仅使用公用子程序就把它归入公共接口。
- 让阅读代码比编写代码更方便。
- 格外警惕从语义上破坏封装性。例如：
	- 不调用A类的initializeOperation()子程序，因为知道A类的performFirstOperation()子程序会自动调用他。
	- 不在调用employee.retrive(database)之前去调用database.connect()子程序，因为知道retrive()方法会去连接数据库。
	- 不去调用A类的termination()子程序，因为知道A类的performLastOperation()已经调用过了。
	- 即便在ObjectA离开作用域后，仍去使用由objectA创建的并指向的objectB的指针或引用，因为知道objectA把objectB放置在了静态存储空间，因此objectB还可以使用。
	- 使用ClassB.MAXIMUM_ELEMENTS而不是用ClassA.MAXIMUM_ELEMENTS，因为知道他们两个的值相等。
	- 上面的问题在于，他们让调用方代码不是依赖于类的公开接口，而是依赖于类的私用实现。此时就不是针对接口编程，而是透过接口使用内部实现来编程了。
- 留意过于紧密的耦合关系
	- 尽可能地限制类和成员的可访问性
	- 避免友元类，因为它们之间是紧密耦合的
	- 在基类中把数据声明为private而不是protected，以降低派生类和基类之间的耦合程度
	- 避免在类的公开接口中暴露成员数据
	- 要对从语义上破坏封装性保持警惕
	- 察觉Demeter法则

### 有关设计和实现的问题 ###
- 通过包含来实现“有一个 has a”的关系
- 在万不得已时通过private继承来实现“有一个”的关系
- 警惕有超过约7个数据成员的类
- 用public继承来实现“是一个 is a”的关系
- 要么使用继承并进行详细说明，要么就不要用它
- 遵循Liskov替换原则，派生类必须能通过基类的接口而被使用，且使用者无须了解二者之间的差异
- 确保只继承需要继承的部分。如果只是想使用一个类的实现而不是接口，则应该使用包含，而不是继承。继承而来的子程序有三种可能：
	- 抽象且可覆盖的子程序是指派生类只继承了该子程序的接口，但不继承其实现
	- 可覆盖的子程序是指派生类继承了该子程序的接口及其默认实现，并可以覆盖该默认实现
	- 不可覆盖的子程序是指派生类继承了该子程序的接口及其默认实现，但不能覆盖该默认实现
- 不要覆盖一个不可覆盖的成员函数。派生类中的成员函数不要与基类中不可覆盖的成员函数重名
- 把共用的接口，数据及操作放到继承树中尽可能高的位置
- 只有一个实例的类时值得怀疑的
- 只有一个派生类的基类也是值得怀疑的。不要创建任何不是绝对必要的继承结构
- 派生后覆盖了某个子程序，但在其中没做任何操作，这种情况也值得怀疑
- 避免让继承体系过深
- 尽量使用多态，避免大量的类型检查。频繁重复出现的case语句有时实在暗示，采用继承可能是种更好的设计选择
- 让所有的数据都是private，而不是protected。如果派生类真的需要访问基类的属性，就应该提供protected的访问器子程序

继承和包含的使用建议：
- 如果多个类共享数据而非行为，应该将这些共享的数据抽象出来创建一个类，让其他类共享这个类的对象
- 如果多个类共享行为而不是数据，应该让他们从共同的基类继承而来，并在基类中定义共用的子程序
- 如果多各类既共享数据也共享行为，应该让他们从一个共同的基类继承而来，并在基类中定义共用的数据和子程序
- 当想由基类控制接口时，使用继承；当想自己控制接口时，使用包含

### 成员函数和数据成员 ###
- 让类中子程序的数量尽可能少
- 禁止隐式地产生不需要的成员函数和运算符
- 减少类所调用的不同子程序的数量
- 对其他类的子程序的间接调用要尽可能少
- 一般应尽量减少类与类之间相互合作的范围。让下面几种数字最小：
	- 所实例化的对象的种类
	- 在被实例化对象上直接调用的的不同子程序的数量
	- 调用由其他对象返回的对象的子程序的数量


### 构造函数 ###
- 如果可能，应该在所有的构造函数中初始化所有的数据成员
- 用私有构造函数来强制实现单件属性
- 优先采用深层复本，除非论证可行，才采用浅层复本

### 创建类的原因 ###
- 为现实世界中的对象建模
- 为抽象的对象建模
- 降低复杂度
- 隔离复杂度
- 隐藏实现细节
- 限制变动的影响范围
- 隐藏全局数据。通过访问器子程序来操控全局数据
- 让参数传递更顺畅。需要把一个参数在多个子程序之间传递，就可能表明应该把这些子程序重构到一个类里，把这个参数当做对象数据来共享
- 建立中心控制点
- 让代码更易于重用
- 为程序族做计划，如果能预计到某个程序要被修改，可以把要被改动的部分放到单独的类里，同其他部分隔离开
- 把相关的操作包装到一起
- 实现某种特定的重构

### 应该避免的类 ###
- 避免创建万能的类
- 消除无关紧要的类
- 避免用动词命名的类

### chapter 7 高质量的子程序 ###

子程序是为了实现特定目的而编写的可调用的方法 method 或过程 procedure。子程序应该有单一而明确的目的。如果他的输入变量可以被修改，则不应该使用前缀为input的变量名。

子程序可以：

- 降低复杂度
- 引入易懂的中间抽象
- 避免代码重复
- 支持子类化
- 隐藏顺序
- 隐藏指针操作
- 提高可移植性
- 简化复杂的布尔判断
- 改善性能

对于子程序而言，内聚性是指子程序中各种操作之间联系的紧密程度。

内聚性可分为：

- **功能的内聚性 functional cohesion**：一个子程序仅执行一项操作。
- **顺序上的内聚性 sequential cohesion**：一个子程序内包含有需要按特定顺序执行的操作，这些步骤需要共享数据，只有在全部执行完毕后才能完成一项完整的功能。
- **通信上的内聚性 communicational cohesion**：一个子程序中的不同操作使用了同样的数据，但不存在其他任何联系。
- **临时的内聚性 temporal cohesion**：一个子程序含有一些因为需要同时执行才放到一起的操作。
- **过程上的内聚性 procedural cohesion**：一个子程序中的操作是按特定顺序进行的，这些操作并不需要为了除此之外的任何其他原因而彼此关联。和顺序上的内聚性不同，这些操并不需要共享数据。
- **逻辑上的内聚性 logical cohesion**：若干操作被放入到同一个子程序中，通过传入的控制标志选择执行其中的一项操作。之所以会放在一起仅仅是为了子程序的控制流。如果子程序里的代码仅由一系列的if语句或者case语句，以及调用其他子程序等等语句组成，那么创建这样一个具有逻辑上得内聚性的子程序也可以接受。此时子程序的唯一功能是发布各种命令，本身并不做任何处理。也就是常说的事件处理器 event handler。
- **巧合的内聚性 coincidental cohesion**：一个子程序中的各个操作之间没有任何明显的关联。


#### 好的子程序名 ####

- 描述子程序所做的所有事情。子程序的名字应当描述其所有的输出结果以及副作用 side effect。如果副作用很多，纳闷名字就会很长，此时应该换一种方式编程序。
- 避免使用无意义的，模糊或表述不清的动词。
- 不要仅通过数字来形成不同的子程序名字。
- 根据需要确定子程序名字的长度。变量名的最佳长度是9-15个字符。
- 给函数命名时要对返回的值有所描述。
- 给过程起名时使用语气强烈的动词加宾语的形式。在面向对象的语言中，不用加入宾语。
- 准确使用对仗词。
	- add/remove
	- begin/end
	- create/destory
	- first/last
	- get/put
	- get/set
	- increment/decrement
	- insert/delete
	- lock/unlock
	- min/max
	- next/previous
	- old/new
	- open/close
	- show/hide
	- source/target
	- start/stop
	- up/down
- 为常用操作确立命名规则

#### 子程序应该写多长 ####

理论上应该是在50-150行左右，若包含复杂的算法可以在100-200行左右。

#### 如何使用子程序参数 ####

- 按照输入-修改-输出的顺序摆列参数。应该先列出仅作为输入用途的参数，然后是既作为输入也作为输出的参数，最后才是仅作为输出的参数。
- 考虑自己创建in和out关键字。
- 如果几个子程序都使用了类似的一些参数，应该让这些参数的排列顺序保持一致。
- 使用所有的参数。
- 把状态或出错变量放在最后
- 不要把子程序的参数用作工作变量，应该使用局部变量。
- 在接口中对参数加以说明。在子程序内部和调用子程序的地方同时对下列所做的假定进行说明。也可以使用断言。
	- 参数是仅用于输入的，要被修改的，还是仅用于输出的。
	- 表示数量的参数的单位。
	- 如果没有用枚举类型的话，应该说明状态代码和错误值的含义。
	- 所能接受的数值的范围。
	- 不该出现的特定数值。
- 把子程序的参数个数限制在大约7个以内。
- 考虑对参数采用某种表述输入，修改，输出的命名规则。
- 为子程序传递用以维持其接口抽象的的变量或对象。如果采用传递整个对象的方法，并发现自己是先创建对象，把被调用子程序所需的对象的属性填入该对象，在调用过子程序后又从对象中取出3项数据的值，说明你应该只传递那3项属性而不是整个对象。一般来说，如果在调用子程序之前出现进行装配 setup 的代码，或者在调用子程序之后出现拆卸 takedown 的代码，都是子程序设计不佳的表现。也就是说不应该只为传递部分属性而专门创建一个对象。如果发现需要经常修改子程序的参数表，而每次修改的参数都来自于同一个对象，那就说明应该传递整个对象而不是个别属性了。
- 使用具名参数。
- 确保实际参数与形式参数相匹配。

#### 函数的使用 ####
如果一个子程序的主要用途是返回由其名字所指明的返回值，就应该使用函数，否则就应该使用过程。函数和过程都可以使用一个状态变量作为显示参数来表示执行结果状态。

在函数的开头就初始化返回值，并检查所有可能的返回路径，确定一定会返回有效的结果。不要返回指向局部数据的引用或指针。

#### 宏子程序和内联子程序 ####

- 把宏表达式整个包含在括号内
- 把含有多条语句的宏用大括号括起来
- 用给子程序命名的方法来给展开后代码形同子程序的宏命名，以便在需要时可以用子程序来替换宏。


## chapter 8 防御式编程 ##
防御式编程的主要思想是：子程序应该不因传入错误数据而被破坏，哪怕是由其他子程序产生的错误数据。

### 保护程序免收非法输入数据的破坏 ###

- 检查所有来源于外部的数据的值。当从文件，用户，网络或其他外部接口中获取数据时，赢价差所获得的数据值，以确保他在允许的范围内。对于数值要确保在可接受的取值范围内；对于字符串要确保其不超长或符合格式需要。如果程序的安全性很重要，要格外注意可能是攻击型的数据，如企图令缓冲区溢出的数据，注入的SQL指令，注入的HTML或XML代码，整数溢出以及传递给系统调用的数据，等等。
- 检查子程序所有输入参数的值。
- 决定如何处理了错误的输入数据。
- 决定如何处理错误的输入数据。

### 断言 ###
断言 assertion 是指在开发期间使用的，让程序在运行时进行自检的代码。为真说明程序运行正常，为假说明发现了未预期的错误。一个断言通常有两个参数：一个描述假设为真时的布尔表达式，和一个断言为假时需要显示的信息。可以用断言检查如下假定：

- 输入参数或输出参数的取值处于预期的范围内；
- 子程序开始或者结束执行时文件或流是否处于打开或者关闭的状态；
- 子程序开始或者结束执行时，文件或流的读写位置处于开头还是结尾；
- 文件或流已用只读，只写或可读写方式打开；
- 仅用于输入的变量的值没有被子程序修改；
- 指针非空；
- 传入子程序的数组或其他容器至少能容纳X个数据元素；
- 表已初始化，存储着真实的数据；
- 子程序开始或结束执行时，某个容器是空的或满的；
- 一个经过高度优化的复杂子程序的运算结果和相对缓慢但代码更清晰的子程序的运算结果一样。

#### 使用断言的建议 ####

- 用错误处理代码来处理预期会发生的状况，用断言来处理绝对不应该发生的状况。断言是用来检查永远不应该发生的情况，而错误处理代码 error-handling code 是用来检查不太可能经常发生的非正常情况，这些情况是能在写代码时就预料到的，且在产品代码中也要处理这些情况。错误处理通常用来爱检查有害的输入数据，而断言是用于检查代码中的bug。错误处理代码检查来源不可信的数据，断言检查来源可信的数据。
- 避免把需要执行的代码放到断言中。
- 用断言来注释并验证前后条件 precondition/postcondition 。
	- 前条件是子程序或类的调用代码在调用子程序或实例化对象之前要确保为true的属性。前条件是调用方代码对其所调用的代码要承担的义务。
	- 后条件是子程序或类在执行结束后要确保为true的属性。是子程序或类对调用方代码所承担的责任。
- 对于高健壮性的代码，应该先使用断言再处理错误。此时，断言是防错机制，而错误处理代码是纠错机制。

### 错误处理技术 ###
在整个程序内采用一致的方式处理非法的参数。在每个系统调用后检查错误码。一旦检查到错误，就记下错误代号和他的描述信息。

- 返回中立值。继续执行操作并返回一个没有危害的数值。数值计算可以返回一个0，字符串操作可以返回一个空字符串，指针操作可以返回一个空指针，等等。
- 换用下一个正确的数据。
- 返回与前次相同的数据。
- 换用最接近的合法值。
- 把警告信息记录到日志文件中。
- 返回一个错误码。如果安全性很重要，要确认调用方的子程序总会检查返回的错误码。通知系统其余部分已发生错误可采用以下方式之一：
	- 设置一个状态变量的值。
	- 用状态值作为函数的返回值。
	- 用语言内建的异常机制抛出一个异常。
- 调用错误处理子程序或对象。
- 当错误发生时显示出错信息。
- 用最妥当的方式在局部处理错误。
- 关闭程序。

- 正确性 correctness：永远不返回不准确的结果。
- 健壮性 robustness：程序可以持久运行下去，哪怕返回不准确的结果

### 异常 ###
子程序使用throw抛出一个异常对象，再被调用链上层其他子程序的try-catch语句捕获。

- 用异常通知程序的其他部分，发生了不可忽略的错误。
- 只有真正例外的情况下才抛出异常。异常和断言相似，都用来处理那些不仅罕见甚至永远不该发生的情况。
- 不能用异常来推卸责任。如果某种错误可以在局部处理，就应该在局部处理掉。
- 避免在构造函数和析构函数中抛出异常，除非你在同一地方将其捕获。
- 在恰当的抽象层次抛出异常。
- 在异常消息中加入关于导致异常发生的全部信息。
- 避免使用空的catch语句。如果遇到某个较低层次上的异常确实无法表现为调用方抽象层次上的异常，那么必须写清楚为什么采用空的catch语句。也可以通过注释或者向日志文件中加入一条记录来文档化这一情况。
- 了解所用函数库可能抛出的异常。
- 考虑创建一个集中的异常报告机制。也就是说使用专门的子程序或对象来处理捕捉到的异常。
- 在项目中把对异常的处理标准化：
	- 为类似C++这种允许抛出多种对象，数据及指针的语言规定可以抛出哪些种类的异常。
	- 考虑创建项目的特定异常类，可以作为项目中所有可能抛出的异常的基类。
	- 规定在何种场合允许代码使用throw-catch语句在局部处理错误。
	- 规定在何种场合允许代码抛出不在局部处理的异常。
	- 确定是否要使用集中的异常报告机制。
	- 规定是否允许在构造函数和析构函数中使用异常。
- 考虑异常的替代方案。

### 隔离程序从而包容由错误造成的损害 ###
把某些接口选定为安全区域的边界。对穿越安全区域边界的数据及逆行合法性校验，当数据非法时做出反应。类的公用接口可以假设接受的数据都是不安全的，需要负责检查并处理错误数据。一旦类的公用方法接受了数据，类的私有方法就可以假定这些数据都是安全的了。

隔离的使用使断言和错误处理有了清晰地区分。隔栏外部的程序应假定所有的数据都是不安全的，并使用错误处理技术对数据进行处理。隔栏内部的程序认为数据已经被处理过，是安全的，此时用断言技术。一旦隔栏内部的数据发现了错误，那么这个错误应该是程序的错误而不是数据的错误。


### 辅助调试的代码 ###

- 采用进攻式编程： 
	- 确保断言语句使程序终止运行。
	- 完全填充已分配到的所有内存。
	- 完全填充已分配到的所有文件或流。
	- 确保每一个case语句中的default分支或else分支都能产生严重的错误，或者至少让这些错误不会被忽视。
	- 让程序把他的错误日志文件用email发给你。
- 使用类似ant和make这样的版本控制工具和make工具。
- 使用内置的预处理器。
- 编写自己的预处理器。
- 使用调试存根 debuging stubs。

### 最终的产品代码中应该保留多少防御式代码 ###

保留那些检查重要错误的代码
去掉检查细微错误的代码。并不是删除，而是利用版本控制工具，预编译器等屏蔽这些代码。
去掉可以导致程序恶性崩溃的代码。
保留可以让程序稳妥地崩溃的代码。
为你的技术支持人员记录错误信息。开发版代码中的断言会中止程序的运行，产品版代码可以把他们改为向日志文件中添加记录信息。
确认留在代码中的错误消息是友好的。

## chpater 9 伪代码编程 ##

### 创建类和子程序的步骤概述 ###
创建类的步骤：

- 创建类的总体设计。定义类的职责，类所要隐藏的内容，类的接口所代表的抽象概念；这个类是否是派生类，是否能够被继承，关键的公用方法，标示并设计出类所需要用到的重要数据成员。
- 创建类中的子程序。
- 复查并测试整个类。

### 伪代码 ###

- 用类似英语的语句来精确描述特定的操作。
- 避免使用目标编程语言中的语法元素。
- 在要实现目标的层面上编写伪代码。用伪代码去描述结局问题的方法的意图，而不是写如何在目标语言中实现这个方法。
- 从抽象层次的高到低，采用迭代的方法，最终在一个足够低的层次上编写伪代码。

在根据伪代码编写代码的同时，可以把伪代码改写为注释。

### 通过伪代码创建子程序 ###

#### 设计子程序 ####
- 检查先决条件。
- 定义子程序要解决的问题。
	- 这一子程序将要隐藏的信息；
	- 传给这个子程序的各项输入；
	- 子程序的输出；
	- 子程序被调用时要满足的前条件；
	- 子程序被调用后要满足的后条件；
- 为子程序命名。
- 决定如何测试子程序。
- 在标准库中搜寻可用的功能。
- 考虑错误处理。所有可能出错的环节。
- 考虑效率问题。
- 研究算法和数据类型。
- 编写伪代码。先从最一般的情况写起，逐步加入更多的细节。在头部注释说明子程序的目的。
- 考虑数据。在伪代码层次设计数据类型。
- 检查伪代码。
- 在伪代码中试验想法，并留下最好的选择。

#### 编写子程序代码 ####

- 写出子程序的接口声明。
- 把伪代码转变成高层次的注释。把第一条和最后一条语句写出来。在Java中是 { 和 } 。然后把伪代码转变为注释。
- 在每条注释下面填充代码。在伪代码注释中的每一句话下面填入代码。所有的变量都是在靠近第一次使用的地方进行声明和定义的。每段注释通常应该展开为2-10行代码。
- 检查代码是否需要进一步分解
	- 把注释下面的代码重构成一个新的子程序
	- 递归地应用伪代码编程过程

#### 检查代码 ####

- 在脑海里检查程序中的错误
- 编译子程序
- 把编译器的警告级别调到最高
- 使用验证工具
- 消除产生错误消息和警告的所有根源
- 在调试器中逐行执行代码
- 用测试用例测试代码
- 消除程序中的错误

#### 收尾工作 ####

- 检查子程序的接口。确认所有的输入，输出数据都参与了计算，并且所有的参数也都用到了。
- 检查整体的设计质量。确认这个子程序使用防御式设计只完成并做好一件事，子程序之间是松散耦合。
- 检查子程序中的变量，检查是否存在不准确的变量名称，未被用到的对象，未经声明的变量，以及未经正确初始化的对象等。
- 检查子程序的语句和逻辑。检查是否存在偏差1，死循环，错误的嵌套以及资源泄露。
- 检查子程序的布局。
- 检查子程序的文档。
- 除去冗余的注释。


## chapter 10 使用变量的一般事项 ##

### 变量初始化原则 ###

- 在声明变量的时候初始化。
- 在靠近变量第一次使用的位置初始化他。就近原则 principle of proximity：把相关的操作放在一起。让注释靠近他所描述的代码，让控制循环的代码靠近循环本身。
- 理想情况下，在靠近第一次使用变量的位置声明并初始化该变量。
- 在可能的情况下使用final或者常量。
- 特别注意计数器和累加器。
- 在类的构造函数里初始化该类的数据成员。
- 一次性初始化具名常量，用可执行代码来初始化变量。
- 使用编译器设置来自动初始化所有变量。
- 利用编译器的警告信息。
- 检查输入参数的合法性。
- 使用内存访问检查工具来检查错误的指针。
- 在程序开始时初始化工作内存。
	- 可以用某种在程序运行前预先填充内存的工具来把程序的工作内存填充为一个可以预料的值；
	- 如果使用内存填充工具，可以偶尔改变一下用来填充内存的值。
	- 可以让程序在启动时初始化工作内存。

### 作用域 ###
作用域或者可见性 visibility 指的是变量在程序中的可见和可引用的范围。

#### 使变量引用局部化 Localize References to Variables ####
攻击窗口 window of vulnerability：介于同一变量多个引用点（包括初始化点）之间的代码。把对一个变量的引用局部化，把引用点尽可能集中在一起。

跨度 span：两个引用点（包括初始化点）之间间隔的代码行数。

#### 尽可能缩短变量的存活时间 Keep Variables Live for as Short a Time as Pssible ####
存活时间 live time：一个变量存在期间所跨越的语句总数，开始于初始化点，结束于引用它的最后一条语句。

长存活时间意味着一个变量经历了很多语句，短存活时间意味着只经历很少的语句，跨度则表明了对一个变量引用的集中程度。

#### 减少作用域的一般原则 General Guidelines for Minimizing Scope ####

- 在循环开始之前再去初始化该循环里使用的变量，而不是在该驯化所属的子程序的开始处初始化这些变量。
- 知道变量即将被使用时再为其赋值。
- 把相关语句放在一起。减少使用变量的跨度和存活时间。
- 把相关语句组提取成单独的子程序。
- 开始时采用最严格的可见性，然后根据需要扩展变量的作用域。

### 持续性 Persistence ###
数据的持续性就是他的生命周期。关于数据持续性的建议：

- 在程序中加入调试代码或者断言来检查那些关键变量的合理取值。
- 准备抛弃变量时给他们赋上不合理的数值。
- 编写代码时要假设数据并没有持续性。
- 养成在使用所有数据之前声明和初始化的习惯。

#### 绑定时间 Binding Time ####
采用越晚的绑定时间越有利。绑定的时间按照复杂度和灵活度从低到高排列：

- 编码时，使用神秘数值。
- 编译时，使用具名常量。
- 加载时，从windows注册表，Java属性文件等外部数据源中读取数据。
- 对象实例化时，例如在每次窗体创建的时候读取数据。
- 即时，例如在每次窗体重绘的时候读取数据。

后三种方法的区别在于，负责读取数据的子程序的级别不一样，主程序调用创建窗体子程序，创建窗体子程序又会调用重绘窗体的子程序。

#### 数据类型和控制结构之间的关系 Relationship Between Data Types and Control Structures ####

- 序列型数据对应于顺序语句。
- 选择型数据对应于if和case语句。
- 迭代型数据对应for，repeat，while等循环结构。

#### 为变量制定单一用途 Using Each Variables for Exactly One Purpose ####

- 每个变量只用于单一用途。
- 避免让代码具有隐含含义。不要出现混乱耦合 hybrid coupling。这样的变量一般具有2种以上的用途。例如，pageCount在正常的情况表示纸张的数量，此时他是一个整数，如果等于-1，则表明有错误发生，此时客串了布尔类型。
- 确保使用了所有已声明的变量。


## 变量名的力量 Power of Variable Names ##
以问题为向导为变量名取名。变量名的平均长度在10到16个字符之间。把表示结果的限定词，如Total，Sum，Average，Max，Min，Record，String，Pointer等，加到名字的最后。Num放在变量名开始位置代表一个总数，Num放在变量名的结束位置代表一个下标。

变量名中常用的对词：

- begin/end
- first/last
- locked/unlocked
- min/max
- next/previous
- old/new
- opend/closed
- visible/invisible
- source/target
- source/destination
- up/down

### 为特定类型的数据命名 Naming Specific Types of Data ###
#### 循环下标 Naming Loop Indexes ####
为循环下标取有意义的名字。特别是多重嵌套。

#### 状态变量 Naming Status Variables ####
状态变量用于描述程序的状态。应该使用枚举类型，具名常量，或用作具名常量的全局变量来为其赋值。

#### 布尔变量 Naming Boolean Variables ####
常用的布尔变量：

- done：表示某件事已完成。
- error：表示有错误发生。
- found：表示某个值已找到。
- success/ok：表示某项操作是否成功。最好用一个更具体的名字来说明是什么操作成功了。

布尔变量的名字应该含有真/假的意思。并使用表示肯定的名字。

#### 枚举类型 Naming Enumerated Types ####
可以为枚举类型的变量名前面加上组前缀。

#### 常量 Naming Constants ####
常量名应该根据该常量所表示的含义，而不是他所具有的数据来命名。

### 非正式命名规则 Informal Naming Conventions ###
#### 与语言无关的指导原则 Guidelines for Language-Independent Convention ####

- 区分变量名和子程序名字。
- 区分类和对象。变量名应该比类名更明确和具体。
- 标识全局变量。例如`g_name`
- 标识成员变量。例如`m_name`
- 标识类型声明。
- 标识具名常量。全部大写，或加`c_`前缀
- 标识枚举类型的元素。
- 在不能保证输入参数只读的语言例标识只读参数。例如在参数名的前面加上一个`const`前缀
- 格式化命名以提高可读性。

#### 与语言有关的指导原则 Guidelines for Language-Specific Conventions ####
@TODO： page 275-279

### b标准前缀 Standardized Prefixes ###
标准化的前缀分为两部分：

- 用户自定义类型 UDT 的缩写。可以标识被命名对象或变量的数据类型。通常不会表示任何由编程语言所提供的预置数据类型。例如：
	- ch  ： 字符
	- doc ： 文档
	- pa  ： 段落
	- scr ： 屏幕区域
	- sel ： 选中范围
	- wn  ： 窗体
- 语义前缀。
	- c     ： 数量，count
	- first ： 数组中需要处理的第一个元素。与min类似，但是相对于当前的操作而不是数组本身。
	- g     ： 全局变量
	- i     ： 数组的下标
	- last  ： 数组中需要处理的最后一个元素。与first相对应。
	- lim   ： 数组中需要处理的元素上限。通常lim等于last+1
	- m     ： 类变量
	- max   ： 数组或者其他种类的列表中绝对的最后一个元素。反映的是数组本身，而不是针对数组的操作。
	- min   ： 数组或其他种类的列表中绝对的第一个元素。
	- p     ： 指针

### 创建具备可读性的短名字 Creating Readable Short Names  ###
#### 缩写的一般指导原则 General Abbreviation Guidelines ####
- 使用字典中常见的缩写。
- 去掉所有非前置元音。computer变成cmptr，screen变成scrn，apple变成appl，integer变成intgr
- 去掉虚词and，or，the等
- 使用每个单词的第一个或前几个字母。
- 统一地在每个单词的第一，第二或者第三个字母后截断。
- 保留每个单词第一个和最后一个字母。
- 使用名字中的每一个重要单词，最多不超过3个。
- 去除无用的后缀，ing，ed等。
- 保留每个音节中最引人注意的发音。
- 确保不要改变变量的含义。

其他注意事项：

- 不要从每个单词中删除一个字符的方式来缩写。
- 缩写要一致。
- 创建你能读出来的名字。
- 避免使用容易看错和读错的字符组合。
- 使用词典来解决命名冲突。
- 在代码里用缩写对照表解释极短的名字的含义。
- 在一份项目级的标准缩写文档中说明所有的缩写。

### 应避免的名字 Kinds of Names to Avoid ###

- 避免使用令人误解的名字或缩写。
- 避免使用具有相似含义的名字。
- 避免使用具有不同含义但却有相似名字的变量。
- 避免使用发音相似的名字。如wrap和rap
- 避免使用在名字中使用数字。如果名字中的数字真的非常重要，就使用数组来代替一组单个的变量。如果数组不合适，那么数字就更不合适。
- 避免在名字中拼错单词。
- 避免使用英语中常常拼错的单词。
- 不要仅靠大小写来区分变量名。
- 避免使用多种自然语言。
- 避免使用标准类型，变量和子程序的名字。
- 不要使用与变量含义完全无关的名字。
- 避免在名字中包含易混淆的字符。如：数字1和小写字母l，大写字母I，符号.和,，数字0和字母o，数字2和大写字母Z，：和；，大写字母S和数字5，大写字母G和数字6


## chapter 31 布局与风格 ##

### 良好布局的目标 ###
- 准确表现代码的逻辑结构
- 始终如一地表现代码的逻辑结构
- 改善可读性
- 经得起修改

### 布局技术 ###

- 分组
- 空行。代码中的一个段落的前面应该加上空行。空行也可以将相关语句各自划分成段落，分开子程序，突出注释部分。空行的最佳比例一般为8%-16%。
- 缩进
- 括号

### 布局风格 ###

- 纯块结构
- 模仿纯块结构
- 使用 begin-end 对或者花括号指定块边界
- 行尾布局

### 控制结构的布局 ###

- 不要用未缩进的 begin-end 对
- 别让begin和end两次缩进
- 段落之间要使用空行
- 单语句代码块的格式要前后统一
- 对于复杂的表达式，将条件分隔放在几行上
- 不用goto。如果必须使用，遵循下列原则：
	- 转到的标号全部用大写字母表示
	- 包含goto的语句单独作为一行
	- 将goto语句转去的标号单独作为一行，上下也为空行。
- case语句不要有行尾布局的例外

### 单条语句的布局 ###

- 使用空格让逻辑表达式更易读懂
- 使用空格让数组引用更易读
- 使用空格让子程序参数更易读
- 断句时
	- 使续行明显。断句最简单的方法是将上一行部分做成若单独是就有明显语法错误的形式，如以逻辑运算符&&，||，&， |等结尾。
	- 把紧密关联的元素放在一起，若数组下标，子程序参数等。
	- 将子程序调用的后续行按标准量缩进。
	- 让后续行的结尾易于发现。
	- 将控制语句的后续行缩进以标准的空格数。
	- 不要将赋值语句按等号对齐。
	- 对赋值语句后续行按标准量缩进。
- 每行只写一条语句，并且不让这条语句有多个操作（副作用），如++操作和其他操作混用。
- 声明数据时，
	- 每行只声明一个数据
	- 变量声明应尽量接近其首次使用的位置
	- 合理组织声明顺序
	- C++中，声明指针变量时把星号靠近变量名，或者去声明指针类型。

### 注释的布局 ###

- 注释的缩进要与相应的代码一致
- 每行注释用至少一个空行与上一行分开

### 子程序的布局 ###

- 用空行分隔子程序的各部分。在子程序的头，数据和和常量名声明以及子程序体之间插入空行
- 将子程序参数按标准缩进

### 类的布局 ###

- 类接口的布局
	- 说明类及其完整用法的头部注释
	- 构造函数与析构函数
	- public子程序
	- protected 子程序
	- private子程序和数据成员
- 类实现的布局
	- 描述类所在文件之内容的头部注释
	- 类数据
	- public子程序
	- protected子程序
	- private子程序
- 如果文件中包含多个类，要清楚地标出每一个类，用空行将类与相邻类分开。不要在类里过度注释，过度使用星号等分隔符。如果需要，类分隔开一用星号，子程序间用连字符，重要的注释使用空行。
- 文件和程序的布局
	- 一个文件应只有一个类
	- 文件的命名应与类名有关
	- 在文件中清晰地分隔子程序，至少用两个空行或分隔符将各子程序分开
	- 按字母顺序排列子程序
	- 仔细组织C++源文件中内容的次序：
		1. 文件的描述性注释
		2. `#include`文件行
		3. 在多个类里使用的敞亮的定义（如果文件里有多个类）
		4. 在多个类中使用的枚举（如果文件里有多个类）
		5. 宏函数定义
		6. 在多个类里使用的类型定义（如果文件里有多个类）
		7. 导入的全局变量和函数
		8. 导出的全局变量和函数
		9. 本文件私用的变量和函数
		10. 各个类，包括各个类中的常量定义，枚举以及类型定义

## chapter 32 自说明代码 ##

### 外部文档 ###

- **单元开发文件夹 unit-development folder UDF/软件开发文件夹 software-development folder SDF**：是一种非正式文档，其中包含了供开发者在编程期间使用的记录。单元没有严格的定义，一般指类，也可以指程序包或者组件。主要用途是提供在其他地方没有说明的设计决策踪迹。
- **详细设计文档**：是低层次的设计文档，描述在类层或子程序层的设计决定，曾考虑过的其他方案，以及采用所选方案的理由。

### 注释的种类 ###

- 重复代码
- 解释代码
- 代码标记
- 概述代码
- 代码意图说明
- 传递代码无法表述的信息

对于完工的代码，只允许有后三种类型的注释。

### 高效注释的关键 ###

- 采用不会打断或抑制修改的注释风格
- 用伪代码编程法减少注释所用时间
- 将注释继承到你的开发风格中。在写代码之前或同时编写注释。
- 不因为性能逃避注释

### 注释的技术 ###

#### 注释单行 ####

- 好的代码很少需要注释单条语句，如果有，可能基于以下理由
	- 改行代码太复杂，需要解释。此时考虑重新改善设计。
	- 改行代码出错，需要记下这个错误。
- 不要随意添加无关的注释。

#### 行尾注释 ####

- 不要对单行代码做行尾注释。
- 不啊哟对多行代码做行尾注释。
- 行尾注释可用于数据声明。
- 避免用行尾注释存放维护标记。注释应该解释代码为什么现在能用，而不是过去为什么不工作。
- 用行为注释标记块尾。

#### 注释代码段 ####

- 注释应表达代码的意图。一种方法是将这段代码假想为一个子程序，他的名字可以作为注释需要表达的意思。
- 代码本身应尽力做好说明。
- 注释代码段时应注重为何做，而不是怎样做。描述目的而不是实现。
- 用注释为后面的内容做铺垫。
- 让每个注释都有用。
- 说明非常规做法。
- 别用缩略语。
- 将主次注释区分开。可以将这段代码抽出来作为一个子程序，主注释作为这个子程序的注释，次注释作为子程序内部代码段的注释。
- 错误或语言环境独特特点都要加注释。
- 给出违背良好编程风格的理由。
- 不注释投机取巧的代码，应该重新设计。

#### 注释数据声明 ####

- 注释数值单位
- 对数值的允许范围给出注释。
- 注释编码含义。0代表何意，1代表何意，等等。
- 注释对输入数据的限制。
- 注释位标志，0000何意，0010何意，0A2F何意，等等。
- 将与变量有关的注释通过变量名关联起来。若变量名发生更改，应及时更新相应的注释。
- 注释全局数据。解释为什么使用全局数据。

#### 注释控制结构 ####

- 应在每个if，case，循环或者代码段前面加上注释。
- 应在每个控制结构后加上注释。
- 如果循环结束处的注释离循环开始处太远，则可看成是代码太复杂的征兆。 

#### 注释子程序 ####

- 注释应靠近其说明的代码。
- 在子程序上部用一两句话说明。
- 在声明参数出注释这些参数，或者使用诸如Javadoc之类的代码说明工具在子程序注释中使用@param，@return等说明。
- 分清输入和输出数据。
- 注释接口假设。可以使用断言。要确保注释了所有的全局变量。
- 对子程序的局限性做注释。比如：
	- 数值结果的精确度。
	- 什么条件下计算没定义。
	- 子程序遇到麻烦时的默认行为。
	- 子程序只工作于特定大小的数组或表格。
	- 可能会损坏子程序的修改。
	- 其他问题。
- 说明子程序的全局效果。描述对全局数据的修改。
- 记录所用算法的来源

#### 注释类，文件和程序 ####

- 注释类的一般原则：
	- 说明该类的设计方法。
	- 说明局限性，用法假设等。
	- 注释类接口。
	- 不要在类接口处说明实现细节。
- 注释文件的一般原则：
	- 说明个文件的意图和内容。如果一个文件中包含多个类，解释原因。
	- 将联系方式放入到注释中。
	- 包含版本控制标记。
	- 在注释中包含法律通告。
	- 将文件命名为与其内容相关的名字。
- 注释程序：
	- 序。一组常见于文件头的注释，起到介绍程序的作用。
	- 目录。给出顶层文件，类和子程序。
	- 节。子程序内的各单位。如子程序声明，数据声明和可执行语句。
	- 交叉引用。代码的“参阅...”映射，含有行号。