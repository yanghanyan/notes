客户端负载均衡：Spring Cloud Ribbon
=========

　　Spring Cloud Ribbon是一个基于HTTP和TCP的客户端负载均衡工具，它基于Netflix Ribbon实现。通过Spring Cloud的封装，可以让我们轻松地将面向服务的REST模板请求自动转换成客户端负载均衡的服务调用。

　　Spring Cloud Ribbon虽然只是一个工具类框架，它不像服务注册中心、配置中心、API网关那样需要独立部署，但是它几乎存在于每一个Spring Cloud构建的微服务和基础设施中。因为微服务间的调用，API网关的请求转发等内容，实际上都是通过Ribbon来实现的,包括后续我们将要介绍的Feign,它也是基于Ribbon实现的工具。

　　所以，对Spring Cloud Ribbon的理解和使用，对于我们使用Spring Cloud来构建微服务非常重要。

## 1、客户端负载均衡
　　负载均衡是对系统的高可用、网络压力的缓解和处理能力扩容的重要手段之一。负载均衡分为硬件负载均衡和软件负载均衡。

- 硬件负载均衡主要通过在服务器节点之间安装专门用于负载均衡的设备，比如F5等
- 软件负载均衡则是通过在服务器上安装一些具有均衡负载功能或模央的软件来完成请求分发工作，比如Nginx等。

　　通过SpringCloudRibbon的封装，我们在微服务架构中使用客户端负载均衡调用非常简单，只需要如下两步:
- 服务提供者只需要启动多个服务实例并注册到一个注册中心或是多个相关联的服务注册中心。
- 服务消费者直接通过调用被@LoadBalanced注解修饰过的RestTemplate 来实现面向服务的接口调用。

## 2、RestTemplate详解
　　RestTemplate会使用Ribbon的自动化配置，同时通过配置@LoadBalanced还能够开启客户端负载均衡。下面将详细介绍RestTemplate针对几种不同请求类型和参数类型的服务调用实现。

### 2.1、GET请求
　　在RestTemplate中，对GET请求可以通过如下两个方法进行调用实现。

#### 2.1.1、getForEntity函数。
　　该方法返回的是ResponseEntity,该对象是Spring对HTTP请求响应的封装，其中主要存储了HTTP的几个重要元素，比如HTTP请求状态码的枚举对象HttpStatus (也就是我们常说的404、 500这些错误码)、在它的父类HttpEntity中还存储着HTTP请求的头信息对象HttpHeaders以及泛型类型的请求体对象。

**getForEntity函数实际上提供了以下三种不同的重载实现:**
- **getForEntity(String url, Class responseType, object... urlVariables):**

　　该方法提供了三个参数，url->请求地址，responseType->请求响应体body的包装类型，urlVariables->url中的参数绑定。比如:
```java
RestTemplate restTemplate = new RestTemplate();
ResponseEntity<User> responseEntity = restTemplate.getForEntity("http://USER-SERVICE/user?name={1}", User.class, "bob");
User body = responseEntity.getBody();
```

- **getForEntity(String url, Class responseType, Map urlVariables) :**

　　该方法提供的参数中，只有urlVariables的参数类型与上面的方法不同。这里使用了Map类型，所以使用该方法进行参数绑定时需要在占位符中指定Map中参数的key值，比如:
```java
RestTemplate restTemplate = new RestTemplate();
Map<string, String> params = new HashMap<>(16);
params.put("name", "bob") ;
ResponseEntity<String> responseEntity = restTemplate. getForEntity("http://USER-SERVICE/user?name={name}", String.class, params);
```

- **getForEntity(URI url, Class responseType):**

　　该方法使用URI对象来替代之前的url和urlVariables参数来指定访问地址和参数绑定。URI 是JDK java.net包下的一个类,它表示一个统一资源标识符( Uniform Resource Identifier)引用。
```java
RestTemplate restTemplate = new RestTemplate() ;
UriComponents uriComponents = UriComponentsBuilder.fromUristring("http://USER-SERVICE/user?name={name}").build().expand("dodo").encode();
URI uri = uriComponents.touri();
ResponseEntity<string> responseEntity = restTemplate.getForEntity(uri, String.class).getBody();
```

