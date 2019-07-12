# Kotlin 作用

1. 相比于 Java 而言，Kotlin 提供了更简洁的语法，以及一些更方便的特性，简而言之，可以更加省代码量了。

2. Kotlin 可以在 JVM 虚拟机上运行，也支持编译成 Native 代码，直接在目标设备上运行，目前 Kotlin Native 支持以下目标平台：iOS，MacOS，Android，Window，Linux，WebAssembly

3.  互操作，Kotlin/Native 支持与原生世界的双向互操作。Kotlin 可以直接调用原生平台的代码，原生平台的代码也可以调用 kotlin 编译后的 native 内容。

   > 编译器可创建：
   >
   > - 用于多个[平台](https://www.kotlincn.net/docs/reference/native-overview.html#目标平台)的可执行文件
   > - 用于 C/C++ 项目的静态库或[动态](https://www.kotlincn.net/docs/tutorials/native/dynamic-libraries.html)库以及 C 语言头文件
   > - 用于Swift 与 Objective-C 项目的 [Apple 框架](https://www.kotlincn.net/docs/tutorials/native/apple-framework.html)
   >
   > 另一方面，支持直接在 Kotlin/Native 中使用以下现有库的互操作：
   >
   > - 静态或动态 [C 语言库](https://www.kotlincn.net/docs/reference/native/c_interop.html)
   > - C 语言、 [Swift 以及 Objective-C](https://www.kotlincn.net/docs/reference/native/objc_interop.html) 框架
   >
   > 将编译后的 Kotlin 代码包含进用 C、 C++、 Swift、 Objective-C 以及其他语言编写的现有项目中会很容易。 直接在 Kotlin/Native 中使用现有原生代码、 静态或动态 [C 语言库](https://www.kotlincn.net/docs/reference/native/c_interop.html)、 Swift/Objective-C [框架](https://www.kotlincn.net/docs/reference/native/objc_interop.html)、 图形引擎以及任何其他原生内容也很容易。
   >
   > Kotlin/Native [库](https://www.kotlincn.net/docs/reference/native/platform_libs.html)有助于在多个项目之间共享 Kotlin 代码。 POSIX、 gzip、 OpenGL、 Metal、 Foundation 以及许多其他流行库与 Apple 框架都已预先导入并作为 Kotlin/Native 库包含在编译器包中。

4. 多平台共享。

   > 不同目标平台的 Kotlin 与 Kotlin/Native 之间支持[多平台项目](https://www.kotlincn.net/docs/reference/multiplatform.html)。 这是在多个平台之间共享公共 Kotlin 代码的方式，这些平台包括 Android、 iOS、 服务器端、 JVM、 客户端、 JavaScript、 CSS 以及原生平台。

