# Aurelia Overview

---

## What is Aurelia?
- Just javascript (ES2015 & ESNext)
- It's a collection of collaborating libraries
- SPA framework

---

## Why should I use Aurelia?
- Future compatible 
  by relying on standards as much as possible like modern javascript, modern dom and web components technology
- All in one solution, but modular
  takes care of all your needs for building SPA, and you only have to pull in what you need and use
- MIT license

---
## Why should I use Aurelia?
- Conventions over configuration
  keeps the code clean & you don't have to struggle with the framework
- Rendering performance
- Relative small learning curve
- Integrates well with other libraries/frameworks
- Active community
- Enterprise support

---

## How to setup Aurelia?

- [Quick Start](quick-start)
- [Aurelia CLI](aurelia-cli)
- Webpack, Yeoman , JSPM / System.js

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
## Aurelia Routing Fundamentals
---
### Agenda
- Routing Overview 
- Defining and Navigating with Routes 
- Working with Route Parameter

---
### Traditional Web App Navigation
 ?? image

---
### SPA Navigation
?? image

---
### Routing in Aurelia
- Define container for routing with <router-view>
- Implement configureRouter() in ViewModel
- Define modules for routes
---

### Route Configuration
| Route propert  |   |
|---|---|
| route   | Relative path from base URL to activate the route   |
| moduleId   |   Name of the module (View/ViewModel pair) to load into the                          router-view element when route is activate  |
| title   |  Will be shown in the title bar or tab of browser |
| nav   |  Boolean to indicate desire to include route in navigation collection on router for data binding purpose |
| name   | Used to identify the route for route related APIs  |

### Routing Parameters
- URL Parameters 
- Query String Parameters

### Consuming Routes in ViewModels

- Implement activate(params, routeConfig, navigationInstruction) method 
- Generate URLs with router.generate(routeName, {params}) 
- Programmatically navigate to another route 
    - router.navigate(relativePath) 
    - router.navigateToRoute(routeName, {params}, options)
    
    ## Data Binding Fundamentals
---
### What Is Data Binding All About?

---
### Data Binding Benefits
- Reduces code effort / maintenance Automatic data flow as data changes 
    - No per-property push/pull logic 
    - Natural associations 
- Key enabler for MVVM 
    - Bindings are loosely coupled bond between View and ViewModel

---
### Aurelia Data Binding
- Adaptive data binding 
- Performance optimized 
- Easy to use / simple syntax 
- Flexible 
- Extensible

### Aurelia Adaptive Binding

### Aurelia Binding –The >90% Case

- HTML element property value from ViewModel or Model property value: .bind
```
     <element property.bind='viewModelProperty' ...></element>
```

- Element content or value insertion in expression: string interpolation
```
    <span>${product.description}</span> <img src="/images/uploads/${filename}"/>
```
- Looping over arrays: repeat.for
```
<table>
 <tr repeat.for="customer of customers"> 
     <td>${customer.FirstName}</td>       
     <td>${customer.LastName}</td> 
     <td>${customer.Phone}</td> 
 </tr> 
</table>
```

### Controlling Data Flow

- .two -way
- .one-time
- .one -way


### Calling ViewModel Method

- event.delegate - Wires up event handler at document level 
- event.trigger - Wires up event handler on element itself 

## Data Binding Summary

- Aurelia Data Binding is simple, flexible, extensible, and adaptive 
- .bind, string interpolation ${ }, and repeat.for cover 90+% of your data binding needs 
- .one-way, .two-way, and .one-time binding commands put you in control when needed
- Event bindings let you invoke methods on your ViewModels when things happen in the view

[aurelia]: <http://aurelia.io>
[quick-start]: <http://aurelia.io/hub.html#/doc/article/aurelia/framework/latest/quick-start/1>
[aurelia-cli]: <http://aurelia.io/hub.html#/doc/article/aurelia/framework/latest/the-aurelia-cli/1>
