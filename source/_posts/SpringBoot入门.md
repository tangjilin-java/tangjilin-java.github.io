---
layout: pages
title: SpringBoot入门
date: 2019-10-31 14:50:35
tags: ["Java","SpringBoot"]
categories: ["Java"]
---
## Springboot入门介绍
---

# 一、Spring框架概述

## 什么是Spring

Spring是一个开源框架，Spring是于2003 年兴起的一个轻量级的Java 开发框架，由Rod Johnson 在其著作《Expert One-On-One J2EE Development and Design》。Spring是为了解决企业级应用开发的复杂性而创建的，使用Spring可以让简单的JavaBean实现之前只有EJB才能完成的事情。但是Spring不仅仅局限于服务器端开发，任何Java应用都能在简单性、可测试性和松耦合性等方面从Spring中获益。
<!-- more -->
## Spring是如何简化Java开发的

为了降低Java开发的复杂性，Spring采用了以下4种关键策略：

### 基于POJO的轻量级和最小侵入性编程；

### 通过依赖注入（DI）和面向接口实现松耦合；

### 基于切面（AOP）和惯例进行声明式编程；

### 通过切面和模版减少样式代码；

---
---
# 二、SpringBoot简介

## 什么是SpringBoot

Spring Boot 是所有基于 Spring 开发的项目的起点。Spring Boot 的设计是为了让你尽可能快的跑起来 Spring 应用程序并且尽可能减少你的配置文件。简单来说就是SpringBoot其实不是什么新的框架，它默认配置了很多框架的使用方式，就像maven整合了所有的jar包，spring boot整合了所有的框架（不知道这样比喻是否合适）。

## SpringBoot四个主要特性

### SpringBoot Starter：他将常用的依赖分组进行了整合，将其合并到一个依赖中，这样就可以一次性添加到项目的Maven或Gradle构建中；

### 自动配置：SpringBoot的自动配置特性利用了Spring4对条件化配置的支持，合理地推测应用所需的bean并自动化配置他们；

### 命令行接口：（Command-line-interface, CLI）：SpringBoot的CLI发挥了Groovy编程语言的优势，并结合自动配置进一步简化Spring应用的开发；

### Actuatir：它为SpringBoot应用的所有特性构建一个小型的应用程序。但首先，我们快速了解每项特性，更好的体验他们如何简化Spring编程模型。

## SpringBoot开发的具体好处

回顾我们之前的 SSM 项目，搭建过程还是比较繁琐的，需要：

### 配置web.xml，加载spring和spring mvc

### 配置数据库连接、配置spring事务

### 配置加载配置文件的读取，开启注解


#### 配置完成之后部署tomcat 调试

#### 而使用 Spring Boot 来开发项目则只需要非常少的几个配置就可以搭建起来一个 Web 项目，并且利用 IDEA 可以自动生成生成，这简直是太爽了...
---

---
# 三、使用IDEA快速搭建SpringBoot项目

## file->new project 在弹出的窗口选择Spring Initializr

## 修改项目信息

## 选择版本及项目需要的依赖

## 最终目录结构

 

项目结构还是看上去挺清爽的，少了很多配置文件，我们来了解一下默认生成的有什么：

    EurekaServerApplication： 一个带有 main() 方法的类，用于启动应用程序
    EurekaServerApplicationTests：一个空的 Junit 测试了，它加载了一个使用 Spring Boot 字典配置功能的 Spring 应用程序上下文
    application.properties：一个空的 properties 文件，可以根据需要添加配置属性
    pom.xml： Maven 构建说明文件
---  
 
---
# 四、项目简单介绍及helloworld编写

## 写一个helloWorld接口
```
    @RestController
    @RequestMapping("/")
    public class HelloWorldController {
        @RequestMapping("hello")
        public String index() {
            return "Hello World";
        }
    }

@RestController 注解： 该注解是 @Controller 和 @ResponseBody 注解的合体版
```
 

## 单元测试
```
    @RunWith(SpringRunner.class)
    @SpringBootTest
    public class ServiceAuthApplicationTests {
       private MockMvc mvc;
       @Before
       public void setUp() {
          mvc = MockMvcBuilders.standaloneSetup(new HelloController()).build();
       }
       @Test
       public void contextLoads() throws Exception {
                    mvc.perform(MockMvcRequestBuilders.get("/hello").accept(
     
            MediaType.APPLICATION_JSON))
                .andExpect(MockMvcResultMatchers.status().isOk())
                .andDo(MockMvcResultHandlers.print())
                .andReturn();
       }
    }
```
 

## pom文件介绍
```
    <?xml version="1.0" encoding="UTF-8"?>
    <project xmlns="http://maven.apache.org/POM/4.0.0"
             xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
             xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
        <modelVersion>4.0.0</modelVersion>
     
     
        <groupId>com.test</groupId>
        <artifactId>springboot</artifactId>
        <version>1.0-SNAPSHOT</version>
        <packaging>pom</packaging>
     
     
     

        <name>spring-cloud-demo</name>
     
        <description>Demo project for Spring Boot</description>
     
        <parent>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-parent</artifactId>
            <version>1.5.18.BUILD-SNAPSHOT</version>
            <relativePath/> <!-- lookup parent from repository -->
        </parent>
     
        <properties>
            <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
            <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
            <java.version>1.8</java.version>
        </properties>
     
        <build>
            <plugins>
                <plugin>
                    <groupId>org.springframework.boot</groupId>
                    <artifactId>spring-boot-maven-plugin</artifactId>
                </plugin>
            </plugins>
        </build>
     
        <repositories>
            <repository>
                <id>spring-snapshots</id>
                <name>Spring Snapshots</name>
                <url>https://repo.spring.io/snapshot</url>
                <snapshots>
                    <enabled>true</enabled>
                </snapshots>
            </repository>
     
            <repository>
                <id>spring-milestones</id>
                <name>Spring Milestones</name>
                <url>https://repo.spring.io/milestone</url>
                <snapshots>
                    <enabled>false</enabled>
                </snapshots>
            </repository>
        </repositories>
     
     
        <pluginRepositories>
     
            <pluginRepository>
                <id>spring-snapshots</id>
                <name>Spring Snapshots</name>
                <url>https://repo.spring.io/snapshot</url>
                <snapshots>
                    <enabled>true</enabled>
                </snapshots>
            </pluginRepository>
     
            <pluginRepository>
                <id>spring-milestones</id>
                <name>Spring Milestones</name>
                <url>https://repo.spring.io/milestone</url>
                <snapshots>
                    <enabled>false</enabled>
                </snapshots>
            </pluginRepository>
        </pluginRepositories>
     
    </project>
     
```
这个标签是在配置 Spring Boot 的父级依赖

有了这个，当前的项目才是 Spring Boot 项目，spring-boot-starter-parent 是一个特殊的 starter ，它用来提供相关的 Maven 默认依赖，使用它之后，常用的包依赖就可以省去 version 标签。

 

## 启动类介绍（*Application）
```
    @SpringBootApplication
    public class EurekaServerApplication {
        public static void main(String[] args) {
            SpringApplication.run(EurekaServerApplication.class, args);
        }
    }

@SpringBootApplication是springBoot的核心注解注解： 该注解是@Configuration、@EnableAutoConfiguration、@ComponentScan 注解的合体版
```
 

## properties介绍

springBoot 使用一个全局的配置文件 application.properties 或 application.yml，放置在【src/main/resources】目录下

将 Tomcat 默认端口设置为 9090 ，并将默认的访问路径从 “/” 修改为 “/test” 时，使用 properties 文件