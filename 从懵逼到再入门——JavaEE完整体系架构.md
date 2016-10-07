
![](http://upload-images.jianshu.io/upload_images/1714316-7dc9926e6015f2da.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


> 理想的建筑师应该既是文学家又是数字家，他还应通晓历史，热衷于哲学研究，精通音乐，懂得医药知识，具有法学造诣，深谙天文学及天文计算。
——Vitruvius（古罗马建筑师） 约公元前25年


软件架构同样需要方方面面的知识和积累。本文是我自己学习JavaEE的体系架构的时候，根据各种资料学习涂涂画画整理所得，有不对之处求轻喷，也请指出便于改正。

JavaEE是一套使用Java进行企业级Web应用开发的大家一致遵循的工业标准。
JavaEE平台提供了一个基于组件的方法来加快设计、开发、装配及部署企业应用程序。
相较于Microsoft的.NET，Sun公司的Java*E和一系列标准、技术及协议更接近或更满足互联网在智能化Web服务方面对开放性、分布性和平台无关性的要求。

### JavaEE的13种核心技术规范：
###### 1、JDBC（Java Database）数据库连接
JDBC是一组用于执行SQL的Java API ，为访问不同的数据库提供了一种统一的途径，几乎所有的关系型数据库厂商（DBMS）都提供了JDBC的服务或驱动。JDBC对数据库的访问也具有平台无关性。

![JDBC处理模型](http://upload-images.jianshu.io/upload_images/1714316-9261f692fea3c64a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


###### 2、JNDI（Java Naming and Directory Interfaces）Java 的命名和目录接口
JNDI是命名目录服务的抽象接口集合，为企业级应用提供了统一的标准化连接，使Java能够无缝地获取任何可目录化的企业信息。在JavaEE体系中，JNDI用来定位各种对象，包括EJB、数据库驱动、JDBC数据源及消息连接等。由于JNDI是独立于目录协议的，因此还可以用JNDI访问各种特定的目录服务，如LDAP（轻量目录访问协议）、NDS（服务器目录访问服务）。

![JNDI数据源](http://upload-images.jianshu.io/upload_images/1714316-e3506af13beee663.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


###### 3、EJB（Enterprise JavaBean）
EJB组件：JavaBean是在编程环境（IDE）中能够被可视化处理的可重用组件，是实现分布式业务逻辑的 Java 组件。我们在开发的时候可以利用这些组件，像搭积木一样建立面向对象的分布式应用。
EJB容器：是EJB组件的运行环境，为部署EJB组件提供服务，包括事务、安全、远程客户端的网络发布、资源管理等。
EJB服务器：管理EJB容器的高端进程或应用程序，并提供对系统服务的访问。
调用EJB组件的应该称为EJB客户端，客户端可以运行在Web容器中。

![EJB](http://upload-images.jianshu.io/upload_images/1714316-a3b9d8607d2d507f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


###### 4、RMI（Remote Method Invoke）远程方法调用
RMI协议能够让在某个Java虚拟机上的对象，像调用本地对象一样调用另一个Java虚拟机中的对象上的方法。它使用了序列化方式在客户端和服务器端传送数据。RMI是一种被EJB使用的更底层的协议。（stub/skeleton层提供了客户程序和服务程序彼此交互的接口）

![RMI远程调用](http://upload-images.jianshu.io/upload_images/1714316-f551961200411951.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


###### 5、Java IDL（Interface Description Language）/CORBA（Common Object Broker Architecture）Java 接口定义语言/公用对象请求代理程序体系结构
IDL是用来描述软件组件接口的一种计算机语言。IDL通过一种中立的方式来描述接口，使得在不同平台上运行的对象和用不同语言编写的程序可以相互通信交流。


###### 6、JSP（Java Server Pages）
JSP页面由HTML代码和嵌入其中的Java代码所组成。服务器在页面被客户端所请求以后对这些Java代码进行处理，然后将生成的HTML页面返回给客户端的浏览器。
JSP可以使用Servlet提供的API，一般和JavaBean结合使用，从而将界面表现和业务逻辑分离。

![JSP](http://upload-images.jianshu.io/upload_images/1714316-fe248f20167d8164.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


###### 7、Servlet
Servlet是一种小型的Java程序，它扩展了Web服务器的功能。作为一种服务器端的应用，当被请求时开始执行。Servlet提供的功能大多与JSP类似，不过实现的方式不同。JSP通常是大多数HTML代码中嵌入少量的Java代码，而servlets全部由Java写成并且生成HTML。


###### 8、XML（Extensible Markup Language）可扩展白标记语言
XML是一种用于标记电子文件使其具有结构性的标记语言。它被用来在不同的商务过程中共享数据。XML的发展和Java是相互独立的，但是它和Java有着相同的目标，即平台独立性。通过Java和XML的组合，可以得到一个完美的具有平台独立性的解决方案。


###### 9、JMS（Java Message Service）Java 消息服务
JMS是Java的消息服务，JMS的客户端之间可以通过JMS服务进行异步的消息传输。JMS用于和面向消息的中间件相互通信的应用程序接口(API)。它既支持点对点的域，有支持发布/订阅(publish/subscribe)类型的域，并且提供对下列类型的支持：经认可的消息传递,事务型消息的传递，一致性消息和具有持久性的订阅者支持。
JMS消息系统带来的好处：1、提供消息灵活性；2、松散耦合；3、异步性。

![JMS点对点](http://upload-images.jianshu.io/upload_images/1714316-a5586a6ed1bbc49e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


###### 10、JTA（Java Transaction API）Java 事务 API
在JavaEE应用中，事务是一个不可或缺的组件模型，它保证了用户操作ACID（即原子、一致、隔离、持久）属性。对于那些跨数据源（例如多个数据库，或者数据库与JMS）的大型应用，则必须使用全局事务JTA。应用系统可以由JTA定义的标准API访问各种事务监控，JTA为JavaEE平台提供了分布式事务服务，它隔离了事务与底层的资源，实现了透明的事务管理方式。

![JTA](http://upload-images.jianshu.io/upload_images/1714316-d2c28532c002d703.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


###### 11、JTS（Java Transaction Service）Java 事务服务
JTS是一个组件事务监视器。JTS是CORBA OTS事务监控的基本实现。JTS规定了事务管理器的实现方式。JTS事务管理器为应用服务器、资源管理器、独立的应用以及通信资源管理器提供了事务服务。


###### 12、JavaMail
JavaMail是用于存取邮件服务器的API，它提供了一套邮件服务器的抽象类。不仅支持SMTP服务器，也支持IMAP服务器和POP服务器。


###### 13、JAF（JavaBean Activation Framework）
JavaMail利用JAF来处理MIME编码的邮件附件。MIME的字节流可以被转换成Java对象，或者转换自Java对象。大多数应用都可以不需要直接使用JAF。


### JavaEE软件开发体系架构
###### 两层架构
传统的客户服务器系统仅只简单地基于两层体系来构建，即客户端（前台）和企业信息系统（后台），没有任何中间件，业务逻辑层与表示层或数据层混在一起。这种两层架构无论从开发、部署、扩展、维护来说，综其只有一个特点——成本高。


###### 三层架构
三层架构自上而下将系统分为表示层、逻辑层、持久层。
表示层由处理用户交互的客户端组件及其容器所组成；
业务逻辑层由解决业务问题的组件组成；
数据层由一个或多个数据库组成，并可包含存储过程。
这种三层架构，在处理客户端的请求时，使客户端不用进行复杂的数据库处理；透明地为客户端执行许多工作，如查询数据库、执行业务规则和连接现有的应用程序；并且能够帮助开发人员创建适用于企业的大型分布式应用程序。

![三层架构](http://upload-images.jianshu.io/upload_images/1714316-fe4df5ff9b3121b4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


###### MVC
在MVC模式中，应用程序被划分为模型层（Model）、视图层（View）、控制层（Controller）三部分。MVC模型就是把一个应用程序的开发按照业务逻辑、数据、视图进行分离分层并组织代码。MVC要求把应用的模型按一定的层次规则抽取出来，将业务逻辑聚集到一个部件里面，在改进和个性化定制界面及用户交互的同时，不需要重新编写业务逻辑。模型层负责封装应用的状态，并实现功能，视图层负责将内容呈现给用户，控制层负责控制视图层发送的请求以及程序的流程。
`Servlet`+`JSP`+`JavaBean`（MVC）这种模式比较适合开发复杂的web应用，在这种模式下，Servlet负责处理用户请求，JSP负责数据显示，JavaBean负责封装数据。
![MVC](http://upload-images.jianshu.io/upload_images/1714316-9372e7e24595ec90.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


###### 基于JavaEE架构模式下的MVC
在这种架构模式下，模型层（Model）定义了数据模型和业务逻辑。为了将数据访问与业务逻辑分离，降低代码之间的耦合，提高业务精度，模型层又具体划分为了DAO层和业务层，DAO即Data Access Object，其主要职能是将访问数据库的代码封装起来，让这些代码不会在其它层出现或者暴露出来给其它层；业务层是整个系统最核心也是最具有价值的一层，该层封装应用程序的业务逻辑，处理数据，关注客户需求，在业务处理过程中会访问原始数据或产生新数据，DAO层提供的DAO类能很好地帮助业务层完成数据处理，业务层本身侧重于对客户需求的理解和业务规则的适应，总体说来，DAO层不处理业务逻辑，只为业务层提供辅助，完成获取原始数据或持久层数据等操作。

![基于JavaEE架构模式下的MVC](http://upload-images.jianshu.io/upload_images/1714316-ee96fee35c11709a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- JSP：JSP被用来产生Web的动态内容。这层把应用数据以网页的形式呈现给浏览器，然后数据按照在JSP中开发的预定的方式表示出来，这层也可以称之为布局层。
- Servlet：JSP建立在Servlet之上，Servlet是J2EE的重要组成部分。Servlet负责处理用户请求，Java Web项目的所有配置都写在了`web.xml`配置文件里，当项目运行的时候，`web.xml`会将http请求映射给对应的Servlet类。
- JavaBean：由一些具有私有属性的Java类组成，对外提供get和set方法。JavaBean负责数据，负责处理视图层和业务逻辑之间的通信。
- Service：业务处理类，对数据进行一些预处理。
- DAO：数据访问层，JDBC调用存储过程，从数据库（DataBase）那里获取到数据，再封装到Model实体类中去。

_________________
需要文中的资料可以私我。

![](http://upload-images.jianshu.io/upload_images/1714316-3ffe3b8fd063a105.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/1714316-dff32dc56aaa6a89.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 转载请注明出处！
同时发布在



