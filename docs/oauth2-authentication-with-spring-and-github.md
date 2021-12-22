# 通过 Spring 和 Github 进行 OAuth2 认证

> 原文:[https://www . geesforgeks . org/oauth 2-使用 spring-and-github 进行身份验证/](https://www.geeksforgeeks.org/oauth2-authentication-with-spring-and-github/)

开放授权或 OAuth 是用于授权的行业级协议。它允许第三方服务交换您的信息，而无需用户提供密码。这是可能的，因为它使用**授权令牌**来证明消费者和服务提供商之间的身份。OAuth2 是对 OAuth 的升级，它本身灌输了更多的安全性。但是在继续之前，让我们详细了解一下 OAuth 的工作和使用。

**示例–**

假设我们有一个服务“A”和“B”。用户 U 同时使用服务“A”和“B”，因此它可以与这两种服务进行通信。现在，如果服务“A”想要访问服务“B”的内容，那么我们需要第三方干预程序来验证服务“A”是安全的，并且可以访问服务“B”。这种干预是由用户自己完成的。

从开发人员的角度来说，假设我们正在构建一个应用程序 x。我们已经知道用户使用一个安全可靠的平台，比如脸书、Instagram、Github 等。因此，我们可以使用脸书的服务让用户登录我们的应用程序，而不是构建我们自己的登录和登录服务。

当我们的应用程序提示脸书服务器时，每次用户尝试登录我们的平台时，服务器都会返回一个密钥，供我们用来验证用户的真实性。OAuth 的整个思想基本上是基于这样一个事实，即第三方应用程序是安全和有保障的，我们相信我们的服务依赖于它们。

**如何在项目中使用 oauth 2:**

现在，Spring 作为一个框架，通过它的各种 Maven 和 Gradle 依赖项向开发人员提供了 OAuth 的特性。要在项目中使用 OAuth2，请按照以下步骤操作:-

1.  Create a new project (Spring Starter), which contains spring web, spring-security dependencies and oauth2 auto-configuration dependencies.
2.  Go to the default class. Add [T0】 @ enableoauth2so 【T1]. This allows us to enable Oauth in the application.
3.  Now, when making OAuth calls, we need to tell the Client (this is a service, here is Github) to look somewhere, so as to know which applications can be used to make Oauth calls. Therefore, we configure our "application". The properties file is changed to applications.yml
4.  We also need various permissions of the application in order to use their security in our application. Here, when we use Github, please go to the [](https://github.com/settings/developers)page.
5.  Select **New OAuth Application** , and the "Register New OAuth Application" page appears. Enter the application name and description. Then, go to the homepage of your application, which in this case should be http://localhost:8080\. Finally, it is pointed out that the authorization callback URL is basically the URL of the path, and users should log in after passing GitHub authentication.
6.  Now, the application we have created will give us **client ID** and **client password.** Copy these fields.
7.  Now, go back to your Spring application and open applications.yml This file needs to be modified as follows. Copy the data in yml file and you can start.

让我们看看下面给出的**应用程序。yml** 如下。

```java
Security:
 oauth2:
    client:
           clientId: your-id
           clientSecret: your-secret
           accessTokenUri: https://github.com/login/oauth/access_token
           userAuthorizationUri: https://github.com/login/oauth/authorize
           clientAuthenticationScheme: form
      resource:
          user-info-uri: https://api.github.com/user
                     prefer-token-info: false
```

**applications . yml 文件描述:**

*   All the information posted above is authorized by Github to identify details. If we want to use "Preference-Token-Information" for any further purpose, we can convert it into **true** .
*   ClienAuthenticationScheme is set to **form** here, just like this example, because Github will use a form to input the detailed information of all users. Moreover, all the above details are used internally by Github, so we don't need to worry about it.

**注意—** 由于应用程序文件是 yml 文件，因此代码的结构必须如上。

此外，当我们在 localhost 上运行上述应用程序时，我们将显示一些文本来查看我们的 OAuth 是否工作，因此我们构建了一个简单的 API 并添加了:-

## Java

```java
@SpringBootApplication
@EnableOAuth2Sso
@RestController

// Main class name DemoApplication
public class DemoApplication {

    // API
    @GetMapping("/")
    public String message(Principal principal) {
        return "hi "+principal.getName();
    }

    public static void main(String[] args) {

        // DemoApplication is the default class.
        SpringApplication.run(DemoApplication.class, args);
    }

}
```

**程序描述:**

*   The demo application is the default class.
*   When Github authentication succeeds, the principal object will receive the user details and display the "hi" user name.

现在运行您的 Spring 应用程序，打开 localhost 8080，自己看看 GitHub 的身份验证工作吧！。