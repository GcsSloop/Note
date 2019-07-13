# Kotlin Android

Kotlin 非常适合开发 Android 应用程序，将现代语言的所有优势带入 Android 平台而不会引入任何新的限制：

- **兼容性**：Kotlin 与 JDK 6 完全兼容，保障了 Kotlin 应用程序可以在较旧的 Android 设备上运行而无任何问题。Kotlin 工具在 Android Studio 中会完全支持，并且兼容 Android 构建系统。
- **性能**：由于非常相似的字节码结构，Kotlin 应用程序的运行速度与 Java 类似。 随着 Kotlin 对内联函数的支持，使用 lambda 表达式的代码通常比用 Java 写的代码运行得更快。
- **互操作性**：Kotlin 可与 Java 进行 100％ 的互操作，允许在 Kotlin 应用程序中使用所有现有的 Android 库 。这包括注解处理，所以数据绑定与 Dagger 也是一样。
- **占用**：Kotlin 具有非常紧凑的运行时库，可以通过使用 ProGuard 进一步减少。 在[实际应用程序](https://blog.gouline.net/kotlin-production-tales-62b56057dc8a)中，Kotlin 运行时只增加几百个方法以及 .apk 文件不到 100K 大小。
- **编译时长**：Kotlin 支持高效的增量编译，所以对于清理构建会有额外的开销，[增量构建通常与 Java 一样快或者更快](https://medium.com/keepsafe-engineering/kotlin-vs-java-compilation-speed-e6c174b39b5d)。
- **学习曲线**：对于 Java 开发人员，Kotlin 入门很容易。包含在 Kotlin 插件中的自动 Java 到 Kotlin 的转换器有助于迈出第一步。[Kotlin 心印](https://www.kotlincn.net/docs/tutorials/koans.html) 通过一系列互动练习提供了语言主要功能的指南。