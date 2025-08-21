## 软件开发原则

核心是 **OCP（开闭原则）**，对扩展开放，对修改关闭

拓展的同时不用修改，方便。

其余6个原则是为它服务

 

***\*DIP 依赖倒置\****

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1F9E.tmp.jpg) 

降低耦合，提高扩展

 

 

违背OCP和DIP，可以采用***\*控制反转\****

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1F9F.tmp.jpg) 

 

Spring框架来接管这两件事，就是实现了IoC思想，Spring是实现IoC思想的容器

控制反转有一些具体实现，比如***\*依赖注入（DI）\****

DI要拆开看

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FA0.tmp.jpg) 

 

DI解决的最主要问题时将组件的创建+配置与组件的使用分离，并无需管理组件的释放（由IoC容器负责管理组件的生命周期）。

 

 

需要告诉容器如何创建组件，以及各组件的依赖关系。一种最简单的配置是通过XML文件来实现

<beans>
  <bean id="dataSource" class="HikariDataSource">
    <property name="dataSource" ref="dataSource"/>
  </bean>
</beans>

在Spring的IoC容器中一个组件就是配置一个Bean。

如果注入的是boolean、int、String这样的数据类型，则通过value注入

<bean id="dataSource" class="com.xxx.HikariDataSource">

  <property name="jdbcUrl" value="jdbc:mysql://localhost:3306/test" />

  <property name="username" value="root" />

<property name="maximumPoolSize" value="10" />

</bean>

 

只不过Spring容器是通过读取XML文件后使用反射完成的。

 

告知后，创建一个Spring的IoC容器实例，然后加载配置文件，让Spring容器为我们创建并装配好配置文件中指定的所有Bean，代码：

ApplicationContext context = new ClassPathXmlApplicationContext("application.xml");

 

 

 

 

 

注入的方式：	set注入，构造方法注入		它们就是set方法赋值，构造方法赋值

Spring的IoC容器同时支持属性注入和构造方法注入，并允许混合使用。

Spring的IoC容器是一个高度可扩展的无侵入容器。

侵入还是无侵入：是否依赖其它项

 

 

 

 

（Spring）Spring Framework 是一个 Java 应用程序开源框架，旨在提供***\*高效且可扩展的开发环境\*******\*，\*******\*解决应用开发复杂性\****。

它是轻量级的，IoC和面向切面（AOP）的容器框架。

支持各种如 Android 和 iOS的移动应用开发技术。

为确保高效开发，提供了对事务管理、对象/关系映射、JavaBeans、JDBC、JMS 和其他技术的支持。

使用 POJO 进行容器配置。

↓

***\*POJO以及容器配置\****

使用 POJO 进行容器配置是一种 Java 开发中常见的配置方式，尤其在依赖注入框架（如 Spring 框架）中广泛应用。

POJO 是只包含了私有成员变量、构造函数和访问器方法（getter 和 setter）的 Java 类(初学java见到的那种类)，它不依赖于特定的框架接口或类库（除了 Java 标准库），没有继承特定的父类，也没有实现特定的接口（除非是 Java 标准接口，如Serializable等）

 

例如，一个简单的POJO类：

 

public class User {

  private String name;

  private int age;

 

  public User(String name, int age) {

​    this.name = name;

​    this.age = age;

  }

 

  public String getName() {

​    return name;

  }

 

  public int getAge() {

​    return age;

  }

}

 

POJO 可以在不同的 Java 项目和环境中使用，具有良好的通用性。

POJO 类的功能可以独立测试，不需要启动整个应用服务器或复杂的运行时环境，便于进行单元测试。

 

***\*容器配置中的应用\****

在 Java 企业级应用开发中，经常使用容器（如 Spring 容器）来管理对象的生命周期、依赖关系等。

使用 POJO 进行容器配置意味着通过 它 和配置文件（XML或 基于 Java 的配置类）告诉容器如何创建、管理和组装这些 POJO 对象。

 

例如，在 Spring 框架中，可以通过 XML 配置文件 定义一个 POJO 对象作为一个 Spring 管理的 bean，并配置其属性和依赖关系：

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FA1.tmp.jpg) 

这段配置告诉 Spring 容器创建一个User类的实例，传入构造函数参数"John"和30，并将这个实例命名为user，可以在其他需要使用User对象的地方通过user这个名称来获取该实例。

 

如果User类依赖于其他 POJO 类，也可以在配置文件中进行依赖注入的配置，如：

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FA2.tmp.jpg) 

这里面UserService类有一个User类型的成员变量

