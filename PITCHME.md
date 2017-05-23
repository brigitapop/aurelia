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
