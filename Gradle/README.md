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

## 第三章：构建脚本代码

Gradle 脚本拥有 Groovy 所有的能力。

```groovy
task upper << {
	String str = "My Name"
	println "Original: " + str
	println "upperCase：" + str.toUpperCase()
}
```

```
task count << {
	5.times { print "$it "}

	println ""
	
	3.times { i -> 
		print i+" "
	}
}
```

## 第四章：任务依赖

你可以声明任务之间的依赖关系。

```groovy
task hello << {
	println "task hello"
}

task intro(dependsOn: hello) << {
	println "I am Gradle!"
}
```

输出内容：

```
> gradle -q intro
Hello world!
I'm Gradle
```

在执行 intro 任务时，会以执行 hello 作为前置条件。

**在添加一个依赖之前，这个依赖任务不需要提前定义。**

```groovy
// 可以在任务定义之前添加依赖
task taskA(dependsOn: 'taskB') << {
	println "Task A"
}

task taskB << {
	println "Task B"
}
```

```
> gradle -q taskA
Task B
Task A
```

这一点对于多任务构建非常重要。

## 第五章：动态任务

Gradle 不仅可以定义一个任务做什么，还可以动态创建任务。

```groovy
// 创建动态任务
4.times { index ->
	task "task$index" << {
		println "I am task $index"
	}
}
```

```
> gradle -q task1
I am task 1
> gradle -q task3
I am task 3
```

## 第六章：使用已经存在的任务

**任务创建后设置依赖关系。**

```groovy
// 创建动态任务

4.times { index ->
	task "task$index" << {
		println "I am task $index"
	}
}

task0.dependsOn task1, task3
```

```
> gradle -q task0
I am task 1
I am task 3
```

**通过 API 访问任务，为任务添加行为。**

```groovy
// 访问任务，给任务添加行为

task hello << {
	println "Hello"
}

hello.doLast {
	println "Do last"
}

hello.doFirst {
	println "Do first"
}

hello << {
	println "Fast do last"
}
```

```
> gradle -q hello
Do first
Hello
Do last
Fast do last
```

doFirst 和 doLast 可以执行多次，它们分别可以在 task 开始和结束时插入动作。`<<` 相当于 doLast 的简写。