通过上述配置，Spring 容器会将之前创建的user实例注入到UserService实例的user成员变量中。

 

 

通过容器配置 POJO，使得对象之间的依赖关系由容器管理，降低代码间耦合度，提高代码的可维护性和可扩展性。

就像上面的例子，UserService类依赖User类，当User类的实现发生变化时，只需要在容器配置中进行修改，而不需要修改UserService类的代码。

把对象的创建、管理和组装等工作交给容器。减少了开发者在这方面的工作量，提高了开发效率。

 

 

***\*上面是Spring重要意义的简单介绍\****

 

 

Spring是Spring Framework 的简称，但Spring一般指Spring 全家桶

## Spring 全家桶

[Spring Framework](https://spring.p2hp.com/projects/spring-framework.html)

 

[【Spring】详解Spring全家桶 - 易水蜗牛 - 博客园](https://www.cnblogs.com/ncwoniu/p/11498460.html)

 

Spring框架自2002年诞生以来一直备受开发者青睐，它包括SpringMVC、SpringBoot、Spring Cloud、Spring Cloud Dataflow等解决方案。有人亲切的称之为：Spring 全家桶。

 

 



▌1.spring framework

包括了ioc依赖注入，Context上下文、bean管理、springmvc等众多功能模块，其它spring项目依赖它。

 

▌2.spring boot

简化Spring应用和服务的创建、开发、部署，简化了配置文件，使用嵌入式web服务器（内置了 Tomcat或其他可选的 Web 服务器，如 Jetty 等），含有诸多开箱即用的微服务功能，可以和spring cloud联合部署。

Spring Boot 应用程序在启动时会启动内置的 Tomcat（或其他选择的 Web 服务器），由其来处理外部的 HTTP 请求。

 

 

Spring Boot的核心思想是约定大于配置，应用只需要很少的配置即可，简化了应用开发模式。

 

▌3.Spring Data

数据访问及操作的工具集，封装了jdbc、Redis、MongoDB等多种数据源的操作能力。

 

▌4.Spring Cloud

是一套完整的微服务解决方案，是一系列不同功能的微服务框架的集合。Spring Cloud基于Spring Boot，简化了分布式系统的开发，集成了服务发现、配置管理、消息总线、负载均衡、断路器、数据监控等各种服务治理能力。比如sleuth提供了全链路追踪能力，Netflix套件提供了hystrix熔断器、zuul网关等众多的治理组件。config组件提供了动态配置能力，bus组件支持使用RabbitMQ、kafka、Activemq等消息队列，实现分布式服务之间的事件通信。

 

▌5. Spring Security

主要用于快速构建安全的应用程序和服务，在Spring Boot和Spring Security OAuth2的基础上，可以快速实现常见安全模型，如单点登录，令牌中继和令牌交换。你可以了解一下oauth2授权机制和jwt认证方式。oauth2是一种授权机制，规定了完备的授权、认证流程。JWT全称是JSON Web Token，是一种把认证信息包含在token中的认证实现，oauth2授权机制中就可以应用jwt来作为认证的具体实现方法。

 

 

 

 

 

## Spring八大模块

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FA3.tmp.jpg) 

IoC是核心，AOP底层也依赖它，其余均依赖它俩

SpringWebMVC是Spring5后出现的，它是Spring内置的框架

SpringWeb可以用于和其它东西组成

 

 

## Spring特点

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FA4.tmp.jpg) 

非侵入式就是不依赖其它东西

实例化对象在这里被称为bean

 

 

## Spring框架包含的内容

以spring-5.3.9-dist.zip为例

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FA5.tmp.jpg) 

↓

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FA6.tmp.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FA7.tmp.jpg) 

 

 

