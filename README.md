# Spring Data REST + AngularJS example
The intention of this example project is to combine proven technologies with the least extra fuzz into a modern web application;
* static html front-end
* restful back-end
* annotation/programmatic configuration

Originally it was based on the tutorials [Spring Data Angular](http://g00glen00b.be/spring-data-angular/) and [Spring Boot Angular](http://g00glen00b.be/prototyping-spring-boot-angularjs/) by [G00gleN00b](https://github.com/g00glen00b). It combines using the standard REST endpoints of Spring MVC with the not-being-a-spring-boot of the first application but it deviates more in detail in order to further reduce complexity without using spring-boot.

## Front-end

### Twitter Bootstrap
For rapidly creating prototypes of a web application, a UI toolkit or library will become really handy. There are many choices available, and for this example I chose [Twitter Bootstrap](http://getbootstrap.com/) for the visual front-end components

### AngularJS
[AngularJS](https://angularjs.org) is a MVC based framework for web applications, written in JavaScript. It makes it possible to use the Model-View-Controller pattern on the front-end. It also comes with several additional modules. In this example I'm also using **angular-resource**, which is a simple factory-pattern based module for creating REST clients.

## Back-end

### Spring Data JPA
[Spring Data JPA](http://projects.spring.io/spring-data-jpa/) allows you to create repositories for your data without even having to write a lot of code. The only code you need is a simple interface that extends from another interface and then you're done.
With Spring Boot you can even leave the configuration behind for configuring Spring Data JPA, so now it's even easier.

### Spring Web MVC
[Spring Web MVC](http://projects.spring.io/spring-framework/) for creating REST endpoints and using [Jackson Databind](https://github.com/FasterXML/jackson-databind) for streaming from/to JSON. 

## Build
It builds as an standard maven war artifact; in the front-end world build and dependency management is mostly bower, npm or grunt based, in this case there is no need for the including those tools. The front-end dependencies are managed with Maven [Webjars](http://www.webjars.org/) reducing the complexity of the build process. If more is needed the [Front-end Maven plugin](https://github.com/eirslett/frontend-maven-plugin) (invoking the front-end tooling) or [wro4j](http://alexo.github.io/wro4j/) (minimizing; less compiling; etc..) can be used. 

### Build command
```
mvn clean package
```
The result in target/*.war is deployable in an 3.1 container (for example Tomcat8)