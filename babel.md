babel的用途

1. 转译 esnext、ts、flow等目标环境支持的语言

2. 一定特定用途的代码转换

3. 代码的静态解析

   这个地方是因为对于代码parse之后，可以进行转换，是因为通过AST的结构，能够理解代码，理解代码之后我们将其转换为其他代码之外，还可以对代码进行一些检查或者操作。

   1. linter工具就是分析AST的结构，进行代码规范检查的。
   2. api文档自动生成，可以提取代码中的注释，然后生成文档。
   3. type checker 会根据从AST中提取的或者推到的类型信息，对AST进行类型是和否一致的检查，从而减少运行时的类型错误。比如TS



babel的编译流程

babel 是 source to source的转换，整体编译流程分为三步。

1. parse：通过 parse 把源码转换成抽象语法书（AST）
2. transform： 遍历AST，通过调用各种 transform 插件对 AST 进行增删改查。
3. generate：把转换后的AST打印成目标代码，生成source map



@babel/parser 之前是babylon，基于acorn实现。提供了 parse 和 parseExpression

```
function parse(input: string, options: ParserOptions):File
function parseExpression(input: string, options?: ParserOptions): Expression
```