| JAR文件                          | 描述                                                         |
| -------------------------------- | ------------------------------------------------------------ |
| spring-aop-5.3.9.jar             | 这个jar 文件包含在应用中使用Spring 的AOP 特性时所需的类      |
| spring-aspects-5.3.9.jar         | 提供对AspectJ的支持，以便可以方便的将面向切面的功能集成进IDE中 |
| spring-beans-5.3.9.jar           | 这个jar 文件是所有应用都要用到的，它包含访问配置文件、创建和管理bean 以及进行Inversion ofControl / Dependency Injection（IoC/DI）操作相关的所有类。如果应用只需基本的IoC/DI 支持，引入spring-core.jar 及spring-beans.jar 文件就可以了。 |
| spring-context-5.3.9.jar         | 这个jar 文件为Spring 核心提供了大量扩展。可以找到使用Spring ApplicationContext特性时所需的全部类，JDNI 所需的全部类，instrumentation组件以及校验Validation 方面的相关类。 |
| spring-context-indexer-5.3.9.jar | 虽然类路径扫描非常快，但是Spring内部存在大量的类，添加此依赖，可以通过在编译时创建候选对象的静态列表来提高大型应用程序的启动性能。 |
| spring-context-support-5.3.9.jar | 用来提供Spring上下文的一些扩展模块,例如实现邮件服务、视图解析、缓存、定时任务调度等 |
| spring-core-5.3.9.jar            | Spring 框架基本的核心工具类。Spring 其它组件要都要使用到这个包里的类，是其它组件的基本核心，当然你也可以在自己的应用系统中使用这些工具类。 |
| spring-expression-5.3.9.jar      | Spring表达式语言。                                           |
| spring-instrument-5.3.9.jar      | Spring3.0对服务器的代理接口。                                |
| spring-jcl-5.3.9.jar             | Spring的日志模块。JCL，全称为"Jakarta Commons Logging"，也可称为"Apache Commons Logging"。 |
| spring-jdbc-5.3.9.jar            | Spring对JDBC的支持。                                         |
| spring-jms-5.3.9.jar             | 这个jar包提供了对JMS 1.0.2/1.1的支持类。JMS是Java消息服务。属于JavaEE规范之一。 |
| spring-messaging-5.3.9.jar       | 为集成messaging api和消息协议提供支持                        |
| spring-orm-5.3.9.jar             | Spring集成ORM框架的支持，比如集成hibernate，mybatis等。      |
| spring-oxm-5.3.9.jar             | 为主流O/X Mapping组件提供了统一层抽象和封装，OXM是Object Xml Mapping。对象和XML之间的相互转换。 |
| spring-r2dbc-5.3.9.jar           | Reactive Relational Database Connectivity (关系型数据库的响应式连接) 的缩写。这个jar文件是Spring对r2dbc的支持。 |
| spring-test-5.3.9.jar            | 对Junit等测试框架的简单封装。                                |
| spring-tx-5.3.9.jar              | 为JDBC、Hibernate、JDO、JPA、Beans等提供的一致的声明式和编程式事务管理支持。 |
| spring-web-5.3.9.jar             | Spring集成MVC框架的支持，比如集成Struts等。                  |
| spring-webflux-5.3.9.jar         | WebFlux是 Spring5 添加的新模块，用于 web 的开发，功能和 SpringMVC 类似的，Webflux 使用当前一种比较流程响应式编程出现的框架。 |
| spring-webmvc-5.3.9.jar          | SpringMVC框架的类库                                          |
| spring-websocket-5.3.9.jar       | Spring集成WebSocket框架时使用                                |

 

 

 

这里面的包有的还会依赖里面的其它包

 

 

## 初见项目

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FA8.tmp.jpg) 

新建模块，工程JDK要记得设置，

GroupID就是这个模块是哪些人做的，如com.etoak

 

 

***\*配置文件（配置是名词不是动词）\****

***\*配置文件作用\****

 

***\*参数配置作用\****

 

应用程序参数设定：配置文件用于设定应用程序运行所需的各种参数。例如，在一个 Web 应用中，通过配置文件可以指定服务器端口号，如在application.yml文件中设置server:port:8080，确定应用监听的端口。对于数据库连接，配置文件可以详细说明数据库的类型（如 MySQL、Oracle 等）、连接地址、用户名、密码等信息，像在application - context.xml（Spring 框架）里配置数据源的相关参数，使得应用能够正确连接数据库进行数据操作。

功能模块参数调整：对于应用内部的不同功能模块，配置文件可以调整其特定参数。以日志功能为例，在log4j.xml或者logback - spring.xml（根据使用的日志框架）文件中，可以设置日志的输出级别（DEBUG、INFO、WARN、ERROR）、输出格式和输出目的地（控制台、文件或者远程日志服务器）。这样开发者可以根据应用的运行阶段（开发阶段可能需要更多 DEBUG 信息，生产阶段则主要关注 ERROR 等关键信息）灵活调整日志记录的行为。

 

***\*环境适配作用\****

 

开发、测试、生产环境区分：配置文件能够方便地实现不同环境下的参数配置。在开发环境中，可能会连接到本地的测试数据库，并且启用详细的调试信息；而在生产环境，会连接到真实的生产数据库，并且关闭不必要的调试信息以提高性能和安全性。通过使用不同的配置文件（如application - dev.yml、application - test.yml、application - prod.yml）或者在同一个配置文件中使用不同的配置节来区分不同环境的参数。

 

