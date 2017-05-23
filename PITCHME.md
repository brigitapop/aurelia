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
