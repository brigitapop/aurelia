# [Aurelia Overview]
## What is Aurelia?
- just javascript (ES2015 & ESNext)
- it's a collection of collaborating libraries
- SPA framework

## Why should I use Aurelia?
- future compatible 
  by relying on standards as much as possible like modern javascript, modern dom and web components technology
- all in one solution, but modular
  takes care of all your needs for building SPA, and you only have to pull in what you need and use
- MIT license
- conventions over configuration
  keeps the code clean & you don't have to struggle with the framework
- rendering performance
- relative small learning curve
- integrates well with other libraries/frameworks
- active community
- enterprise support

---
## Using Dependency Injection in Aurelia

### Agenda
- Dependency Injection Overview 
- Using Dependency Injection in Aurelia 
- Lifetime Management 
- Globally Registering Dependencies

---
Dependency Injection is mostly about having loose coupling between dependent components

---
### Related Patterns
- Dependency Injection (DI)
- Inversion of Control (IoC)
- Service Locator

---
### Dependency Injection in Aurelia
- Done using the @inject(type[,type2,…]) decorator on the class 
- Instance(s) of type(s) is passed to the constructor of the class
 ??code sample
---

### Dependency Injection in Aurelia
- Alternate (non-ES2016): use static inject property instead of decorator
 ?? code sample

---
### Registering Lifetime

Can indicate on class what instance lifetime it should have in container 
- Singleton –constructed on first inject, same ref passed to other injections
- Transient –new instance constructed on each injectio

---
### Globally Registering Dependencies
- Avoid repetitive import declarations 
- Register a dependency globally through your app configure method 

[Aurelia]: <http://aurelia.io>