跨平台适配：有些应用需要在不同的操作系统或者硬件平台上运行。配置文件可以帮助调整与平台相关的参数。例如，文件路径的配置在 Windows 和 Linux 系统下可能有所不同，通过配置文件可以根据不同的操作系统来设置正确的文件路径格式和存储位置，确保应用在不同平台上能够正确读取和写入文件。

 

***\*组件集成与协调作用\****

框架和库集成：在一个基于多种框架和库的应用中，配置文件起到了集成和协调这些组件的作用。例如，在一个使用 Spring、Hibernate 和 MyBatis 的 Java 应用中，pom.xml（Maven 项目管理）文件配置了这些框架和库的依赖关系，确保正确的版本被引入项目；而application - context.xml（Spring 框架）文件则配置了如何将 Hibernate 或 MyBatis 的相关组件（如数据源、会话工厂、映射器等）集成到 Spring 容器中，通过配置 Bean 的方式实现不同组件之间的协作，使得数据访问层（通过 Hibernate 或 MyBatis）能够与业务逻辑层（通过 Spring 管理的服务 Bean）有效协同工作。

外部服务集成：当应用需要与外部服务（如消息队列、缓存系统、第三方 API 等）集成时，配置文件用于配置这些外部服务的连接参数和相关行为。例如，在集成 Redis 缓存时，配置文件可以设置 Redis 服务器的地址、端口、密码（如果有）以及缓存过期时间等参数，使得应用能够正确地与 Redis 缓存进行数据交互，提高应用的性能和响应速度。

 

***\*常见配置文件类型\****

 

XML 文件

特点：具有丰富的标签结构，可以表示复杂的层次关系和嵌套数据。标签可以有属性，用于更详细的配置。语法相对严格，需要正确的开闭标签。

应用场景：在 Java 企业级开发中广泛应用，如 Spring 框架的配置文件（application - context.xml、spring - mvc.xml等）用于配置 Bean、事务管理、MVC 组件等；也用于配置 Web 服务（如web.xml用于传统 Java Web 应用的部署描述符）。还用于一些其他框架的配置，如 Hibernate 的hibernate.cfg.xml用于配置数据库映射等。

YAML / YML 文件

特点：格式简洁，通过缩进表示层次结构，使用键 - 值对来配置参数。易读性强，尤其在配置大量参数时，相较于 XML 更加清晰明了。

应用场景：在现代 Web 开发和微服务架构中非常流行，如 Spring Boot 项目的application.yml用于配置服务器端口、数据库连接、缓存设置等各种应用参数。适用于配置复杂的多层级应用系统，能有效减少配置文件的篇幅。

JSON 文件

特点：基于 JavaScript 对象表示法，格式简单，也是键 - 值对形式。数据结构清晰，易于与 JavaScript 集成，在数据交换和配置方面都有应用。

应用场景：主要用于 Web 开发中的前后端数据交互，如配置 Ajax 请求的参数、前端框架（如 React、Vue.js）的配置文件等。也可作为配置文件用于一些 JavaScript 应用程序或者需要与 Web 服务紧密结合的场景。

INI 文件

特点：具有简单的节和键 - 值对结构，通过方括号区分不同的节。语法简单，易于理解和编辑。

应用场景：在传统软件和系统配置中较为常见，特别是在 Windows 平台的应用程序配置中。适用于配置简单的参数，如一些工具软件的基本设置、数据库连接的简单配置等。

Properties 文件

特点：以简单的键 - 值对形式存在，每行一个配置项，用等号连接。格式简单，是 Java 应用程序早期常用的配置文件格式。

应用场景：主要用于 Java 应用程序配置简单的参数，如配置日志级别、基本的数据库连接参数等。在一些对配置文件格式要求不高、配置内容相对简单的 Java 应用场景中仍有使用。

 

总结对比

从格式复杂度来看，XML 文件的语法结构最复杂，能表示复杂的关系但阅读和编写相对麻烦；YAML 和 JSON 在表示复杂数据结构时也很有效，且格式更简洁；INI 和 Properties 文件格式最为简单，适用于简单的配置场景。

在应用场景方面，XML 在传统 Java 企业级开发和框架配置中占据重要地位；YAML 在现代 Web 开发和微服务中使用广泛；JSON 主要用于 Web 数据交互和部分 JavaScript 应用配置；INI 在传统软件配置中有一定应用；Properties 主要用于简单的 Java 应用配置。

 

 

***\*Spring框架中配置文件\****

 

