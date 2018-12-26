# java-sample-spring-boot-junior

## 课程介绍

​	第1~8章是spring boot基础。第9~16章是spring boot的高级知识。本次课只讲第1~8章。

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

###### 3-1. 环境配置

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


