> 类全路径：`org.springframework.boot.CommandLineRunner`

`org.springframework.boot.CommandLineRunner` 是 Spring Boot 提供的一个接口，**用于在 Spring Boot 应用程序启动后执行一些自定义的操作**。它是一个函数式接口，定义了一个方法 `void run(String... args)`，允许你在应用程序启动时执行一些初始化逻辑。

通常，你可以创建一个实现 `CommandLineRunner` 接口的类，并在其中编写初始化逻辑。当 Spring Boot 应用程序启动时，这些初始化逻辑将在 `run()` 方法中执行。

以下是使用 `CommandLineRunner` 的一般用法：

1. 创建一个类，实现 `CommandLineRunner` 接口。   
2. 实现 `run()` 方法，编写应用程序启动后要执行的初始化逻辑。在这个方法中，你可以执行各种任务，如加载配置、预热缓存、初始化数据库连接等。
3. 将实现了 `CommandLineRunner` 接口的类注册到 Spring 的应用上下文中。
4. 在应用程序启动后，`run()` 方法中的逻辑将自动执行。

示例代码如下：
```java
import org.springframework.boot.CommandLineRunner;
import org.springframework.stereotype.Component;

@Component
public class MyCommandLineRunner implements CommandLineRunner {

    @Override
    public void run(String... args) throws Exception {
        // 在应用程序启动后执行的初始化逻辑
        System.out.println("Application has started. Performing initialization tasks...");
        // 可以在这里执行任何你需要的初始化操作
    }
}
```

在这个示例中，`MyCommandLineRunner` 类实现了 `CommandLineRunner` 接口，并在 `run()` 方法中执行了初始化逻辑。当应用程序启动后，Spring Boot 将自动调用这个方法。

你可以创建多个实现 `CommandLineRunner` 接口的类，它们的 `run()` 方法将按照它们在应用上下文中的注册顺序依次执行。这允许你分隔和组织初始化逻辑，以确保在应用程序启动时按照特定的顺序执行不同的任务。