功能相关命名（Spring 配置文件）：Spring 配置文件通常会根据其功能来命名。例如，application - context.xml用于整个应用的上下文配置，spring - mvc.xml用于 Spring MVC 相关配置，spring - security.xml用于 Spring 安全相关配置。这种命名方式有助于开发者快速理解文件的主要用途。

工具或框架相关命名（其他配置文件）：对于非 Spring 相关的配置文件，如日志配置文件log4j.xml，其命名是根据所使用的工具或者框架来命名的。还有像hibernate.cfg.xml用于 Hibernate 框架的配置，通过文件名就能大致知道它是用于配置哪个工具或者框架的。

pom.xml（Project Object Model）是 Maven 项目的核心配置文件。它在整个项目构建过程中起到了关键的作用，就像是项目的 “总控室”，管理着项目的方方面面。Maven 通过读取pom.xml文件中的配置信息来构建项目，包括获取依赖项、执行插件、确定项目打包方式等众多操作。

对于每个依赖项，pom.xml会指定其groupId（通常是组织或公司的标识）、artifactId（库的名称）和version（版本号）

 

***\*常见项目管理和构建工具\****

Maven

Gradle

 

***\*构建工具和配置文件关系\****

 

Maven 与配置文件（pom.xml）的关系

 

核心配置文件：pom.xml是 Maven 项目的核心配置文件，Maven 的整个构建过程和依赖管理完全依赖于这个文件中的配置。它就像是一个项目构建和依赖的 “蓝图”，Maven 会读取pom.xml文件中的信息来执行相应的操作。

构建过程控制：在构建方面，pom.xml定义了项目的基本信息，如项目的打包方式（<packaging>元素，如jar、war等），主类（用于可执行 JAR），以及构建过程中需要使用的插件（<plugin>元素）及其配置参数。例如，通过配置maven - compiler - plugin来指定 Java 编译器的版本，Maven 在执行构建任务时会根据这个配置进行代码编译。

依赖管理中心：对于依赖管理，pom.xml是管理项目依赖的关键。开发者在文件中使用<dependency>元素声明项目所需要的外部库，包括库的坐标（groupId、artifactId、version）。Maven 会根据这些信息从中央仓库或其他指定仓库中获取依赖，并处理依赖冲突。例如，如果两个不同的依赖库都依赖于同一个库的不同版本，Maven 会根据pom.xml中的配置规则（如版本范围、依赖的优先级等）来确定最终使用的版本。

 

Gradle 与配置文件（build.gradle）的关系

 

构建脚本文件：build.gradle是 Gradle 的构建脚本文件，它采用 Groovy 或 Kotlin 语言编写。与 Maven 的pom.xml的固定格式不同，build.gradle更像是一个可编程的构建脚本，通过代码逻辑来定义项目的构建过程和依赖管理。

灵活构建定义：在构建方面，build.gradle可以通过编写自定义的任务（Task）来灵活地定义构建过程。例如，可以定义一个任务来生成项目文档，或者根据不同的条件执行不同的构建路径。它还可以配置项目的属性，如项目版本、源文件目录等，这些属性会影响构建过程。

依赖管理方式：在依赖管理上，build.gradle使用类似于 Maven 的语法来声明依赖，但更加灵活。可以通过代码块来定义不同类型的依赖（如implementation、testImplementation等），并且可以动态地添加或修改依赖。例如，可以根据项目的构建变体（如开发版、测试版、生产版）来添加不同的依赖，或者根据环境变量来调整依赖版本。

 

总结关系

这些工具都依赖特定的配置文件来进行项目构建和依赖管理。Maven 的pom.xml和 Gradle 的build.gradle在功能上比较相似，都能够自动处理构建过程中的很多环节并且管理依赖，但它们的语法和灵活性有所不同。Ant 的build.xml则更侧重于手动定义构建任务，对开发者的操作要求更高，并且缺乏自动的依赖管理功能。配置文件是这些工具实现项目构建自动化和依赖管理规范化的关键载体。

 

 

 

***\*Maven与XML详解\****

<packaging>元素

用于定义项目的打包方式。常见的打包方式有jar、war、ear等。

值为jar时，表示这个项目最终会被打包成一个 Java Archive（JAR）文件。JAR 文件主要用于打包 Java 类、资源文件等，适用于构建 Java 库或者简单的可执行 Java 应用程序。

如果是一个 Web 应用，通常会使用war（Web Archive）打包方式，其中包含 Web 应用的所有资源，如 HTML、CSS、JavaScript 文件以及 Servlet 和 JSP 等。

 

<properties>元素

