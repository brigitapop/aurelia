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
- [From scratch with NPM and JSPM]([aurelia-jspm])
- Webpack, Yeoman, etc

---

# Implementing MVVM with Aurelia

---

Model-View-ViewModel (MVVM) is mostly about trying to achieve good Separation of Concerns

---

###No Separation of Concerns

```
 <div>
   <ul id="workinprogress"></ul> 
  </div> 
  <div> 
     <input id='taskName' type='text'/>           
     <button id='startwork' onclick="$('wp').class('wk')"> WK</button> 
   </div>
  <script type="text/javascript"> 
      $(function(){         
         $('#startwork').click(function(){ var taskNo = 
                           someService.startTask($("#taskName").val());                               
         $('#workinprogress').append('<li><span>Task ' + taskNo + '</span></li>');
         }); 
      }); 
  </script> 
```

---

### Separation of Concerns
View:
```
<template>
  <div> 
    <ul class.bind='listStyle'> 
      <li repeat.for='task of tasks'>${task}</li> 
    </ul> 
 </div> 
 <div> 
    <input type="text" value.bind='taskName'/> 
    <button type='button' click.delegate='startTask()'>Start Task</button> 
 </div> </template>

```

---

### Separation of Concerns
ViewModel

```
import {inject} from 'aurelia-framework';
 @inject(SomeService) 
 export class App { 
   constructor(someService) { 
   this.tasks = []; 
   this.taskName = ''; 
   this.someService = someService; 
   this.listStyle = ''; 
   }  startTask() {
        var taskNo = this.someService.startTask(this.taskName);
        this.tasks.push(`Task ${taskNo}`); 
        this.listStyle = 'working'; 
        } 
```

---

### MVVM Approaches in Aurelia

- Using compose element
- Using Aurelia Routing & Navigation System
- Using Custom Elements 

---

## Using Dependency Injection in Aurelia

---

Dependency Injection is mostly about having loose coupling between dependent components

---
### Dependency Injection in Aurelia
- Done using the @inject(type[,type2,…]) decorator on the class 
- Instance(s) of type(s) is passed to the constructor of the class
---

```
import {SomeService} from 'someService';
import {inject} from 'aurelia-framework';

    @inject(SomeService)
    export class App {
        constructor(someService) {
            this.taskName = '';
            this.someService = someService;
            }
            startTask() {
            var taskNo = this.someService.startTask(this.taskName);
            }
         }
```
---


### Dependency Injection in Aurelia
- Alternate (non-ES2016): use static inject property instead of decorator

---

```
import {SomeService} from 'someService';
import {inject} from 'aurelia-framework';

    export class App {
        static inject = [SomeService];
        constructor(someService) {
            this.taskName = '';
            this.someService = someService;
            }
            startTask() {
            var taskNo =this.someService.startTask(this.taskName);
            }
        }
```

---
### Registering Lifetime

- Singleton –constructed on first inject, same ref passed to other injections
- Transient –new instance constructed on each injection

---
### Globally Registering Dependencies
- Avoid repetitive import declarations 
- Register a dependency globally through your app configure method 

---

## Aurelia Routing Fundamentals
---

### Traditional Web App Navigation
![traditional](https://github.com/brigitapop/aurelia/blob/master/traditional.png?raw=true)

---
### SPA Navigation
![spa](https://github.com/brigitapop/aurelia/blob/master/spa.png?raw=true)

---
### Routing in Aurelia
- Define container for routing with ```<router-view>```
- Implement configureRouter() in ViewModel
- Define modules for routes
---

### Route Configuration

| Route property  |   |
|---              |---|
| route            | Relative path from base URL to activate the route   |
| moduleId         | Name of the module (View/ViewModel pair) to load into the router-view element when route is activate  |

---

### Route Configuration

| Route property  |   |
|---              |---|
| title           | Will be shown in the title bar or tab of browser |
| nav             | Boolean to indicate desire to include route in navigation collection on router for data binding purpose |
| name            | Used to identify the route for route related APIs  |

---
### Routing Parameters
- URL Parameters 
- Query String Parameters

---

### Consuming Routes in ViewModels

- Implement activate(params, routeConfig, navigationInstruction) method 
- Generate URLs with router.generate(routeName, {params}) 
- Programmatically navigate to another route 
    - router.navigate(relativePath) 
    - router.navigateToRoute(routeName, {params}, options)
    
---

## Data Binding Fundamentals

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

---

### Aurelia Binding –The >90% Case

- HTML element property value from ViewModel or Model property value: .bind
```
     <element property.bind='viewModelProperty' ...></element>
```

- Element content or value insertion in expression: string interpolation
```
    <span>${product.description}</span> <img src="/images/uploads/${filename}"/>
```

---

### Aurelia Binding –The >90% Case

- Looping over arrays: repeat.for
``` 
  <nav>
    <ul>
      <li repeat.for="row of router.navigation" class="${row.isActive ? 'active' : ''}">
        <a href.bind="row.href">${row.title}</a>
      </li>
    </ul>
```

---

### Controlling Data Flow

- .two -way
- .one-time
- .one -way

---

### Calling ViewModel Method

- event.delegate - Wires up event handler at document level 
- event.trigger - Wires up event handler on element itself 

---

### Working with Services

---

### Calling HTTP Services

- AKA “AJAX” service calls
- Vital part of any SPA
- Not constrained to use only what Aurelia provides
- Two choices in Aurelia:
    - http-client
    - fetch-client
 
--- 
### Resources

- http://aurelia.io/training.html

---


[aurelia]: <http://aurelia.io>
[quick-start]: <http://aurelia.io/hub.html#/doc/article/aurelia/framework/latest/quick-start/1>
[aurelia-cli]: <http://aurelia.io/hub.html#/doc/article/aurelia/framework/latest/the-aurelia-cli/1>
[aurelia-jspm]:<http://briannoyesblog.azurewebsites.net/2016/05/27/hello-aurelia/>