#### 2.1.2、getFor0bject函数。
　　该方法可以理解为对getForEntity的进一步封装，它通过HttpMessageConverterExtractor对HTTP的请求响应体body内容进行对象转换，实现请求直接返回包装好的对象内容。比如:
```java
RestTemplate restTemplate = new RestTemplate();
User result = restTemplate.getForobject("http://USER-SERVICE/user?name={1}", User.class, "bob");
```

　　**当不需要关注请求响应除body外的其他内容时，该函数就非常好用，可以少一个从Response中获取body的步骤。它与getForEntity函数类似，也提供了三种不同的重载实现:**
- **getFor0bject(String url, Class responseType, object... urlVariables):**

　　与getForEntity的方法类似，url参数指定访问的地址，responseType 参数定义该方法的返回类型，urlVariables参数为url中占位符对应的参数。

- **getForobject(String url, Class responseType, Map urlVariables):**

　　在该函数中,使用Map类型的urlVariables替代上面数组形式的urlVariables,因此使用时在url中需要将占位符的名称与Map类型中的key一一对应设置。

- **getForobject(URI url, Class responseType):**

　　该方法使用URI对象来替代之前的url和urlVariables参数使用。


### 2.2、POST请求
　　在RestTemplate中，对POST请求时可以通过如下三个方法进行调用实现。

#### 2.2.1、postForEntity 函数。
　　该方法同GET请求中的getForEntity类似，会在调用后返回ResponseEntity<T>对象，其中T为请求响应的body类型。比如:
```java
RestTemplate restTemplate = new RestTemplate();
HttpHeaders headers = new HttpHeaders();
headers.setContentType(MediaType.APPLICATION_JSON_UTF8);
HttpEntity<User> httpEntity = new HttpEntity<>(new User(1L, "bob"), headers);
ResponseEntity<string> responseEntity = restTemplate.postForEntity("http://USER-SERVICE/user", httpEntity, String.class);
String body = responseEntity.getBody();
```

**postForEntity函数也实现了三种不同的重载方法：**
- **postForEntity(String url, object request, Class responseType, object... uriVariables)**
- **postForEntity(String url, object request, Class responseType, Map uriVariables)**
- **postForEntity(URI url, object request, Class responseType)**

　　这些函数中的参数用法大部分与getForEntity一致，这里需要注意的是新增加的request参数，该参数可以是一个普通对象，也可以是一个HttpEntity对象。如果是一个普通对象非HttpEntity对象的时候，RestTemplate 会将请求对象转换为一个HttpEntity对象来处理，其中Object就是request的类型，**request 内容会被视作完整的body来处理**；而如果request是一个HttpEntity对象，那么就会被当作一个完成的HTTP请求对象来处理，**这个request中不仅包含了body的内容，也包含了header的内容**。

#### 2.2.2、postForobject 函数。
　　该方法也跟getForobject的类型类似，它的作用是简化postForEntity的后续处理。通过直接将请求响应的body内容包装成对象来返回使用，比如下面的例子:
```java
RestTemplate restTemplate = new RestTemplate();
User user = new User("cendy", 20);
String postResult = restTemplate.postForobject("http://USER-SERVICE/user", user, String.class);
```

**postForobject函数也实现了三种不同的重载方法:**
- **postForobject(String url, object request, Class responseType, object... uriVariables)**
- **postForobject(String url, object request, Class responseType, Map uriVariables)**
- **postForobject(URI url, object request, Class responseType)**

　　这三个函数除了返回的对象类型不同，函数的传入参数均与postForEntity一致，因此可参考之前postForEntity的说明。

#### 2.2.3、postForLocation函数。
　　该方法实现了以POST请求提交资源，并返回新资源的URI,比如下面的例子:
```java
User user = new User("tony",40) ;
URI responseURI = restTemplate.postForLocation("http://USER-SERVICE/user", user);
```
**postForLocation函数也实现了三种不同的重载方法:**
- **postForLocation(String url, object request, object... urlVariables)**
- **postForLocation(String url, object request, Map urlVariables)**
- **postForLocation(URI url, Object request)**