用于定义项目中的属性。这些属性可以在整个pom.xml文件中被引用，用于统一管理项目中的版本号、路径等信息，提高项目的可维护性。

如java.version ， spring.version，这通常用于管理项目中 Spring 框架相关依赖的版本。当在<dependencies>部分添加 Spring 相关的依赖时，可以引用这个属性来确保所有 Spring 组件使用相同的版本。

<dependency>元素（在<dependencies>内部）

含义：<dependencies>元素是一个容器，用于列出项目所依赖的其他库或模块。而<dependency>元素则是具体描述每一个依赖项的配置。一个<dependency>元素通常包含了依赖的坐标信息，如groupId、artifactId和version，这些信息用于 Maven 在仓库中查找和下载正确的依赖。

 

***\*依赖引入+常用依赖\****

依赖引入后要刷新

spring context依赖 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FA9.tmp.jpg) 

注意：打包方式jar。

当加入spring context的依赖之后，会关联引入其他依赖：

spring aop：面向切面编程

spring beans：IoC核心

spring core：spring的核心工具包

spring jcl：spring的日志包

spring expression：spring表达式

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FAA.tmp.jpg)	

这些都是spring基础依赖

 

//单元测试依赖//没有就从远程仓库调用

<!--junit-->

​    <dependency>

​      <groupId>junit</groupId>

​      <artifactId>junit</artifactId>

​      <version>4.13.2</version>

​      <scope>test</scope>

​    </dependency>

 

//在新建工程师选择jdk版本才会有这个，否则Maven不会自动生成

<properties>

​    <maven.compiler.source>17</maven.compiler.source>

​    <maven.compiler.target>17</maven.compiler.target>

</properties>

 

 

上面是CI的配置文件

***\*IoC配置\****

Spring的配置文件（如.xml）写在resources文件下（放这儿也就相当于放在类根路径下 ）

 

<bean id="" class="" />

每个<bean ...>都有一个不能重复的id标识，相当于Bean（实例化对象）的唯一ID；

class填写类的全路径，全限定类名（带包名的类名）

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FAB.tmp.jpg) 

 

 

Spring底层默认以反射机制调用无参构造方法实例化对象

如果定义了有参构造方法，就无法实例化

对象被存储在一个Map中

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FAC.tmp.jpg)	

 

可指定多个配置文件

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FAD.tmp.jpg) 

配置文件来自其它类，就用路径方是引导

 

当使用Bean时，要先获取Spring容器对象（下面也包含容器对象ApplicationContext的解释）：

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FAE.tmp.jpg) 

 

 

***\*一些使用细节\****

官方类也能当Bean用（注意无参构造方法去）

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FAF.tmp.jpg) 

 

 

getBean（）返回Object类型，用第二参数强转为指定类型

 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FB0.tmp.jpg) 

 

从其它地方获取xml配置文件

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FB1.tmp.jpg) 

 

 

BeanFactory

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FB2.tmp.jpg) 

一般用子类，因为子类更丰富

 

 

Bean的ID不存在，get他会报错而非返回null

 

 

Bean对象的创建时间是在解析xml文件后，而不是getBean的时候创建

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FB3.tmp.jpg) 

 

 

 

Spring集成的日志框架

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FB4.tmp.jpg) 

 

日志需要启动：

pom.xml写入对它的依赖

在类的根路径下提供log4j2.xml配置文件（文件名固定为：log4j2.xml，文件必须放到类根路径下。）

 

 

 

使用日志框架

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FB5.tmp.jpg) 

 

日志框架可以更精细，有目的的DEBUG

 

 

***\*实现Bean的依赖\****

通过set方法和构造方法

在xml（不是pom）中，通过<property name="..." ref="..." />注入另一个Bean；

 

***\*通过set方法\****

<bean id="dataSource" class="HikariDataSource"></bean>

<bean id="bookService" class="BookService">

  <property name="dataSourceYa" ***\*ref\****="dataSource" />

</bean>

通过 “ref” 属性引用了 BeanID 为 “dataSource” 的 bean（即HikariDataSource实例），并将其注入到BookService实例中的名为 “setdataSourceYa” 的set方法中（BookService的set方法是setdataSourceYa，那name这里就写不带set的dataSourceYa）。这样就建立了BookService与HikariDataSource之间的依赖关系，实现了依赖注入。

//ref是引用

通过<bean>标签的属性和子元素，可以配置对象之间的依赖关系，实现依赖注入（Dependency Injection）。这使得对象的创建和组装更加灵活和可维护。

 

 

 

***\*通过构造方法\****

