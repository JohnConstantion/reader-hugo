---
title: "HttpServletRequest not present"
date: 2024-09-14T12:10:24+06:00
# post thumb
images:
  - "images/blog/blog-4.jpg"
  - "images/blog/blog-1.jpg"
#author
author: "Crucio"
# description
description: "This is meta description"
# Taxonomies
categories: ["microwave","tech"]
tags: ["season","recipe"]
type: "trending" # available type (epic, trending, popular, or regular)
draft: false
---

### Type javax.servlet.http.HttpServletRequest not present 异常
``` java
java.lang.TypeNotPresentException: Type javax.servlet.http.HttpServletRequest not present
	at java.base/sun.reflect.generics.factory.CoreReflectionFactory.makeNamedType(CoreReflectionFactory.java:117) ~[na:na]
	at java.base/sun.reflect.generics.visitor.Reifier.visitClassTypeSignature(Reifier.java:125) ~[na:na]
	at java.base/sun.reflect.generics.tree.ClassTypeSignature.accept(ClassTypeSignature.java:49) ~[na:na]
	at java.base/sun.reflect.generics.visitor.Reifier.reifyTypeArguments(Reifier.java:68) ~[na:na]
	at java.base/sun.reflect.generics.visitor.Reifier.visitClassTypeSignature(Reifier.java:138) ~[na:na]
	at java.base/sun.reflect.generics.tree.ClassTypeSignature.accept(ClassTypeSignature.java:49) ~[na:na]
	at java.base/sun.reflect.generics.repository.ClassRepository.computeSuperInterfaces(ClassRepository.java:117) ~[na:na]
	at java.base/sun.reflect.generics.repository.ClassRepository.getSuperInterfaces(ClassRepository.java:95) ~[na:na]
	at java.base/java.lang.Class.getGenericInterfaces(Class.java:1296) ~[na:na]
	at org.springframework.core.ResolvableType.getInterfaces(ResolvableType.java:517) ~[spring-core-6.1.12.jar:6.1.12]
	at org.springframework.core.ResolvableType.as(ResolvableType.java:465) ~[spring-core-6.1.12.jar:6.1.12]
	at org.springframework.core.ResolvableType.forClass(ResolvableType.java:1093) ~[spring-core-6.1.12.jar:6.1.12]
	at org.springframework.plugin.core.config.PluginRegistriesBeanDefinitionRegistrar.getTargetType(PluginRegistriesBeanDefinitionRegistrar.java:101) ~[spring-plugin-core-2.0.0.RELEASE.jar:2.0.0.RELEASE]
	at org.springframework.plugin.core.config.PluginRegistriesBeanDefinitionRegistrar.registerBeanDefinitions(PluginRegistriesBeanDefinitionRegistrar.java:71) ~[spring-plugin-core-2.0.0.RELEASE.jar:2.0.0.RELEASE]
	at org.springframework.context.annotation.ImportBeanDefinitionRegistrar.registerBeanDefinitions(ImportBeanDefinitionRegistrar.java:86) ~[spring-context-6.1.12.jar:6.1.12]
	at org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader.lambda$loadBeanDefinitionsFromRegistrars$1(ConfigurationClassBeanDefinitionReader.java:376) ~[spring-context-6.1.12.jar:6.1.12]
	at java.base/java.util.LinkedHashMap.forEach(LinkedHashMap.java:986) ~[na:na]
	at org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader.loadBeanDefinitionsFromRegistrars(ConfigurationClassBeanDefinitionReader.java:375) ~[spring-context-6.1.12.jar:6.1.12]
	at org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader.loadBeanDefinitionsForConfigurationClass(ConfigurationClassBeanDefinitionReader.java:148) ~[spring-context-6.1.12.jar:6.1.12]
	at org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader.loadBeanDefinitions(ConfigurationClassBeanDefinitionReader.java:120) ~[spring-context-6.1.12.jar:6.1.12]
	at org.springframework.context.annotation.ConfigurationClassPostProcessor.processConfigBeanDefinitions(ConfigurationClassPostProcessor.java:429) ~[spring-context-6.1.12.jar:6.1.12]
	at org.springframework.context.annotation.ConfigurationClassPostProcessor.postProcessBeanDefinitionRegistry(ConfigurationClassPostProcessor.java:290) ~[spring-context-6.1.12.jar:6.1.12]
	at org.springframework.context.support.PostProcessorRegistrationDelegate.invokeBeanDefinitionRegistryPostProcessors(PostProcessorRegistrationDelegate.java:349) ~[spring-context-6.1.12.jar:6.1.12]
	at org.springframework.context.support.PostProcessorRegistrationDelegate.invokeBeanFactoryPostProcessors(PostProcessorRegistrationDelegate.java:118) ~[spring-context-6.1.12.jar:6.1.12]
	at org.springframework.context.support.AbstractApplicationContext.invokeBeanFactoryPostProcessors(AbstractApplicationContext.java:789) ~[spring-context-6.1.12.jar:6.1.12]
	at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:607) ~[spring-context-6.1.12.jar:6.1.12]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.refresh(ServletWebServerApplicationContext.java:146) ~[spring-boot-3.3.3.jar:3.3.3]
	at org.springframework.boot.SpringApplication.refresh(SpringApplication.java:754) ~[spring-boot-3.3.3.jar:3.3.3]
	at org.springframework.boot.SpringApplication.refreshContext(SpringApplication.java:456) ~[spring-boot-3.3.3.jar:3.3.3]
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:335) ~[spring-boot-3.3.3.jar:3.3.3]
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:1363) ~[spring-boot-3.3.3.jar:3.3.3]
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:1352) ~[spring-boot-3.3.3.jar:3.3.3]
	at org.crucio.oddity.OddityApplication.main(OddityApplication.java:10) ~[classes/:na]
Caused by: java.lang.ClassNotFoundException: javax.servlet.http.HttpServletRequest
	at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641) ~[na:na]
	at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188) ~[na:na]
	at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:526) ~[na:na]
	at java.base/java.lang.Class.forName0(Native Method) ~[na:na]
	at java.base/java.lang.Class.forName(Class.java:534) ~[na:na]
	at java.base/java.lang.Class.forName(Class.java:513) ~[na:na]
	at java.base/sun.reflect.generics.factory.CoreReflectionFactory.makeNamedType(CoreReflectionFactory.java:114) ~[na:na]
	... 32 common frames omitted
```
> 这个错误表明Java编译器在尝试编译一个使用了javax.servlet.http.HttpServletRequest类的Java程序时，找不到这个类。通常这是因为缺少了需要的库或者jar包。
需要查询一下最新添加的功能或者是配置是不是配置异常，导致了程序运行时找不到类，运行异常
