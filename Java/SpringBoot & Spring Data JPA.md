### Mardi, 23 juillet
#### What is spring framework?
- open source framework for building Java application
- simplify complex Java development:
	- dependency injection
	- lose coupling
	- support for JDBC & Hibernate
### Core features of Spring:
- Inversion of Control Container: (IOC)
	- ways to configure & manage Java objects, life cycle of Java objects
	- use dependency injection/dependency lookup to provide reference to object at runtime
- Aspect oriented programming:
	- define separate common tasks/concerns i.e logging, security checking, transaction management
	- into special blocks called aspects
	- then define where & when these aspects get applied to app
- Data Access Framework:
	- JDBC:
		- Java Database Connection
		- opening a connection, create statement(SQL queries), executing SQL queries, process statement, closing statement, closing connection
	- Hibernate:
		- Hibernate implements JPA and JPA is guidelines on making on ORM
	- JPA:
		- ORM: map Java objects to database tables
		- JPA is a specification or a set of guidelines provided by Oracle for implementing ORM in Java
- Spring MVC: 
	- View: representation of data
	- Model: underlying, logical structure of data
	- Controller: take in inputs, coverts to commands for Model and View
### What is a Bean?
- Object: Java objects managed by Spring Framework/Container
- Configuration, instantiation, wiring -> less manual work
- Can be configured with XML, config annotation, Java code
### Lifecycle of a Bean?
- Bean lifecycle is managed by spring container
- Start container -> instantiate beans -> inject beans -> destroy beans -> close containers
### @Configuration 
![[Capture d’écran 2024-07-23 à 22.15.46.png]]

### @Component
- class level annotation that marks class as Spring component
- constructor-dependency injection done with @Atutowired
- @Autowired is optional if there is only 1 constructor
- Hibernate implements JPA and JPA is guidelines on making on ORM
- HAS TO BE managed by Spring Container
- @Repository, @Service, @Controller are `meta-annotation` for @Component
### @Bean Naming
![[Pasted image 20240723233813.png]]

### Dependency Injection
- Constructor Injection
- Field Injection
- Configuration Method/Method injection through method parameters
- Setter Method Injection
### Using @Qualifier
- Multiple Beans of the same type using qualifier to identify
  ![[Pasted image 20240723234550.png]]
### @Primary
- multiple Beans, always use the Bean with the @Primary annotation 

### Avoid Field Injection because testing in isolation is much harder
Should only be used in test classes

![[Pasted image 20240723234942.png]]

![[Pasted image 20240723235045.png]]
### Setter Injection
- not recommended, used to inject optional dependencies
![[Pasted image 20240723235131.png]]
### Bean scoping
- Bean scoping refers to lifecycle, which beans can interact with it
- Types:
	- Singleton: 1 instance of the Bean, everyone requesting this bean will get the same instance, states of bean usually do not be shared among users/threads
	- Prototype: new instance is requested each time, hold states specific to users/not shared
	- Request: new instance for every HTTP request
	- Session: new instance for every HTTP session
	- Application: this bean is scoped at application level
	- Websocket: websocket level
![[Pasted image 20240724000028.png]]

---------------------------- --------------------------
### Special Spring Bean
- Environment: Environment abstraction 
	- In Java, an @Environment bean is a type of annotation used with Spring Boot to represent a bean that can be injected with configuration properties from the environment. These properties can be sourced from various places such as system properties, environment variables, or configuration files
	- ![[Pasted image 20240724000832.png]]

- Bean profile:
	- certain bean should only be used in certain environment
	- 3 levels: spring component level, config level, bean method in configuration level
	- ![[Pasted image 20240724001049.png]]
- ![[Pasted image 20240724001344.png]]
![[Pasted image 20240724001421.png]]

### @Value annotation
- inject properties files, env variables, or default values into Beans
- ![[Pasted image 20240724001728.png]]
-  ![[Pasted image 20240724001748.png]]

--------------------------------------------------------
### Spring Best Practices