　　由于postForLocation函数会返回新资源的URI,该URI就相当于指定了返回类型，所以此方法实现的POST请求不需要像postForEntity和postForobject那样指定responseType。其他的参数用法相同。

### 2.3、PUT请求
　　在RestTemplate中，对PUT请求可以通过put方法进行调用实现，比如:
```java
RestTemplate restTemplate = new RestTemplate();
Long id = 10001L;
User user = new User("tony", 40);
restTemplate.put("http://USER-SERVICE/user/{1}", user, id);
```

**put函数也实现了三种不同的重载方法:**
- **put(String url, object request, object... urlVariables)**
- **put(String url, object request, Map urlVariables)**
- **put(URI url, object request)**

　　put函数为void类型，所以没有返回内容，也就没有其他函数定义的responseType参数，除此之外的其他传入参数定义与用法与postForobject基本一致。

### 2.4、DELETE请求
　　在RestTemplate中,对DELETE请求可以通过delete方法进行调用实现，比如:
```java
RestTemplate restTemplate = new RestTemplate();
Long id = 10001L;
restTemplate.delete("http://USER-SERVICE/user/{1}", id);
```

**delete函数也实现了三种不同的重载方法:**
- **delete(String url, object... urlVariables)**
- **delete(String url, Map urlvariables)**
- **delete(URI url)**

　　由于我们在进行REST请求时，通常都将DELETE请求的唯一标识拼接在 url中，所以DELETE请求也不需要request的body信息,就如上面的三个函数实现一样，非常简单。url指定DELETE请求的位置，urlVariables 绑定url中的参数即可。

## 3、配置详解
### 3.1、自动化配置
　　在引入Spring Cloud Ribbon的依赖之后，就能够自动化构建下面这些接口的实现。

- **IClientConfig:**
Ribbon 的客户端配置，默认采用com.netflix.client.config.DefaultClientConfigImpl实现。
- **IRule:**
Ribbon 的负载均衡策略，默认采用com.netflix.loadbalancer.ZoneAvoidanceRule实现,该策略能够在多区域环境下选出最佳区域的实例进行访问。
- **IPing:**
Ribbon的实例检查策略,默认采用com.netflix.loadbalancer.NoOpPing实现，该检查策略是一个特殊的实现，实际上它并不会检查实例是否可用，而是始终返回true,默认认为所有服务实例都是可用的。
- **ServerList<Server>:**
服务实例清单的维护机制，默认采用com.netflix.loadbalancer.ConfigurationBasedServerList实现。
- **ServerListFilter<Server>:** 服务实例清单过滤机制，默认采用org.springframework.cloud.netflix.ribbon.ZonePreferenceServerListFilter实现，该策略能够优先过滤出与请求调用方处于同区域的服务实例。
- **ILoadBalancer:** 负载均衡器，默认采用com.netflix.loadbalancer.ZoneAwareLoadBalancer实现，它具备了区域感知的能力。

　　针对一些个性化需求，我们也可以方便地替换上面的这些默认实现。只需在SpringBoot应用中创建对应的实现实例就能覆盖这些默认的配置实现。比如下面的配置内容，由于创建了PingUrl实例，所以默认的NoOpPing就不会被创建。
```java
@Configuration
public class MyRibbonConfiguration {
    @Bean
    public IPing ribbonPing(IClientConfig config) {
        return new PingUrl();
    }
}
```

　　另外，也可以通过使用@RibbonClient注解来实现更细粒度的客户端配置，比如下面的代码实现了为hello-service服务使用HelloServiceConfiguration中的配置。
```java
@Configuration
@RibbonClient(name = "hello-service", configuration = HelloServiceConfiguration.class)
public class RibbonConfiguration {
}
```

### 3.2、参数配置
　　对于Ribbon的参数配置通常有两种方式:全局配置以及指定客户端配置。

