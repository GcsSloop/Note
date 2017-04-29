# Gradle 笔记

## 第一章：Project 和 Task

Gradle 里面任何东西都是基于两个基础概念：

- Peoject - 项目
- tasks - 任务

每一个构建都由一个或者多个 Project 构成，一个 Project 代表什么取决于你想用 Gradle 做什么。

每一个 Project 又由若干 tasks 构成，一个 tasks 代表更加细化的构建。

## 第二章：Hello World

你可以用 **gradle** 命令运行一个 Gradle 构建。

**gradle** 命令会在当前目录下查找一个 build.gradle 的文件，我们称这个文件为构建脚本，但是严格来说他是一个构建配置脚本，这个脚本定义了一个 project 和它的 tasks。

先创建一个 build.gradle 

```groovy
task hello{
	println "pre hello"
	doLast {
		println "Hello World!"
	}
		doLast {
		println "Hello World! 2"
	}
	println "post hello"
	doFirst{
		println "frist hello"
	}
	doFirst{
		println "frist hello2"
	}
}
```

在命令行中执行 `gradle -q hello` 可以看到输出结果为：

```
pre hello
post hello
frist hello2
frist hello
Hello World!
Hello World! 2
```

从上面示例中我们可以得到以下信息：

1. `-q` 表示 quite 模式，只输出结果，不输出中间信息。
2. gradle 会先按顺序执行 task 中内容，随后会根据 action 状态来执行 action。
3. `doFirst` 按照书写顺序逐个插入头部，因此执行顺序和书写顺序相反。
4. `doLast` 按照书写顺序逐个插入尾部，因此执行顺序和书写顺序相同。 

### 快捷任务

```groovy
task hello << {
    println 'Hello world!'
}
```

上述内容和下面等价：

```groovy
task hello {
    doLast {
        println 'Hello world!'
    }
}
```

