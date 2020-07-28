# Spring Framework

- A Dependency Injection Framework

## Terminologies

### Beans

- Instances managed by Spring framework

### Autowiring

- Process of identifying dependencies and instantiating the object

### Dependency Injection

- 

### Inversion of Control

- Giving control of instatiating objects to Spring Framework

### IOC Container

- Represent anything that is implementing IOC

### Application Context

- Where all the beans are created and maintained.

## Annotations

### `@SpringBootApplication` = @Configuration + @ComponentScan

### `@ComponentScan("<<package_name>>")`

### `@Component` registers marked class as bean managed by Spring

### `@AutoWired` instantiates the object of autowired class/interface

### `@Qualifier` used for named instantiation along with @AutoWired

- `@Qualifier("bubbleSortService")`

### `@Scope` defines the scope of the object instantiated by Spring

- `@Scope(ConfigurableBeanFactory.SCOPE_PROTOTYPE)`
- `@Scope(value = ConfigurableBeanFactory.SCOPE_PROTOTYPE, proxyMode = ScopedProxyMode.TARGET_CLASS)` is applied for Child class to instantiates child of Singleton object with child scope like Prototype. It makes sure that separate objects are created for child class event if parent is with Singleton scope.

### `@PostConstruct` annotted method is called after bean is created with dependencies

### `@PreDestroy` annotted method is called before bean is removed

### `@RestController`

### `@Controller` 

### `@Service` business service Facade

### `@Repository` encapsulates storage, retrieval, and search behavior from RDBMS

### `@RequestMapping("/welcome")`