- **全局配置的方式很简单，只需使用ribbon.&lt;key&gt;=&lt;value&gt;格式进行配置即可。**
其中，&lt;key&gt;代表了Ribbon 客户端配置的参数名&lt;value&gt;则代表了对应参数的值。比如，我们可以像下面这样全局配置Ribbon创建连接的超时时间:
```properties
ribbon.ConnectTimeout=250
```

- **指定客户端的配置方式采用&lt;client&gt;.ribbon.&lt;key&gt;=&lt;value&gt;的格式进行配置。**

　　对于Ribbon参数的key以及value类型的定义,可以通过查看com. netflix.client.config.CommonClientConfigKey类获得更为详细的配置内容。

### 3.3、与 Eureka 结合
　　当在Spring Cloud的应用中同时引入Spring Cloud Ribbon和Spring Cloud Eureka依赖时，会触发Eureka中实现的对Ribbon的自动化配置。

　　这时ServerList的维护机制实现将被
com.netflix.niws.1oadbalancer.DiscoveryEnabledNIWSServerList的实例所覆盖，该实现会将服务清单列表交给Eureka的服务治理机制来进行维护；IPing的实现将被com.netflix.niws.loadbalancer.NIWSDiscoveryPing的实例所覆盖，该实现也将实例检查的任务交给了服务治理框架来进行维护。

　　默认情况下，用于获取实例请求的Serverlist接口实现将采用Spring Cloud Eureka中封装的org.springframework.cloud.netflix.ribbon.eureka.DomainExtractingServerList,其目的是为了让实例维护策略更加通用，所以将使用物理元数据来进行负载均衡，而不是使用原生的AWS AMI元数据。

　　在Spring Cloud Ribbon与Spring Cloud Eureka结合的工程中,可以通过参数配置的方式来禁用Eureka对Ribbon服务实例的维护实现。只需在配置文件中加入如下参数，这时我们对于服务实例的维护就又将回归到使用&lt;client&gt;.ribbon.listOfServers参数配置的方式来实现了。
```yml
ribbon:
  eureka:
    enabled: false
```

## 4、重试机制
　　由于Spring Cloud Eureka实现的服务治理机制强调了CAP原理中的AP，即可用性与可靠性，它与ZooKeeper这类强调CP (一致性、可靠性)的服务治理框架最大的区别就是，Eureka为了实现更高的服务可用性，牺牲了一定的一致性， 在极端情况下它宁愿接受故障实例也不要丢掉“健康”实例。

　　由于Spring Cloud Eureka在可用性与一致性上的取舍，不论是由于触发了保护机制还是服务剔除的延迟，引起服务调用到故障实例的时候，我们还是希望能够增强对这类问题的容错。所以，我们在实现服务调用的时候通常会加入一些重试机制。
```yml
spring:
  cloud:
    loadbalancer:
      retry:
        enabled: true
```

**各参数的配置说明:**
- **spring.cloud.loadbalancer.retry.enabled:** 该参数用来开启重试机制，它默认是关闭的。
- **hystrix.command.default.execution.isolation.thread.timeoutInMilliseconds:** 断路器的超时时间需要大于Ribbon 的超时时间，不然不会触发重试。
- **hello-service.ribbon.ConnectTimeout:** 请求连接的超时时间。
- **hello-service.ribbon.ReadTimeout:** 请求处理的超时时间。
- **hello-service.ribbon.OkToRetryOnAlloperations:** 对所有操作请求都进行重试。
- **hello-service.ribbon.MaxAutoRetriesNextServer:** 切换实例的重试次数。
- **hello-service.ribbon.MaxAutoRetries:** 对当前实例的重试次数。

　　根据如上配置，当访问到故障请求的时候，它会再尝试访问一次当前实例(次数由MaxAutoRetries配置)，如果不行，就换一个实例进行访问，如果还是不行，再换一次实例访问(更换次数由MaxAutoRetriesNextServer配置)，如果依然不行，返回失败信息。