根据BeanID引入

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FB6.tmp.jpg) 

ref是要引入的Bean的ID，index是它作为第几个参数，必须严格保证参数顺序正确

根据参数名引入

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FB7.tmp.jpg) 

 

根据类型，自动匹配//可读性差劲

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FB8.tmp.jpg) 

 

***\*内部、外部Bean方式->引用外面的Bean\****

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FB9.tmp.jpg) 

 

外部Bean就是先定义/声明它，再使用

内部Bean就是ref的部分换成定义Bean

 

上面都是注入引用数据类型，下面是注入简单数据类型（是简单数据类型，不是基本数据类型）

基本数据类型在BeanUtils的isSimpleValueType方法中

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FBA.tmp.jpg) 

 

 

简单数据类型用value

public class asd {

  private String id;
  private String name;
  private String password;


  public void setId(String id) {
    this.id = id;
  }
  public void setName(String name) {
    this.name = name;
  }
  public void setPassword(String password) {
    this.password = password;
  }

 


  public void pr(){
    System.**out**.println(name);
  }

}

 

 

<bean id="asdBean" class="com.example.demo.dao.asd">
  <property name="id" value="18"></property>
  <property name="name" value="asdasd"></property>
  <property name="password" value="123456"></property>
</bean>

 

 

 

 

Bean的顺序不重要，Spring根据依赖关系会自动正确初始化。

 

context.getBean(UserService.class);

可以通过Bean的ID得到它，但基本是通过 类

 

 

Spring还提供另一种IoC容器叫BeanFactory，使用方式和ApplicationContext类似：

BeanFactory factory = new XmlBeanFactory(new ClassPathResource("application.xml"));MailService mailService = factory.getBean(MailService.class);

BeanFactory和ApplicationContext的区别在于，BeanFactory的实现是按需创建，即第一次获取Bean时才创建这个Bean，而ApplicationContext会一次性创建所有的Bean。实际上，ApplicationContext接口是从BeanFactory接口继承而来的，并且，ApplicationContext提供了一些额外的功能，包括国际化支持、事件和通知机制等。通常情况下，我们总是使用ApplicationContext，很少会考虑使用BeanFactory。

 

 

 

 

使用spring管理数据源

数据源可能有各种类型，如sql、oracle、为了一劳永逸

把它做成Bean给spring容器管理

就是传递必要的driver、url、name、password信息

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FBB.tmp.jpg) 

 

 

***\*级联属性注入\****

本来一个Bean的值应当在它自己的Bean中实现

如果在其它Bean中property它并在此赋值，就是级联属性注入

级联属性注入必须提供在property它的Bean类中提供get方法，毕竟给属性赋值，需要提供属性

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FCC.tmp.jpg) 

先得到Bean再级联赋值，不能改变顺序

 

 

注入数组

注入简单类型

<bean id="arrayTestBean" class="com.example.demo.bean.arrayTest">    <property name="hobbies">        <array>            <value>"1"</value>            <value>"2"</value>            <value>"3"</value>            <value>"4"</value>        </array>    </property></bean>

注入引用类型

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FCD.tmp.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FCE.tmp.jpg) 

先定义Bean，然后ref注入

 

 

 

 

 

 

 

 

使用XML配置的优点是所有的Bean都能一目了然地列出来，并通过配置注入能直观地看到每个Bean的依赖。它的缺点是写起来非常繁琐，每增加一个组件，就必须把新的Bean配置到XML中。

 

更简单的方法，使用Annotation配置，可以完全不需要XML，让Spring自动扫描Bean并组装它们。

@Component		组件

在 Spring 框架中，@Component注解用于将一个普通的 Java 类标记为 Spring 管理的组件（bean）。

当使用@Component注解标记一个类时，可以为这个组件指定一个名称，如果不指定名称，Spring 会默认使用类名首字母小写的形式作为这个组件的名称。指定名称: @Component("customMailServiceName")

 

 

 

@Autowired		自动连线

把指定类型的Bean注入到注释的字段中。可以写在set()方法、字段、构造方法中

@Autowired(required = false)

找到就注入，找不到就忽略。

默认true

没这个参数就抛出NoSuchBeanDefinitionException异常。

 

 

@Configuration

//配置（n）这里是配置类的意思

除了main()方法外，AppConfig标注了@Configuration，表示它是一个配置类，因为我们创建ApplicationContext时：ApplicationContext context = new AnnotationConfigApplicationContext(AppConfig.class);

使用的实现类是AnnotationConfigApplicationContext，必须传入一个标注了@Configuration的类名。

