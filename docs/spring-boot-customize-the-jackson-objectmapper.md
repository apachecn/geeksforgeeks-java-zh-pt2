# Spring Boot–定制杰克逊对象映射器

> 原文:[https://www . geesforgeks . org/spring-boot-customize-the-Jackson-object mapper/](https://www.geeksforgeeks.org/spring-boot-customize-the-jackson-objectmapper/)

当使用 JSON 格式时，Spring Boot 将使用对象映射器实例来序列化响应和反序列化请求。在本文中，我们将了解配置序列化和反序列化选项的最常见方法。

让我们来看看默认配置。因此，默认情况下，Spring Boot 配置如下:

*   Disable mapping performance.

*   Disable serialization. WRITE _ date _ AS _ timestamp

让我们从一个更快的例子开始，通过实现相同的

**实施:**

*   客户向我们的/咖啡发送 GET 请求？名称=拉瓦扎
*   控制器将返回一个新的咖啡对象
*   Spring 将通过使用字符串和本地日期时间对象来使用定制选项

如下所示，所以我们首先需要创建一个名为 Coffee 的类，如下所示:

```
// Class
public class Coffee {

  // Getters and setters
  private String name;
  private String brand;
  private LocalDateTime date;
}
```

*   Now we will also define a simple REST controller to demonstrate serialization:

```
@GetMapping ("/coffee")

public Coffee getCoffee(
  @RequestParam(required =  false) String brand,
  @RequiredParam(required = false) String name) {

  return new Coffee()
         .setBrand(brand)
         .setDate(FIXED_DATE)
         .setName(name);
}
```

*   By default, the response when calling get ***is http://localhost:8080/Coffee? Brand = Lavazza*** will be as follows [T4】 o ws:

```
{
  "name": null,
  "brand": Lavazza",
  "date": "2020 - 11 - 16T10: 21: 35.974"
}
```

*   Now we want to exclude null values and have a custom date format *(DD-mm-yyyh: mm)* . The final response is as follows:

```
{
  "brand:" "Lavazza",
  "date": "04-11-20202 10:34"
}
```

*   When using Spring Boot, we can choose to customize the default object mapper or override it. We will introduce these two options in the following chapters.

现在，让我们通过自定义默认对象映射器转到文章中的偏心点。给你。我们将讨论如何定制 Spring Boot 使用的默认对象映射器。

**应用程序属性和自定义杰克逊模块**

配置映射器的最简单方法是通过应用程序属性。配置的一般结构如下:

```
  spring.jackson.<category_name>.<feature_name>=true, false
```

例如，如果我们想禁用序列化功能。WRITE _ DATES _ AS _ TIMESTAMPS，我们将添加:

```
spring.jackson.serialization.write-dates-as-timestamps=false
```

除了上面提到的特征类别，我们还可以配置属性包含:

```
spring.jackson.default-property-inclusion=always, non_null, non_absent, non_default, non_empty
```

用最简单的方法配置环境变量。这种方法的缺点是我们不能定制高级选项，比如为 LocalDateTime 定制日期格式。此时，我们将获得如下所示的结果:

```
{
  "brand": "Lavazza",
  "date": "2020-11-16T10:35:34.593"
}
```

现在，为了实现我们的目标，我们将使用我们的自定义日期格式注册一个新的 JavaTimeModule:

```
@Configuration
@PropertySource("classpath:coffee.properties")

// Class
public class CoffeeRegisterModuleConfig {

  @Bean

  public Module javaTimeModule() {

    JavaTimeModule module = new JavaTimeModule();
    module.addSerializer(LOCAL_DATETIME_SERIALIZER);

    return module;
  }
}
```

**Jackson 2 object mapper buildercustomizer**

这个功能接口的目的是允许我们创建配置 beans。它们将应用于通过杰克逊 2 对象映射生成器创建的默认对象映射器。

```
@Bean
public Jackson2ObjectMapperBuilderCustomizer jsonCustomizer() {
  return builder ->
         builder.serializationInclusion(JsonInclude.Include.NON_NULL)
         .serializers(LOCAL_DATETIME_SERIALIZER);
}
```

> 配置豆以特定的顺序应用，我们可以使用@Order 注释来控制。如果我们想从不同的配置或模块中配置对象映射器，这种优雅的方法是合适的。

杰克逊 2ObjectMapperBuilder

另一个干净的方法是定义一个 Jackson 2 objectmapperbuilder bean。实际上，默认情况下，Spring Boot 在构建对象映射器时使用这个构建器，并且会自动拾取定义的对象:

```
@Bean
public Jackson2ObjectMapperBuilder jackson2ObjectMapperBuilder() {
  return new
         Jackson2ObjectMapperBuilder().serializers(LOCAL_DATETIME_SERIALIZER)
         .serializationInclusion(JsonInclude.Include.NON_NULL);
}
```

默认情况下，它将配置两个选项:

*   Disable the mapping function.

根据 Jackson2ObjectMapperBuilder 文档，如果有些模块存在于类路径中，它也会注册它们:

*   Jackson-datatype-jdk8: Other java 8 types are supported. How to choose them?
*   Jackson-datatype-jsr310: supports Java 8 date and time API types
*   Jackson-datatype-joda:ā345 joda-timeā
*   杰克逊-模块-科特林:支持科特林类和数据类

> **注**

我们只需定义一个类型为 mapping Jackson 2 httpmessageconverter 的 bean，Spring Boot 就会自动使用它:

```
@Bean

// Convertor method
public MappingJackson2HttpMessageConverter() {

  Jackson2ObjectMapperBuilder builder = new
  Jackson2ObjectMapperBuilder().serializers(LOCAL_DATE_SERIALIZER)
  .serializationInclusion(JsonInclude.Include.NON_NULL);

  return new MappingJackson2HttpMessageConverter(builder.build());
}
```

> **注:**请务必查看我们的 Spring Http Message Converters 文章以了解更多信息。

**测试配置**

最后，为了测试我们的配置，我们将使用 TestRestTemplate 并将对象序列化为字符串。通过这种方式，我们可以验证我们的 Coffee 对象是在没有空值的情况下用自定义日期格式进行序列化的:

```
@Test

public voif whenGetCoffee_thenSerializedWithDateAndNonNull() {

  String formattedDate =
    DateTimeFormatter.ofPattern(CoffeeConstants.dateTimeFormat).format(FIXED_DATE);

// Our strings
  String brand = "Lavazza";
  String url = "/coffee?branf=" + brand;
  String response = restTemplate.getForObject(url, String.class);

  assertThat(response).isEqualTo("{"brand\":\"" + brand +
                                "\",\"date\":\"" + formatedDate + "\"}");
}
```

> **结论:**在使用 [Spring Boot 时，我们看了几种配置 JSON 序列化选项的方法。](https://www.geeksforgeeks.org/introduction-to-spring-boot/)这里我们看到了两种不同的方法:配置默认选项或覆盖默认配置。