---
layout: pages
title: SpringBoot六大特性之独立的Spring应用
date: 2019-11-04 13:47:03
tags: ["Java","SpringBoot"]
categories: ["Spring"]
---
# SpringBoot六大特性之独立的Spring应用
# SpringBoot六大特性:
<!-- more -->
>

    Create stand-alone Spring applications

    Embed Tomcat, Jetty or Undertow directly (no need to deploy WAR files)

    Provide opinionated 'starter' dependencies to simplify your build configuration

    Automatically configure Spring and 3rd party libraries whenever possible

    Provide production-ready features such as metrics, health checks and externalized configuration

    Absolutely no code generation and no requirement for XML configuration

## 可以将其逐一理解为：
- 创建独立的Spring应用；
- 直接嵌入Tomcat，Jetty或Undertow等Web容器(不需要部署WAR文件)；
- 提供固化的"starter"依赖，简化构建配置；
- 尽可能自动配置Spring和第三方库；
- 提供运维(Production-Ready)特性，可用于生产的特性，如度量标准、健康状况检查和外部化配置；
- 完全不需要代码生成，也不需要XML配置；

*现在我们先讲讲这六大特性之一的独立的Spring应用*
# 理解独立的Spring应用
## 创建独立的Spring应用作为SpringBoot的首要特性，其中有两层含义思考。
- 首先，为什么要独立的应用？
- 其次，为什么是Spring应用，而非SpringBoot应用？
### 在大多数SpringBoot应用场景中，程序直接或间接地使用SpringApplicationAPI引导应用。其中又结合嵌入式Web容器，对外提供HTTP服务。从应用类型上划分SpringBoot应用包括Web应用和非Web应用。
- 而非Web应用主要应用于服务提供，调度任务，消息处理等场景。
- Web应用类型在SpringBoot1.x中有且仅有Servlet容器实现，包括传统的Servlet和Spring Web MVC。

### 光指定了应用类型还不够，还需要搭配SpringBoot Starter技术，直接或者间接地引入相关的依赖，结合SpringBoot自动装配，再利用SpringBoot和Spring Framework的生命周期，创建并启动嵌入式的Web容器，如：
> Servlet Web 的Maven依赖为org.springframework.boot:spring-boot-starter-web,而Reactive Web则需依赖org.springframework.boot:spring-boot-starter-webflux。换言之，SpringBoot应用无须再像传统的JavaEE应用那样，将应用打包成WAR文件或者EAR文件，并部署到JavaEE容器中运行。不过，SpringBoot也支持传统的Web部署方式，但是这样的部署方式是一种兼容的或者过渡的手段，并非独立的Spring应用。


**总而言之，SpringBoot应用采用嵌入式容器，独立于外部容器，对应用生命周期拥有完全自主的控制，从此改变了"寄人篱下"的境地**
> 不少人存在一个理解上的误区：认为SpringBoot嵌入式Web容器启动时间少于传统的Servlet容器，实际上并没有这样的证据证明这个。而应该将其理解为是一种方便快捷的启动方式，可以提供开发和部署的效率。



