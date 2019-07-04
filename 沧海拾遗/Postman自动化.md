# Postman自动化

我们经常需要使用 Postman 来测试 API，但是很多 API 请求都依赖于之前的请求结果，这样我们在做 API 测试的时候就很麻烦。

针对于这个问题，Postman 有一个叫做ENVIRONMENTS(环境)的东西可以实现记录一些数据，它既可以设置固定的数据，也可以在 Pre-request Script 和 Test 中写代码来实现环境变量的记录。之后可以在路径或者参数中直接引用这些变量。

如果把整个逻辑设计得当，可以直接用 Postman 的 Runner 来快速对 API 进行一次整体的测试。