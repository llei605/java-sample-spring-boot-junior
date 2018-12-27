# java-sample-spring-boot-junior

## 课程介绍

​	第1至8章是spring boot基础。第9至16章是spring boot的高级知识。本次课只讲第1至8章。

![1545751149795](assets/1545751149795.png)

## 正文

### 一、Spring Boot入门

![1545751263511](assets/1545751263511.png)

​	官网：https://spring.io/

#### 1. SpringBoot简介

* 简化Spring应用开发的一个框架

- 整个Spring技术栈的一个大整合

- J2EE开发的一站式解决方案

![1545752189916](assets/1545752189916.png)

![1545752203969](assets/1545752203969.png)

#### 2. 微服务简介

​	微服务：一种架构风格。

​	一个应用应该是一组小型服务；相互之间可以通过HTTP方式进行互通。

​	每一个功能元素最终都是一个可独立替换和独立升级的软件单元。

```
一个描述微服务的网站：https://martinfowler.com/articles/microservices.html
```

![1545752519996](assets/1545752519996.png)

​	单体应用缺点：有可能一个小小的修改，都会影响到整个系统。

![1545752425792](assets/1545752425792.png)

#### 3. Hello World

​	需求：基于maven创建一个Spring Boot的hello world程序。

##### 3-1. 环境配置

1. JDK： 1.8

2. MAVEN： 3.5.4

   需要设置~/.m2/settings.xml

   1). 在mirrors中设置阿里云镜像

   ```xml
   <mirror>
       <id>alimaven</id>
       <name>aliyun maven</name>
       <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
       <mirrorOf>central</mirrorOf>
   </mirror>
   ```

   2). 在profiles标签中设置maven编译环境

   ```xml
   <!-- 这段设置告诉maven用1.8的jdk来编译 -->
   <profile>
       <id>jdk-1.8</id>
       <activation>
           <actionByDefault>true</actionByDefault>
           <jdk>1.8</jdk>
       </activation>
       <properties>
           <maven.compiler.source>1.8</maven.compiler.source>
           <maven.compiler.target>1.8</maven.compiler.target>
           <maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>
       </properties>
   </profile>
   ```

3. 设置IDEA的maven环境

   ![1545803362977](assets/1545803362977.png)

##### 3-2. 创建spring boot

详情参考： **demo-01-hello**

3-3. 发布spring boot

1. 根据官方文档，创建一个可执行的jar包。需要将下面配置写入pom.xml

   ``` xml
   <build>
       <plugins>
           <plugin>
               <groupId>org.springframework.boot</groupId>
               <artifactId>spring-boot-maven-plugin</artifactId>
           </plugin>
       </plugins>
   </build>
   ```

2. 运行mvn package进行打包

![1545804995204](assets/1545804995204.png)

3. 打包后会在target里面

![1545805035064](assets/1545805035064.png)

4. 通过命令行可以直接启动

![1545805059306](assets/1545805059306.png)

#### 4. pom.xml

##### 4-1. 父项目

![1545874160897](assets/1545874160897.png)

​	SpringBoot的版本仲裁中心；

​	以后我们导入依赖，默认是不需要写版本的。 

##### 4-2. 导入的依赖

![1545874368730](assets/1545874368730.png)

​	spring-boot-starter-xxx：spring boot的场景启动器

#### 5. 主入口类

![1545877852716](assets/1545877852716.png)

​	这是一个组合注解

![1545878046236](assets/1545878046236.png)

##### 5-1. @SpringBootConfiguration

![1545878160140](assets/1545878160140.png)

##### 5-2. @EnableAutoConfiguration

 ![1545878203034](assets/1545878203034.png)

 ![1545879392525](assets/1545879392525.png)

 	![1545879618024](assets/1545879618024.png)

 #### 6. 配置文件

##### 6-1. 简介

 ![1545880506640](assets/1545880506640.png)

 ##### 6-2. YAML配置文件

###### 6-2-1. 基本语法

![1545880774995](assets/1545880774995.png)

###### 6-2-1. 值的写法

![1545882180263](assets/1545882180263.png)

![1545882348791](assets/1545882348791.png)

![1545882463823](assets/1545882463823.png)

##### 6-3. 获取配置文件的值

详细参考： demo-02-yml

##### 6-4. @Value注解和@Configurationproperties注解的比较

![1545887301685](assets/1545887301685.png)

![1545888705946](assets/1545888705946.png)

##### 6-5. @PropertySource和@ImportSource：

**@Configurationproperties是在全局配置文件中获取值**

![1545888903777](assets/1545888903777.png)

**@PropertySource：** 加载指定的配置文件

![1545890675189](assets/1545890675189.png)

**@ImportSource：**

1. 创建helloService.java

   ![1545891037007](assets/1545891037007.png)

2. 创建bean.xml

   ![1545890829132](assets/1545890829132.png)

3. 标志在主配置类上

   ![1545890998931](assets/1545890998931.png)

4. 输出结果

   ![1545890916250](assets/1545890916250.png)

##### 6-6. @Bean

内容看注释

![1545891336979](assets/1545891336979.png)

##### 6-7. 配置文件的占位符

![1545891448766](assets/1545891448766.png)

##### 6-8. profile - 多环境支持

![1545893047513](assets/1545893047513.png)

##### 6-9. 配置文件的加载位置

![1545894257233](assets/1545894257233.png)

##### 6-10. 外部配置文件

![1545894352809](assets/1545894352809.png)

![1545894393606](assets/1545894393606.png)