//Annotation宣布		Application应用

 

@ComponentScan

//组件扫描

告诉容器，自动搜索当前类所在的包以及子包，把所有标注为@Component的Bean自动创建出来，并根据@Autowired进行装配。

 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FCF.tmp.jpg) 

ApplicationContext context = new AnnotationConfigApplicationContext(AppConfig.class);

应用程序上下文	=	宣布配置应用程序上下文  	

 

***\*@Scope\****

指定 Bean 的生命周期和实例化方式。它决定了在 Spring 容器中一个 Bean 是如何被创建、共享和销毁的。

***\*默认\**** ***\*单例作用域（\*******\*“\*******\*Singleton\*******\*”\*******\*）\****

使用@Component注解标记的类 单例Bean实例在容器初始化后创建，容器关闭前销毁。

在容器运行期间，getBean(Class)获取这个 Bean始终会得到同一个实例。

 

***\*原型作用域（\*******\*“\*******\*Prototype\*******\*”\*******\*）\****

每次通过getBean(Class)方法获取时，容器都会创建一个新的实例。

其生命周期相对较短，只在特定的请求或使用场景中存在。

例：

//Scope是范围

@Component

@Scope(ConfigurableBeanFactory.SCOPE_PROTOTYPE) // @Scope("prototype")

public class MailSession {

  ...

}

 

 

***\*注入lisit\****

流程就是一个接口，几个实现它的类，这些类被@Component，然后主类里，创建一个Collection。（这里用的List）被@Autowired	

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FD0.tmp.jpg) 

@Oreder

//给收来的元素排个序

 

 

***\*@Bean\****

注释在方法上

他和@Component比较

 

@Component基于类

@Bean：

基于方法，就是通过使用方法来定义 bean，该方法的返回值将成为一个由 Spring 容器管理的 bean。

Spring对标记为@Bean的方法***\*只调用一次\****，因此返回的Bean仍然是单例。

第三方库的Bean可以用@Bean

如果一个Bean不在我们自己的package管理之内，例如ZoneId，如何创建它？

答案是我们自己在@Configuration类中编写一个Java方法创建并返回它，

原因是@Component注解一般不能扫描到包外的类（除非你特别配置包扫描路径包含外部类所在的包），但@Bean注解可以用于将包外的类实例作为 Bean 注册到 Spring 容器中。

用了@Bean注解的特性

 

Bean的初始化和销毁

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FD1.tmp.jpg) 

约定成俗的，初始化方法是init（），销毁方法是shutdown（）

分别在这两个方法上加@PostConstruct 和@PreDestory

这俩不加的话 会使代码的结构不够清晰，并且容易忘记进行初始化操作。

 

到目前我对注解的理解是用标签代替操作，增加对业务逻辑的专注

 

 

 

***\*@Component\*******\*基于类，\*******\*（\*******\*其衍生注解（如@Service、@Repository、@Controller等）\*******\*）\****

 

 

 

 

 

 

***\*@Bean("name")\*******\*指定\*******\*Bean\*******\*别名\****

 

***\*@Bean\*******\*
\*******\*@Qualifier("name")指定\*******\*Bean\*******\*别名\****

***\*//qualifier\****	***\*限定符\****

Bean默认名是全小写类名

在 对一种类型需要创建多个Bean创建多个实例 的情况下。例如，同时连接多个数据库，就必须创建多个同类型Bean实例。

这时候 Spring 就搞不清楚该用哪个了，所以会报 NoUniqueBeanDefinitionException 异常，意思就是出现了重复的 Bean 定义，它不知道该给需要 ZoneId 类型的地方注入哪一个具体的实例。

为了让 Spring 能区分开这些同类型的不同 Bean，需要给每个 Bean 添加不同的名字

上面两个方法哪个都行

↓

重名问题解决了，但只是单方面解决问题，注入时也要讲究，如果和以前一样直接注入，又会报错：

NoUniqueBeanDefinitionException: No qualifying bean of type 'java.com.xxx' available: expected single matching bean but found 2

期待找到唯一的xxxx类型Bean，但是找到俩。因此，注入时，要指定Bean的名称

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FD2.tmp.jpg) 

还有一种方法是把其中某个Bean指定为@Primary：

这样在注入的时候，如果没有特别指出要注入哪个 Bean 的名字，Spring 就会默认注入这个标记有 @Primary 的 Bean。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FD3.tmp.jpg) 

 

 

# 大杂烩

 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wps1FD4.tmp.jpg) 

 

 

 

Spring只根据Annotation查找无参数方法，对方法名不作要求。

 

