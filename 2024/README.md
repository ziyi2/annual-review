2025 年已经到来，在 Web 前端这个岗位上不知不觉已经工作了 7 年。这里将自己 2024 年的学习和写作情况做一些简单总结。
> 温馨提示：感兴趣的同学可以追溯 [2023 前端年度技术总结](https://juejin.cn/post/7318561797451939881)。


## 2024 技能更新
紫色部分是今年有所实践的技术。总体来看，在 AI 技术上进行了一些简单实践：
![Front End.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/08c9f9b1168745f0816e59fce727fbd1~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736146541&x-orig-sign=2VUOUPg71dct657fP%2B7B0gXEiYM%3D)
## 2024 学习情况
### AI
今年在 AI 技术上涉及最多，如果说去年对 AI 的原理和基础知识有了基本了解，那么今年在 AI 上进行了几个简单的学习和实践，主要包括以下内容：
|方向|细分|学习关键词|
| --- | --- |--- |
| Open AI 基础 | Prompt Engineering（提示工程）| 提示词要素（指令、上下文、输入数据、输出指示）、零样本提示、少样本提示、链式思考 CoT 提示（中间推理步骤、零样本 CoT 提示）、Prompt Chaining、思维数 ToT、**检索增强生成 RAG**、**Few Shot** 等|
| Open AI 基础 | Fine- Tuning（微调）            | 训练模型（数据探索、数据准备）、测试模型、使用微调模型、根据统计数据迭代微调模型（分析微调模型、迭代数据质量、迭代数据量、迭代参数和）、微调模型和基本模型评估对比等|
| 低代码 AI    | AI  生成 & 修改                | 竞品分析、 Prompt 组装（含 RAG、多模态生成、**JSON Patch**、**Yoga 跨平台布局引擎**、HTML & JSON Schema 转换|
| Java Copilot | 简单 Copilot 设计尝试   | Java 工程配置、检索增强生成 RAG、多任务调度代码生成|
| Copilot      | Github Copilot 原理解析        | 竞品分析、Code 模型能力对比、Sourcemap 逆向还原、VS Code Extension API、**Prompt 提取策略（Prompt 配置、相邻文件文件获取、相似 Snnippets 滑动窗口计算）**、Prompt 组装策略（剩余 Token 计算、组装优先级）、补全策略（单行补全、多行补全）、补全缓存、补全请求、LSP（**Language Server Protocol**）、Tree Sitter（AST 解析）|
#### 低代码 AI
在低代码 AI Prompt 的组装设计中，使用了 [Prompt Engineering（提示工程）](https://www.promptingguide.ai/zh)的 CoT 和 RAG 提示能力，以增强 AI 生成的稳定性和准确性。在 AI 修改（在已有页面中发送修改指令）的设计中，为了节省请求的 Token 数量，仅让 AI 返回需要增删改的节点信息，并通过 [JSON Patch](https://jsonpatch.com/) 的方式更新节点。由于低代码编辑器采用自由布局（类似于 iOS 的 [Frame based layout](https://fluffy.es/frame-vs-autolayout/)），需要 AI 返回 Frame 信息（`left`、`top`、`width` 和 `height` 等位置和大小信息）的 JSON Schema，但 AI 往往无法准确计算出节点的位置信息（例如节点位置重叠、忽略  padding 处理等）。为此，尝试让 AI 返回 Flex 布局的 JSON Schema 或者 HTML，然后利用算法计算出 Frame 信息，粗略的实现流程如下所示：

![无标题文档(2) (2).png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/8089a6902b1a4fe5a8343d5e8fb4c399~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736147695&x-orig-sign=rPoiVz4wvOMEvX4eJu6K8Q80T9I%3D)

计算 Frame 信息的方案包括静态和动态两种方式，静态计算采用  [Yoga 跨平台布局引擎](https://github.com/facebook/yoga) 实现，需要强制让 AI 返回符合 Flex 布局的 JSON Schema（对于 AI 而言具备解释成本，但是相对于 Frame Layout 解释成本变低，例如需要防止 AI 生成 Grid 布局），然后通过 [Yoga Layout](https://www.npmjs.com/package/yoga-layout) 静态计算出 Frame 信息（如何考虑数据的动态填充渲染计算呢）。动态计算则是将 JSON Schema 直接通过低代码引擎（支持 Flex 布局渲染 Antd 组件库）进行浏览器渲染，经过浏览器渲染后计算出对应的 Frame 信息，然后转化成 Frame based Layout 编辑态布局。当然，也可以直接让 AI 返回 HTML 信息（HTML 不支持 Antd 组件库，那么如何在 HTML 中渲染出类似于 Antd 组件库的能力呢？），然后进行浏览器渲染，经过渲染后再转化成编辑态需要的 JSON Schema。大家可以猜猜哪一种方案相对于 AI 而言生成效果更好，那种方案对于 AI 而言解释成本更高？
#### Java Copilot 设计尝试
为了方便 Java 开发人员快速基于数据模型生成对应的 CRUD 接口实现，一起参与共建了 Java Copilot 的 CLI 形态设计。在此期间，简单学习了 Java 服务端的一些基础知识，包括包管理器、编译器和  Java 虚拟机等：
![image.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/0af0469aae7046df95c285fdc86ca138~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736148196&x-orig-sign=CHMLjAhHaiYEjK1VUy7QpbdbxXM%3D)
并简单尝试了 JDK、Meavn 的安装、配置和 IDEA 的使用：
![Image (1).png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/89e8d2cfa56c4abca6f31c6d6861df66~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736148227&x-orig-sign=%2FpALM2p3dt74VBcBJ9ERo4d1TOU%3D)
Java Copilot 起初的设想是一个非常完备的设计方案，具体的设计思路如下所示：

![无标题文档(2) (3).png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/c5f4cc81f104442fa5ba787d269e394d~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736148297&x-orig-sign=hB%2Fzv7ShfLZY2UAFX9wS0WtNuWc%3D)
> 温馨提示：前期简单调研和参考了 Github Copilot 的实现原理。

当时为了快速设计 Demo 原型，最终的实现方案如下所示：

![无标题文档(2) (4).png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/9697fe5020674549900b208964b078dc~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736148580&x-orig-sign=V6WdBgL7R0KBTH516W%2B7VSC%2BpbQ%3D)

#### Github Copilot 原理解析
在设计 Java Copilot 的同时额外研究了 Github Copilot 的实现原理。在研究原理之前，首先对 Github Copilot 的 VS Code Extension 工程项目进行了逆向还原，根据 Sourcemap 对编译代码进行了 AST 解析，将源代码的变量名进行了还原处理，如下所示：

![image (2).png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/fcd0710f259348f5897877092ccc3a0b~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736148764&x-orig-sign=7%2FwDs7ERMv6yOrmwflZbcP8RI20%3D)
> 温馨提示：为什么要增加注释信息，增加注释信息的 `extension.js` 不会破坏原有的代码结构，支持运行和打印调试，而 `extension- recovery.js` 并不能完整还原源代码，只能用于源码阅读，运行时存在一些其它问题（做了各种尝试，最终发现 Copilot 官方在生成 Sourcemap 时专门去除了一些源代码信息）。

尽管还原了工程项目，但是根据 VS Code 扩展入口深入阅读代码非常费劲，第一个星期基本上在阅读一些扩展上下文初始化信息，没有找到核心内容（也是因为对 VS Code Extension 的补全 API 不熟悉，当时就没有想到先找补全 API 的实现），除此之外，如果对 VS Code Exntension 的开发不熟悉，还会继续增加解析成本，中途一度差点放弃。第二个星期突然找到了核心代码部分，还是要感谢坚持的自己，至此一发不可收拾，断断续续花了将近两个月的时间将核心解析完毕，补上一张凌乱的 XMind 核心图感受一下（就像我当时的解析心情一样凌乱）：

尽管还原了工程项目，但根据 VS Code 扩展入口深入阅读后，仍然感到非常费劲。第一个星期基本上在阅读一些扩展上下文初始化信息，却没有找到核心内容。此外，如果对 VS Code Extension 的 API 不熟悉，还会进一步增加解析成本，一度让我差点放弃。第二个星期突然找到了核心代码部分（当然，第一个星期阅读的内容也终于派上了用场），这让我意识到坚持的重要性。于是，我花了将近两个月的时间断断续续地将核心部分解析完毕，补上一张凌乱的 XMind 核心图，感受一下当时解析过程中的纠结心情：

![Github Copilot 核心分析.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/5c741cd4d71744eda72c2bf9b63d697c~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736149273&x-orig-sign=GZND%2FWxJT%2BopmfeU%2Bg%2Bf6WYxaN4%3D)

将上述内容进行总结抽象，Github Copilot 的整个执行流程大致如下所示：

![Github Copilot 智能补全 (1).png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/052933e96ebf4aba920fbfce953e0903~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736149332&x-orig-sign=wq2kdkqt8p02f9FJ5DRl0Ez6OOc%3D)

整个实现的核心是围绕 VS Code  Extension 的补全 API 进行 Prompt 组装和 AI 请求补全，当然内部还会涉及 [LSP（Language Server Protocol）](https://microsoft.github.io/language-server-protocol)、[Tree Sitter（多语言 AST 的 WebAssembly 解析器）](https://tree-sitter.github.io/tree-sitter/)、Web Worker 多线程以及一些相似性算法，例如相邻文件的代码片段利用**滑动窗口算法进行相似度匹配计算**：

![Github Copilot 原理解析 (1) (1).png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/8343fa37a07c4d19aa5723c9c8056353~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736149508&x-orig-sign=GfDtbbYK66%2FCr6%2B4nt9MP6S%2F7go%3D)

> 温馨提示：多线程的执行还需要涉及将对应的 JS 脚本进行工程的逆向还原处理，但是在解析的过程中发现在 `extension.js` 中同样存在多线程中执行的代码，猜想是 Github 的工程师们一开始没有设计多线程，后续为了提升性能进行了 Webpack 多入口的配置。为了减少逆向成本，索性直接更改了扩展脚本，关闭了多线程进行调试。

整个 Github Copilot 的核心解析即将在[《深入浅出微前端》](https://juejin.cn/book/7258893482318626868?scrollMenuIndex=1)的番外篇中出现，整体包括 Github Copilot 的功能介绍、竞品分析、Code 模型介绍 & 对比、原理解析（Prompt 提取策略、组装策略、补全策略和补全请求）和  LSP Demo 实现等，后续也会想办法在社区进行一次分享，感兴趣的同学可以关注一下。

> 温馨提示：你知道 Github Copilot 的代码补全使用的是什么 AI 模型吗？

### LSP

Github Copilot 使用 AI 进行智能提示，但是也内置了 LSP 服务的补全能力（该功能默认不开启，作为 AI Copilot 的备选）。LSP（Language Server Protocol）是一种协议，类似于 CDP 协议，它是由微软定义，主要是为了解决编辑器中语言的**补全、诊断、跳转到定义**等功能：
![VS Code 编程语言扩展能力 (1).png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/215a7cb0ff52481a86b280c5277c3b1b~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736149881&x-orig-sign=EPRI6u0WFew0YZAJvuBXmwTvWg0%3D)
当然，如果直接将语言服务直接集成到 IDE 中会占据大量的 CPU 资源，因为它会对大量的文件进行 AST 解析和静态分析。为了确保语言功能不影响 VS Code （IDE）本身的性能，可以通过 LSP 协议将 IDE 和 LSP 语言服务功能解耦开，语言服务器可以用任何服务语言实现（例如 Node.js、PHP、Java 等），并在自己的独立进程中运行，从而避免 IDE 的性能损耗，而 IDE 只需要请求语言服务器进行通信即可。除此之外，任何符合 LSP 的语言工具都可以与多个符合 LSP 的代码编辑器集成，例如：

![image (3).png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/efbc8340457d4bc293176acacf65f20f~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736150191&x-orig-sign=0vz5oegW%2BawjcBz%2F%2Fagr1LevwrU%3D)

可以通过 Node SDK 来集成 LSP，让 LSP 服务运行在 Node 的环境中。例如不同的语言可以创建不同的语言服务器，如下所示：

![5eecdaf48460cde5e25f0ada718686d26457f3cdc98aed2a58e70b814913bc360a414d3de9277d871abf3af1cbd752498502f534c277d0d4acb43caf8e0cade2184fd0ea91fdc2ccdba3319c9354f026606326575311938dfc653b69905bac42.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/c5457e3f4e0e487cbed89b5236346219~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736150236&x-orig-sign=u%2BFZnKlti1wlx4owmfSevuesmpo%3D)

了解了基础知识后，简单尝试使用 TypeScript 编写 LSP 服务实现了 VS Code 的补全示例，例如以下通过键入 `dd` 自动提示 `dd.ready`（钉钉开放平台的 JS API）：

![image (4).png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/fd5211f3ac0c4588b4291301c1cd97de~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736150301&x-orig-sign=dHDsDyvCPPPZ42VNEmKzcQ3Ty2Q%3D)

> 温馨提示：示例参考了 [Language Server Extension Guide](https://code.visualstudio.com/api/language-extensions/language-server-extension-guide#why-language-server) 进行设计。

### 微前端小册

原计划今年完成[《深入浅出微前端》](https://juejin.cn/book/7258893482318626868?scrollMenuIndex=1)小册的撰写，但是因为番外篇（居然有人觉得番外篇比正片好看...）和生了一个不大不小的病，导致国庆之后两个月没有更新，在这里对于小册读者说一声抱歉。当然，小册的内容也在不断地增加，从原来的 42 个章节增加到了 59 个章节，今年小册的质量相对于去年应该有所提升，核心原理均已解析完毕，主要更新的章节内容包括：

| 方向  | 细分| 学习内容 |                                                     
| --- | --- |--- |                     
| 微前端小册 | 框架示例 | single- spa 的 NPM、Script、Fetch 和 Code Splitting 示例，在 Script 示例中提供了微应用生命周期的 SDK 设计方式。在 Fetch 示例中额外讲解了 Webpack `libirary` 、`libraryTarget` 配置和 Webpack 模块化的运行时原理，并重点讲解了如何提供通用化的识别方式获取微应用的生命周期对象。在 Code Splitting 示例中额外解析了 Code Splitting 的 Webpack 运行时原理。 |
| 微前端小册 | 框架解析 | single- spa 的源码解析、qiankun 的使用示例、`import- html- entry`的源码解析，并循序渐进地讲解了 qiankun 无沙箱、CSS 隔离、CSS 动态隔离、快照隔离、Legacy Proxy 隔离以及 Proxy 隔离的实现原理。                                                                                                                                                     |
| 微前端小册 | 框架设计 | 在状态管理设计中额外讲解了 Monorepo 的设计结构以及 SDK 的调试工程化设计，隔离、性能优化、通信和整体解决方案预计在 2025 年完成。                                                                                                                                                                                                                 |
| 微前端小册 | 番外篇   | 在依赖注入解析篇中讲解了元编程（Metaprogramming）、反射（Reflect）、反射元编程、元数据（ Reflect Metadata）、五种 TypeScript 装饰器类型、依赖注入（Dependency Injection，简称 DI）和控制反转（Inversion of Control，简称 IoC）等概念，并基于以上基础概念简单实现了一个 Midway 依赖注入的框架示例。                                                            |

撰写小册其实花了我非常多的时间，尤其是画一些 UML 图、流程图和框架图，这里给出一张 single-spa 的运行 UML 图设计示例，供大家进行参考：

![vue.svg](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/412fb2d66dc64a2a8fefc801e66dbcbd~tplv-k3u1fbpfcp-image.image#?w=4966\&h=8156\&s=289967\&e=svg\&a=1\&b=fbf1cb)

除了小册的质量提升，小册章节的内容量也再提升，如下所示：

| 章节  | 字数 | 学习时长 |                                                     
| --- | --- |--- |         
| 19.框架解析：single-spa 的 NPM 示例 | 8146 |1小时46分 |    
| 20.框架解析：single-spa 的 Script 示例 | 6390 |1小时12分 |    
| 21.框架解析：single-spa 的 Fetch 示例 | 6390 |2小时36分 |    
| 22.框架解析：single-spa 的 Code Splitting 示例 | 16629 | 3小时14分 |    
| 23.框架解析：single-spa 源码解析 | 17811 |4小时1分 |    
| 24.框架解析：qiankun 使用示例 | 6464 |1小时59分 |    
| 25.框架解析：import-html-entry 源码解析 | 17403 |4小时50分 |    
| 26.框架解析：qiankun 源码解析 - 无沙箱模式 | 18713 |4小时48分 |  
| 27.框架解析：qiankun 源码解析 - CSS 隔离 | 9571 |2小时6分 |  
| 28.框架解析：qiankun 源码解析 - CSS 动态隔离 | 11509 |3小时35分 |  
| 29.框架解析：qiankun 源码解析 - 快照隔离 | 8463 |2小时50分 |  
| 30.框架解析：qiankun 源码解析 - Legacy Proxy 隔离 | 5653 |1小时19分 |  
| 31.框架解析：qiankun 源码解析 - Proxy 隔离 | 18608 |6小时2分 |  
| 44.框架设计：状态管理 | 10182 |1小时38分 |  
| 56.番外篇：依赖注入解析 | 10118 |2小时19分 |  

每次撰写小册章节时都会先调研一些理论基础，并花费大量的时间对一些周边相关的运行原理进行解析，例如工程化原理、Webpack 编译产物运行时原理等，用于加强整个小册的深度和通用性设计，帮助大家掌握微前端的同时也对前端的其它知识有更深入的了解。

### DI & IoC

依赖注入（Dependency Injection，简称 DI）和控制反转（Inversion of Control，简称 IoC）是软件设计中的两个密切相关的概念，它们通常用于实现松耦合的设计，从而提高代码的可维护性和可扩展性。[Midway](https://midwayjs.org/) 是一个服务端 IoC 依赖注入的 Node.js 应用框架，为了完整掌握 Midway 的内部实现原理，简单实现了一个 IoC 自动依赖注入的示例，实现示例的项目工程如下所示：

```jsx
.
├── src                           # 源码目录（可以理解为 midway 中的 src 目录）
│   ├── animal.ts                 
│   ├── cat.ts                    
│   └── dog.ts    
├── ioc                           # 自动识别文件和自动依赖注入功能（需实现）（midway 不对外提供）     
│   ├── container.ts              # IoC 容器（注册和获取实例）
│   ├── inject.ts                 # 属性装饰器（通过元数据建立依赖关系）
│   ├── key.ts                    # 定义元数据的 key
│   ├── load.ts                   # 自动扫描和执行 src 目录的模块文件，实现 IoC 自动绑定功能
│   └── provider.ts               # 通过元数据建立 IoC 容器的绑定关系
└── index.ts                      # 启动脚本
```

`src` 目录下的代码可以理解为已经实现了 IoC 依赖注入功能的代码，主要提供了对应的类和装饰器，通过装饰器声明类之间的依赖关系：

```jsx
// src/animal.ts
import { Inject } from "../ioc/inject"; // 需实现
import Cat from "./cat";
import Dog from "./dog";

@Provider()
export default class Animal {
  @Inject()
  private cat: Cat;

  @Inject()
  private dog: Dog;

  print() {
    this.cat.print();
    this.dog.print();
  }
}


// src/cat.ts
import { Provider } from "../ioc/provider"; // 需实现

@Provider()
export default class Cat {
  print() {
    console.log("Cat");
  }
}

// src/dog.ts
import { Provider } from "../ioc/provider"; // 需实现

@Provider()
export default class Dog {
  print() {
    console.log("Dog");
  }
}


// src/index.ts 启动脚本

// IoC 容器，需实现
import { IoCContainer } from "./ioc/container"; 
 // 程序加载，负责扫描 @Provide、@Inject 相应的实例化及绑定处理，需实现
import { load } from "./ioc/load";

const container = new IoCContainer();
load(container, "./src");

// 无需手动绑定，自动绑定
// Animal 依赖 Cat 和 Dog，通过 @Inject 装饰器自动绑定
// 这里的 Animal 字符串是 Animal 类上的元数据 id，对应的是 Animal 类的构造函数名称
// INFO: 这里也可以通过  Reflect.getMetadata(providerKey, Animal) 获取到 Animal 类上的元数据;
const animal = container.get("Animal");
animal.print(); // Cat Dog
```

`ioc` 目录大致实现流程如下所示：

![image (5).png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/a0aefa2f2b3140a4bc24d7a307622760~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736152156&x-orig-sign=Eh6goofY0moEWvYspNLcIiCQwG0%3D)

依赖注入在服务端设计是非常常见的一种技术，当然在前端领域也可以参考此类技术实现一些框架，例如扩展框架。当然，如果你想使用 IoC 技术来实现一些公司通用的框架设计，可以使用社区中现有的 IoC 库，例如 [InversifyJS](https://github.com/inversify/InversifyJS)。

> 温馨提示：DI 和  IoC 的关系是什么？

### 编译工具

设计了 Webpack Loader & Plugin，用于优化低代码编译的体积问题，并用于解决开发态 JSON Schema 的 URL 请求问题。假设存在如下开发态代码：

```jsx
// @xxx/lowcode-render-engine 内部默认集成了所有的 Antd 组件和 Antd Icons
import LowCodeRenderEngine from '@xxx/lowcode-render-engine';

// 组件化的使用方式
// LowCodeRenderEngine 开发态支持 URL 传递，URL 对应的是低代码平台产生的 JSON Schema 地址（固定地址）
// LowCodeRenderEngine 支持 schema 传递，对应的是 JSON Schema
// LowCodeRenderEngine 内部会根据 JSON Schame 声明的 Antd 组件名称进行动态渲染处理
<LowCodeRenderEngine url="http://aaa.com/bbb.json"></LowCodeRenderEngine>
<LowCodeRenderEngine url="http://aaa.com/ccc.json"></LowCodeRenderEngine>
```

我们希望生产态时，它能转化成如下功能（注意不是编译后的代码）：

```jsx
// @xxx/lowcode-render-engine 内部的 Antd 和 Icons 能够按需引入
// 根据 JSON Schema 中的 Antd 和 Icons 使用情况而定
import LowCodeRenderEngine from '@xxx/lowcode-render-engine';

// 组件化的使用方式
// 生产态部署页面所在的环境可能无法请求到 URL 地址对应的服务环境，因此需要将 URL 转换成真实的 JSON Schema 值
<LowCodeRenderEngine schema=[{/- url 地址对应的 JSON Schema 值 - /}]></LowCodeRenderEngine>
```

在 `LowCodeRenderEngine` 中全量引入了 Antd 组件库和 Icon，从而实现低代码的组件动态渲染。但是真正在开发时可能只需要使用组件库中的一些组件，那么如何使得上述情况可以实现按需引入呢？除此之外，我们希望开发态引入的是 `url` 属性对应的 JSON Schema 地址，而生产态引入 `schema` 属性对应的真正 JSON Schame 值。为了实现上述功能，我们可以借助 Webpack Loader 和 Webpack Plugin 来实现该功能，如下所示：

![image (6).png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/97041a26bd174335b6d550eaea93e73b~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5a2Q5byI:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMzIyNzgyMTg3MDE2MzE3NiJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1736152421&x-orig-sign=5PzW95nR0Tz2664ggXq9c5r5lj8%3D)

第一阶段需要对所有的 TSX 或者 JSX 文件通过 Webpack  Loader 一一进行 AST 解析，提取出对应的 URL 地址，然后批量请求 URL 地址对应的 JSON Schema 值，并将其重新设置到组件的 `schema` 属性上。第二阶段则是通过 Webpack Plugin 对所有使用的 `schema` 属性进行 AST 解析，解析出所有 JSON Schema 的集合，判断整个项目使用了那些 Antd 组件库和 Icons，并再次通过 AST 操作 `@xxx/lowcode-render-engine` 内部的 Antd 和 Icons 全量引入逻辑，将其替换成按需引入语法。例如：

```jsx
// 内部原有实现
import * as designComponents from 'antd';
// AST 替换
// 根据 JSON Schema 动态分析需要按需引入的组件
import * as Button from "antd/es/button";
import * as FlexLayout from "antd/es/flex- layout";
import * as Layout from "antd/es/layout/Layout";
import Page from "antd/es/page";
const designComponents = {
  ...Button,
  ...FlexLayout,
  ...Layout,
  ...Page
};
```

## 2024 收藏书签

这里将平时学习时查阅的博客、文档、电子书、PPT、视频以及 Github 仓库等进行书签汇总，并按照收藏时间进行倒序排序。如果想浏览某一项技术，建议按照年份从低到高进行浏览。通过整理年度书签，可以用于分析自己在这一年中主要学习了哪些技术。

### 作者文章
- [2023 前端年度技术总结](https://juejin.cn/post/7318561797451939881)
- [前端，请回答 2022](https://juejin.cn/post/7188890491188936762)
- [前端杂烩](https://juejin.cn/post/7069468539412807693)
- [Vue CLI 3 结合 Lerna 进行 UI 设计](https://juejin.cn/post/6844903817776103431)
- [基于Vue实现一个简易MVVM](https://juejin.cn/post/6844904099704471559)
- [V8 编译浅谈](https://juejin.cn/post/7041021350114230285)
- [面试分享：两年工作经验成功面试阿里P6总结](https://juejin.cn/post/6844903928442667015)
- [在阿里我是如何当面试官的](https://juejin.cn/post/6844904093425598471)
- [前端面试知识点（一）](https://juejin.cn/post/6987549240436195364)
- [前端面试知识点（二）](https://juejin.cn/post/6996815121855021087)
- [从零开始配置 TypeScript 项目](https://juejin.cn/post/6856410900577026061)
- [Cz工具集使用介绍 - 规范Git提交说明](https://juejin.cn/post/6844903831893966856)
- [使用 NPM 发布和使用 CLI 工具](https://juejin.cn/post/6844904153030852621)
- [2019 前端年度总结](https://juejin.cn/post/6844904038543130632)
- [你真的理解 $nextTick 吗](https://juejin.cn/post/6844903843197616136)
- [基于 Express 应用框架的技术方案选型浅谈](https://juejin.cn/post/6844904150627516424)
- [深入浅出 JavaScript](https://juejin.cn/post/7054363717403836424)
- [桌面端混合开发总结](https://juejin.cn/post/6890659144718614542)
-  [技术文章的写作技巧分享](https://juejin.cn/post/6844904168600109069)
- [Vue CLI 3 构建库时对于产生 Polyfill 的问题分析](https://github.com/ziyi2/ziyi2.github.io/issues/1)
- [Vue CLI 3 缓存旧版本的 Vue 组件(Npm 包)问题](https://github.com/ziyi2/ziyi2.github.io/issues/2)

### 面试
- [面试分享：两年工作经验成功面试阿里 P6 总结](https://juejin.cn/post/6844903928442667015)
- [在阿里我是如何当面试官的](https://juejin.cn/post/6844904093425598471)
- [前端面试知识点（一）](https://juejin.cn/post/6987549240436195364)
- [前端面试知识点（二）](https://juejin.cn/post/6996815121855021087)
- [面试分享：两年工作经验成功面试阿里 P6 总结](https://juejin.im/post/5d690c726fb9a06b155dd40d)
- [在阿里我是如何当面试官的（持续更新）](https://juejin.im/post/5e6ebfa86fb9a07ca714d0ec)
- [【1 月最新】前端 100 问：能搞懂 80% 的请把简历给我](https://juejin.im/post/5d23e750f265da1b855c7bbe)
- [2018 前端面试总结，看完弄懂，工资少说加 3K | 掘金技术征文](https://juejin.im/post/5b94d8965188255c5a0cdc02)
- [2019 面试系列 - 简历](https://juejin.im/post/5d05ca79f265da1bc75237ea)
- [JavaScript-面试](https://segmentfault.com/a/1190000015863923?utm_source=tag-newest#articleHeader0)
- [Javascript 面试核心考点(基础版)](https://github.com/ljianshu/Blog/issues/63)
- [jsliang 的 2019 面试准备](https://juejin.im/post/5c8e4cd3f265da67c87454a0)
- [总结了 17 年初到 18 年初百场前端面试的面试经验(含答案)](https://juejin.im/post/5b44a485e51d4519945fb6b7)
- [面试 -- 网络 HTTP](https://juejin.im/post/5872309261ff4b005c4580d4)
- [中高级前端大厂面试秘籍，为你保驾护航金三银四，直通大厂(上)](https://juejin.im/post/5c64d15d6fb9a049d37f9c20)
- [(下篇)中高级前端大厂面试秘籍，寒冬中为您保驾护航，直通大厂](https://juejin.im/post/5cc26dfef265da037b611738)
- [你要的 React 面试知识点，都在这了](https://juejin.im/post/5cf0733de51d4510803ce34e)
- [大揭秘！“恐怖”的阿里一面，我究竟想问什么](https://juejin.im/post/5d4cd42a6fb9a06aea618155)
- [你要的 Vue 面试题都在这里。](https://juejin.im/post/5d13436f6fb9a07eca698ba0)
- [面试官：自己搭建过 vue 开发环境吗？](https://juejin.im/post/5cc55c336fb9a032086dd701)
- [前端进阶之道](https://yuchengkai.cn/docs/frontend/#%E5%86%85%E7%BD%AE%E7%B1%BB%E5%9E%8B)
- [从面试题看 JS 事件循环与 macro micro 任务队列](https://juejin.im/post/5c8a024d51882546be0a3082)
- [中高级前端开发高频面试题](https://juejin.im/post/5ceaaaf0e51d45508c2fb7c0)
- [阿里前端社招面试总结](https://juejin.im/post/5c90f573e51d450a7d7dfc75)
- [前端内参](https://github.com/coffe1891/frontend-hard-mode-interview)
- [阿里前端社招面试总结](https://juejin.im/post/5c90f573e51d450a7d7dfc75)

### Copilot

- [Github Copilot](https://docs.github.com/zh/copilot/quickstart)
- [Cursor](https://www.cursor.com/)
- [Gemini Code Assist](https://cloud.google.com/gemini/docs/codeassist/overview?hl=zh-cn)
- [通义灵码](https://help.aliyun.com/zh/lingma/product-overview/)
- [MarsCode](https://www.marscode.com/)
- [Copilot-Explorer](https://thakkarparth007.github.io/copilot-explorer/)
- [花了大半个月，我终于逆向分析了Github Copilot](https://zhuanlan.zhihu.com/p/639993637)
- [GitHub Copilot 深度剖析：一个 AI 产品的性能提升、成本控制与效果评估](https://xie.infoq.cn/article/06aabd93dc757a1015def6857)
- [Github Copilot 相关的研究数据报告](https://github.blog/news-insights/research/)
- [研究：量化 GitHub Copilot 对开发人员生产力和幸福感的影响](https://github.blog/news-insights/research/research-quantifying-github-copilots-impact-on-developer-productivity-and-happiness/)
- [GitHub Copilot in the CLI](https://github.com/github/gh-copilot)
- [Smarter, more efficient coding: GitHub Copilot goes beyond Codex with improved AI model](https://github.blog/news-insights/product-news/smarter-more-efficient-coding-github-copilot-goes-beyond-codex-with-improved-ai-model/)
- [首次覆盖超 11 类真实编程场景！豆包大模型团队开源代码大模型全新基准](https://team.doubao.com/zh/blog/%E9%A6%96%E6%AC%A1%E8%A6%86%E7%9B%96%E8%B6%85-11-%E7%B1%BB%E7%9C%9F%E5%AE%9E%E7%BC%96%E7%A8%8B%E5%9C%BA%E6%99%AF-%E8%B1%86%E5%8C%85%E5%A4%A7%E6%A8%A1%E5%9E%8B%E5%9B%A2%E9%98%9F%E5%BC%80%E6%BA%90%E4%BB%A3%E7%A0%81%E5%A4%A7%E6%A8%A1%E5%9E%8B%E5%85%A8%E6%96%B0%E5%9F%BA%E5%87%86)
- [How GitHub Copilot is getting better at understanding your code](https://github.blog/ai-and-ml/github-copilot/how-github-copilot-is-getting-better-at-understanding-your-code/?spm=ata.21736010.0.0.687d7536ko6iYB)
- [The economic impact of the AI-powered developer lifecycle and lessons from GitHub Copilot](https://github.blog/news-insights/research/the-economic-impact-of-the-ai-powered-developer-lifecycle-and-lessons-from-github-copilot/)


### Model

- [o1-mini（STEM 增强）](https://openai.com/index/openai-o1-mini-advancing-cost-efficient-reasoning/)
- [o1-preview（STEM 增强）](https://openai.com/index/introducing-openai-o1-preview/)
- [o1](https://openai.com/index/learning-to-reason-with-llms/)
- [o1-pro](https://openai.com/index/introducing-chatgpt-pro/)
- [Claude 3.5 Sonnet](https://www.anthropic.com/claude/sonnet)
- [CodeX](https://www.anthropic.com/claude/sonnet)
- [Best AI for coding. GPT-o1 mini vs Claude 3.5 Sonnet](https://aimlapi.com/academy-articles/best-ai-for-coding-gpt-o1-mini-vs-claude-3-5-sonnet-comparison)
- [SWE-bench 测评榜单](https://www.swebench.com/)
- [HumanEval Pass@1 基准测试集](https://paperswithcode.com/sota/code-generation-on-humaneval)
- [Enhancing and Benchmarking Real-world Repository-level Code Completion Abilities of Code Large Language Models](https://arxiv.org/pdf/2406.01359)
- [Embedding Models for Different LLM Versions (GPT, Claude, etc.) in Cursor](https://forum.cursor.com/t/embedding-models-for-different-llm-versions-gpt-claude-etc-in-cursor/20677/1)

### Open AI
- [Prompt Engineering Guide](https://www.promptingguide.ai/zh)
- [A-Guide-to-Retrieval-Augmented-LLM](https://github.com/Wang-Shuo/A-Guide-to-Retrieval-Augmented-LLM?tab=readme-ov-file)（RAG 好文）
- [检索增强生成 (RAG)](https://www.promptingguide.ai/zh/techniques/rag)
- [Chain-of-Thought Prompting](https://www.promptingguide.ai/zh/techniques/cot)
- [微调（Fine-tuning）](https://openai.xiniushu.com/docs/guides/fine-tuning)
- [GitHub Copilot Workspace: Welcome to the Copilot-native developer environment](https://github.blog/news-insights/product-news/github-copilot-workspace/)
- [CNN入门讲解：什么是微调（Fine Tune）？](https://zhuanlan.zhihu.com/p/35890660)
- [开源大模型微调指南](http://www.bimant.com/blog/open-source-llm-fine-tuning-guide/)
- [不会算法 也能微调一个NLP预训练模型](https://zhuanlan.zhihu.com/p/567609431)
- [原创｜ GPT 微调，万字保姆级教程+实操案例](https://zhuanlan.zhihu.com/p/654159382)
- [前端工程师如何快速使用一个NLP模型](https://mp.weixin.qq.com/s?__biz=MzkxNTIwMzU5OQ==&mid=2247492139&idx=1&sn=81edc7c73cbe7bf3462ae56d02171cf3&chksm=c160114bf617985df6b493ef18606820b466c93205e3de1b581b11977e6dc8b08074adb2231c&token=1482102797&lang=zh_CN&scene=21#wechat_redirect)
- [南大周志华团队8年力作！「学件」系统解决机器学习复用难题，「模型融合」涌现科研新范式](https://mp.weixin.qq.com/s/N3LzIEVtsxa_-KKjj1A9Xw)
- [微软、OpenAI大佬暗示LLM应用开发范式迁移：从Prompt Engineering到Flow Engineering](https://mp.weixin.qq.com/s/Tj63t9ekS1H6aRPPYgA9NQ)
- [一文探秘LLM应用开发(24)-Prompt(架构模式Agent)](https://mp.weixin.qq.com/s?__biz=MzA5MTIxNTY4MQ==&mid=2461142799&idx=1&sn=82555814fb62babde1ced2e42a9dddac&chksm=87396d21b04ee4370fd27d7a94b3817a176855d20af4d4fb280b74ac3b204ee0da399287ed31&scene=21#wechat_redirect)
- [Open AI](https://openai.com/)
- [API Reference](https://platform.openai.com/docs/api-reference/completions/create)
- [openai-node](https://github.com/openai/openai-node)
- [LangChain](https://python.langchain.com/docs/get_started/introduction)
- [动手深度学习](https://zh-v2.d2l.ai/)
- [openai-cookbook](https://github.com/openai/openai-cookbook)
- [OpenAI API 中文教程](https://www.w3cschool.cn/openai_api/)
- [用 ChatGPT 开发一个能听懂人话的命令行工具](https://mp.weixin.qq.com/s/y177DoneuuQ5krPTGVUU9w)
- [如何让 ChatGPT 读懂超长保险条款？](https://www.yuque.com/wuomzfx/article/wrm3xfauothl1etw)
- [我用我的微信聊天记录和 280 篇博客文章，做了我自己的数字克隆 AI](https://greatdk.com/1908.html)
- [LangChain 与大型语言模型(LLMs)应用基础教程:Prompt 模板](https://blog.csdn.net/weixin_42608414/article/details/129774329?spm=1001.2014.3001.5502)
- [LangChain 与大型语言模型(LLMs)应用基础教程:信息抽取](https://blog.csdn.net/weixin_42608414/article/details/129886621?spm=1001.2014.3001.5502)
- [分享几本 ChatGPT 必读书籍（含 PDF 下载）](https://zhuanlan.zhihu.com/p/622909333)


### Awesome
- [awesome-svelte](https://github.com/TheComputerM/awesome-svelte)
- [awesome-shell](https://github.com/alebcay/awesome-shell)
- [awesome-zsh-plugins](https://github.com/unixorn/awesome-zsh-plugins)
- [awesome-chatgpt](https://github.com/humanloop/awesome-chatgpt)
- [awesome-chatgpt-prompts](https://github.com/f/awesome-chatgpt-prompts)
- [Awesome-Prompt-Engineering](https://github.com/promptslab/Awesome-Prompt-Engineering)
- [awesome-actions](https://github.com/sdras/awesome-actions)
- [awesome-wasm](https://github.com/mbasso/awesome-wasm)（WebAssembly 生态清单）
- [awesome-vue](https://github.com/vuejs/awesome-vue)
- [awesome-react](https://github.com/enaqx/awesome-react)
- [awesome-javascript](https://github.com/sorrycc/awesome-javascript)
- [awesome-nodejs](https://github.com/sindresorhus/awesome-nodejs)
- [awesome-css](https://github.com/awesome-css-group/awesome-css)
- [awesome](https://github.com/sindresorhus/awesome)
- [awesome-awesome](https://github.com/emijrp/awesome-awesome)
- [awesome-awesome-awesome](https://github.com/jonatasbaldin/awesome-awesome-awesome)
- [Front-End-Develop-Guide](https://github.com/icepy/Front-End-Develop-Guide)（前端开发所使用语言的主流学习资源）
- [knowledge](https://github.com/f2e-awesome/knowledge)（前端技术架构图谱）
- [awesome-javascript-cn](https://github.com/jobbole/awesome-javascript-cn)（JavaScript 资源大全中文版）
- [awesome-wechat-weapp](https://github.com/justjavac/awesome-wechat-weapp)\-（微信小程序开发资源汇总）
- [awesome-graphql](https://github.com/chentsulin/awesome-graphql)
- [Awesome Redux](https://github.com/xgrommx/awesome-redux)
- [awesome-github-vue](https://github.com/opendigg/awesome-github-vue)
- [awesome-github-wechat-weapp](https://github.com/opendigg/awesome-github-wechat-weapp)(微信小程序开源项目库汇总)
- [awesome-nuxt](https://github.com/nuxt-community/awesome-nuxt)
- [awesome-nextjs](https://github.com/unicodeveloper/awesome-nextjs)
- [awesome-ui-component-library](https://github.com/anubhavsrivastava/awesome-ui-component-library)
- [awesome-react-components](https://github.com/brillout/awesome-react-components)
- [awesome-mac](https://github.com/jaywcjlove/awesome-mac)
- [awesome-vscode](https://github.com/viatsko/awesome-vscode)
- [Awesome-Design-Tools](https://github.com/LisaDziuba/Awesome-Design-Tools)
- [awesome-webpack](https://github.com/webpack-contrib/awesome-webpack)
- [awesome-gulp](https://github.com/alferov/awesome-gulp)
- [awesome-github](https://github.com/AntBranch/awesome-github)
- [awesome-npm](https://github.com/sindresorhus/awesome-npm)
- [awesome-chrome-devtools](https://github.com/ChromeDevTools/awesome-chrome-devtools#chrome-devtools-protocol)（Chrome DevTools 生态清单）
- [Font Awesome](https://github.com/FortAwesome/Font-Awesome)
- [awesome-resume](https://github.com/resumejob/awesome-resume)（程序员简历例句）
- [awesome-interview-questions](https://github.com/MaximAbramchuck/awesome-interview-questions)
- [awesome-webpack-cn](https://github.com/webpack-china/awesome-webpack-cn)（webpack 优秀中文文章）
- [awesome-architecture](https://github.com/toutiaoio/awesome-architecture)（架构师技术图谱）
- [awesome-books](https://github.com/guanpengchn/awesome-books)（开发者推荐阅读的书籍）
- [awesome-programming-books](https://github.com/royeo/awesome-programming-books)（经典技术书籍推荐）
- [awesome-bookmarks](https://github.com/PanJiaChen/awesome-bookmarks)

### Sourcemap

- [shuji](https://github.com/paazmaya/shuji)
- [reverse-sourcemap](https://github.com/davidkevork/reverse-sourcemap)
- [source-map-explorer](https://github.com/danvk/source-map-explorer)
- [JavaScript Source Maps 简介](https://developer.chrome.com/blog/sourcemaps?hl=zh-cn#how-does-the-source-map-work)
- [调试原始代码，而不是使用源代码映射进行部署](https://developer.chrome.com/docs/devtools/javascript/source-maps?hl=zh-cn#sourceurl_and_displayname)
- [什么是源代码映射？](https://web.dev/articles/source-maps?hl=zh-cn)
- [JavaScript Source Map 详解](https://www.ruanyifeng.com/blog/2013/01/javascript_source_map.html)

### 模块化

- [What are UMD modules?](https://jameshfisher.com/2020/10/04/what-are-umd-modules/)
- [详解 AMD,CMD,ComminJS,ES6 和 UMD 模块化规范](https://github.com/codeF1x/FE/blob/master/%E8%AF%A6%E8%A7%A3AMD%2CComminJS%E5%92%8CUMD%E6%A8%A1%E5%9D%97%E5%8C%96%E8%A7%84%E8%8C%83.md)
- [AMD , CMD, CommonJS，ES Module，UMD](https://juejin.cn/post/6844903663404580878)
- [可能是最详细的UMD模块入门指南](https://juejin.cn/post/6844903927104667662)
- [javascrip中UMD规范的详细介绍](https://www.jianshu.com/p/06f59d60c306)
- [关于前端:一文带你了解-JS-Module-的始末](https://lequ7.com/guan-yu-qian-duan-yi-wen-dai-ni-liao-jie-jsmodule-de-shi-mo.html)
- [《模块化系列》彻底理清 AMD,CommonJS,CMD,UMD,ES6](https://www.qiufeng.blue/webpack/module.html#%E5%BC%95%E8%A8%80)

### 服务端

- [Spring Boot](https://docs.spring.io/spring-boot/)
- [Spring Framework 中文文档](https://springdoc.cn/spring/index.html)
- [Java 教程](https://liaoxuefeng.com/books/java/introduction/index.html)
- [设计模式](https://refactoringguru.cn/design-patterns?_gl=1*3b6sgb*_ga*MjEwMTExOTI2Ny4xNzA0MjgyNzc5*_ga_SR8Y3GYQYC*MTcwNDI4Mjc3OS4xLjAuMTcwNDI4MjgwMS4zOC4wLjA.#intro-patterns)
- [后端架构师技术图谱](https://github.com/xingshaocheng/architect-awesome)
- [Spring Boot 中文论坛](https://forum.springdoc.cn/)
- [超详细！4小时开发一个SpringBoot+vue前后端分离博客项目！！](https://juejin.cn/post/6844903823966732302?searchId=202401031853159910ADF41EAA461BC8D9)
- [Spring 系列框架的中文 PDF 文档](https://springdoc.cn/pdf/#google_vignette)
- [Java服务端学习路线总纲](https://blog.csdn.net/CSDN2497242041/article/details/101926767)
- [2024年最新超详细Java学习路线一条龙版（建议收藏🔥）](https://javabetter.cn/xuexiluxian/java/yitiaolong.html)
- [一份完整的后端学习路线](https://juejin.cn/post/7027743254846111752)
- [后端开发需要学什么？推荐这份超详细的后端开发学习路线图！](https://xie.infoq.cn/article/4418b6129d407aa09dfad35aa)
- [零基础Java学习路线](https://github.com/cosen1024/Java-Interview/blob/main/%E9%9B%B6%E5%9F%BA%E7%A1%80Java%E5%AD%A6%E4%B9%A0%E8%B7%AF%E7%BA%BF.md)
- [IntelliJ-IDEA-Tutorial](https://github.com/judasn/IntelliJ-IDEA-Tutorial?tab=readme-ov-file)
- [Maven](https://mp.weixin.qq.com/s/3umZOaI4l0EIZ5RgtEDchw)


### 协议
- [LSP（Language Server Protocol）](https://microsoft.github.io/language-server-protocol/)
- [CDP（Chrome DevTools Protocol ）](https://chromedevtools.github.io/devtools-protocol/)

### AST
- [AST Explorer](https://astexplorer.net/)
- [Tree Sitter（多语言 AST 的 WebAssembly 解析器）](https://tree-sitter.github.io/tree-sitter/)

### VS Code

- [Language Server Extension Guide](https://code.visualstudio.com/api/language-extensions/language-server-extension-guide#why-language-server)

### IoC

- [谈元编程与表达能力](https://draveness.me/metaprogramming/)
- [Reflect](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Reflect)
- [TypeScript 中的元数据以及 reflect-metadata 实现原理分析](https://juejin.cn/post/7255561917682991163)
- [依赖注入手册](https://github.com/midwayjs/injection/wiki#%E4%BE%9D%E8%B5%96%E6%B3%A8%E5%85%A5%E6%89%8B%E5%86%8C)
- [这一次，教你从零开始写一个 IoC 容器](https://mp.weixin.qq.com/s/g07BByYS6yD3QkLsA7zLYQ)
- [控制反转 Ioc，依赖注入 DI 如何实现的？](https://www.cnblogs.com/EnSnail/p/14774565.html)

### Chromium
- [The Anatomy of a Frame](https://aerotwist.com/blog/the-anatomy-of-a-frame/)
- [使用 RAIL 模型衡量性能](https://web.dev/articles/rail?hl=zh-cn)
- [Chromium History Versions Download](https://vikyd.github.io/download-chromium-history-version/#/)
- [Sandbox](https://chromium.googlesource.com/chromium/src/+/HEAD/docs/design/sandbox.md)
- [RenderingNG 架构概览](https://developer.chrome.com/docs/chromium/renderingng-architecture?hl=zh-cn)
- [浏览器的工作方式](https://web.dev/articles/howbrowserswork?hl=zh-cn#Layered_representation)
- [How Chromium Displays Web Pages](https://www.chromium.org/developers/design-documents/displaying-a-web-page-in-chrome/)
- [Multi-process Resource Loading](https://www.chromium.org/developers/design-documents/multi-process-resource-loading/)
- [Threading and Tasks in Chrome](https://chromium.googlesource.com/chromium/src.git/+/HEAD/docs/threading_and_tasks.md)
- [Chromium architecture overview](https://szeged.github.io/sprocket/architecture_overview.html)
- [Browser process - detailed architecture overview](https://szeged.github.io/sprocket/browser_process.html)
- [Blink (Rendering Engine)](https://www.chromium.org/blink/)
- [Blink-in-JavaScript](https://docs.google.com/document/d/13cT9Klgvt_ciAR3ONGvzKvw6fz9-f6E0FrqYFqfoc8Y/edit)
- [Blink-in-JavaScript（PPT）](https://browser.alibaba-inc.com/?Url=https://docs.google.com/presentation/d/1XvZdAF29Fgn19GCjDhHhlsECJAfOR49tpUFWrbtQAwU/htmlpresent)
- [Life of a Pixel](https://docs.google.com/presentation/d/1boPxbgNrTU0ddsc144rcXayGA_WF53k96imRH8Mp34Y/edit#slide=id.ga884fe665f_64_1535)
- [Mojo](https://chromium.googlesource.com/chromium/src/+/master/mojo/README.md)
- [Intro to Mojo & Services](https://chromium.googlesource.com/chromium/src/+/HEAD/docs/mojo_and_services.md)
- [Mojo Core Embedder API](https://chromium.googlesource.com/chromium/src/+/HEAD/mojo/core/embedder/README.md)
- [Mojo & Servicification Performance Notes](https://docs.google.com/document/d/1n7qYjQ5iy8xAkQVMYGqjIy_AXu2_JJtMoAcOOupO_jQ/edit)
- [Network Service](https://chromium.googlesource.com/chromium/src/+/HEAD/services/network/README.md)
- [network::mojom::URLLoader 101](https://docs.google.com/presentation/d/1ku7pkh09h6sQ6epudsVvHehRzvanAU7ckzfiVvMoljo/edit#slide=id.g84d512bbb7_0_78)
- [Network Service in Chrome](https://docs.google.com/document/d/1wAHLw9h7gGuqJNCgG1mP1BmLtCGfZ2pys-PdZQ1vg7M/edit?pref=2&pli=1#heading=h.3p2pizkn33qh)
- [Life of a URLRequest](https://www.cnblogs.com/bigben0123/p/12620889.html)
- [Explore the Magic Behind Google Chrome](https://zicodeng.medium.com/explore-the-magic-behind-google-chrome-c3563dbd2739)
- [How do the Render Engine and JavaScript Engine Communicate in a browser?](https://stackoverflow.com/questions/68325731/how-do-the-render-engine-and-javascript-engine-communicate-in-a-browser)
- [Blink architecture overview](https://chromium.googlesource.com/chromium/src/+/master/third_party/blink/renderer/README.md)
- [Blink Binding V8 API](https://source.chromium.org/chromium/chromium/src/+/main:third_party/blink/renderer/platform/bindings/?q=platform%2Fbindings&ss=chromium)
- [Window 上下文创建源码](https://source.chromium.org/chromium/chromium/src/+/main:third_party/blink/renderer/bindings/core/v8/local_window_proxy.cc;l=216;drc=3127e1f4ea87c8ef4238ad4762e856754f0d0675)
- [Understanding Asynchronous JavaScript](https://blog.bitsrc.io/understanding-asynchronous-javascript-the-event-loop-74cd408419ff)
- [Introduction to web APIs](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Introduction)
- [V8 Binding Explained](https://docs.google.com/presentation/d/1OFG81taxgjOGU43sv9WHvPZkt5--KnM6gSijWN8NMcU/edit#slide=id.p)
- [Web IDL Standard](https://webidl.spec.whatwg.org/#introduction)
- [WebKitIDL – WebKit](https://trac.webkit.org/wiki/WebKitIDL)
- [JavaScript 运行机制详解：再谈 Event Loop](https://www.ruanyifeng.com/blog/2014/10/event-loop.html)
- [C++ std::thread Event Loop with Message Queue and Timer](https://www.codeproject.com/Articles/1169105/Cplusplus-std-thread-Event-Loop-with-Message-Queue)
- [Event Loop](https://gist.github.com/kassane/f2330ef44b070f4a5fa9d59c770f68e9)
- [Mitigating Spectre with Site Isolation in Chrome](https://security.googleblog.com/2018/07/mitigating-spectre-with-site-isolation.html)
- [适用于 Web 开发者的网站隔离功能](https://developer.chrome.com/blog/site-isolation?hl=zh-cn)
- [多进程架构](https://www.cntofu.com/book/101/zh/Start_Here_Background_Reading/Multi-process_Architecture.md)
- [Chrome/Chromium 沙箱 - 安全架构设计](https://cloud.tencent.com/developer/article/1009457)
- [Cross-Origin Read Blocking (CORB)](https://chromium.googlesource.com/chromium/src/+/master/services/network/cross_origin_read_blocking_explainer.md)
- [Cross-Origin Read Blocking for Web Developers](https://www.chromium.org/Home/chromium-security/corb-for-developers/)
- [了解“同网站”和“同源”](https://web.dev/articles/same-site-same-origin?hl=zh-cn)
- [往返缓存](https://web.dev/articles/bfcache?hl=zh-cn)
- [为什么需要“跨源隔离”来实现强大的功能](https://web.dev/articles/why-coop-coep?hl=zh-cn)
- [使用 COOP 和 COEP 将网站设置为“跨源隔离”](https://web.dev/articles/coop-coep?hl=zh-cn)
- [关于启用跨域隔离的指南](https://web.dev/articles/cross-origin-isolation-guide?hl=zh-cn)
- [跨域隔离概览](https://developer.chrome.com/blog/enabling-shared-array-buffer?hl=zh-cn#cross-origin-isolation)
- [Inside look at modern web browser (part 1)](https://developer.chrome.com/blog/inside-browser-part1/)
- [Inside look at modern web browser (part 2)](https://developer.chrome.com/blog/inside-browser-part2/)
- [Inside look at modern web browser (part 3)](https://developer.chrome.com/blog/inside-browser-part3/)
- [Inside look at modern web browser (part 4)](https://developer.chrome.com/blog/inside-browser-part4/)
- [Chromium 中文文档](https://github.com/ahangchen/Chromium_doc_zh)
- [多进程架构](https://www.chromium.org/developers/design-documents/multi-process-architecture/)
- [沙箱隔离](https://chromium.googlesource.com/chromium/src/+/HEAD/docs/design/sandbox.md)
- [站点隔离](https://www.chromium.org/developers/design-documents/site-isolation/)
- [How Blink works](https://docs.google.com/document/d/1aitSOucL0VHZa9Z2vbRJSyAIsAz24kX8LFByQ5xQnUg/edit#heading=h.v5plba74lfde)
- [event-loop](https://github.com/atotic/event-loop)
### TypeScript
- [Centralized Recommendations for TSConfig bases](https://github.com/tsconfig/bases)
- [TypeScript](https://www.typescriptlang.org/)
- [深入理解 TypeScript](https://jkchao.github.io/typescript-book-chinese/)
- [TypeScript 高级技巧](https://juejin.cn/post/6844903863791648782)
- [TypeScript Deep Dive](https://basarat.gitbook.io/typescript/getting-started)
- [TypeScript 入门教程](https://ts.xcatliu.com/)
- [3 Ways to Implement TypeScript Into Your Project](https://medium.com/isovera/3-ways-to-implement-typescript-into-your-project-39a2c9d7f850)
- [TS 常见问题整理（60 多个，持续更新 ing）](https://juejin.im/post/5e33fcd06fb9a02fc767c427)
- [使用 TypeScript 装饰器装饰你的代码](https://juejin.im/post/5d15e13fe51d45108f254242)
### JavaScript
- [使用 requestIdleCallback](https://developer.chrome.com/blog/using-requestidlecallback?hl=zh-cn#using-requestidlecallback-to-make-dom-changes)
- [browsing-context](https://www.w3.org/html/wg/spec/browsers.html#browsing-context)
- [深入理解 JavaScript 执行上下文](https://segmentfault.com/a/1190000023216555)
- [\[译\] 理解 JavaScript 中的执行上下文和执行栈](https://muyiy.cn/blog/1/1.1.html)
- [JavaScript 深入之执行上下文](https://github.com/mqyqingfeng/Blog/issues/8)
- [JavaScript 深入之执行上下文栈](https://github.com/mqyqingfeng/Blog/issues/4)
- [JavaScript 深入之变量对象](https://github.com/mqyqingfeng/Blog/issues/5)
- [一文搞清 Javascript 中的「上下文」](https://segmentfault.com/a/1190000020732949)
- [CommonJS，AMD，CMD，ESM 模块化规范详述](https://juejin.cn/post/7008727517716545550#heading-7)
- [Labeled statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/label)
- [Results for js web frameworks benchmark](https://krausest.github.io/js-framework-benchmark/2023/table_chrome_119.0.6045.105.html)
- [highlight.js](https://github.com/highlightjs/highlight.js)
- [es-module-shims](https://github.com/guybedford/es-module-shims)
- [history](https://github.com/remix-run/history)
- [path-to-regexp](https://github.com/pillarjs/path-to-regexp)
- [licia](https://github.com/liriliri/licia)
- [ECMAScript 6 入门](https://es6.ruanyifeng.com/#README)
- [ES modules: A cartoon deep-dive](https://hacks.mozilla.org/2018/03/es-modules-a-cartoon-deep-dive/)（[中文翻译](https://segmentfault.com/a/1190000014318751)）
- [Tasks, microtasks, queues and schedules](https://jakearchibald.com/2015/tasks-microtasks-queues-and-schedules/)（宏任务、微任务、队列）
- [lodash](https://lodash.com/)
- [JavaScript 与有限状态机](http://www.ruanyifeng.com/blog/2013/09/finite-state_machine_for_javascript.html)
- [模块化规范之 ES Modules && CommonJS 规范](https://juejin.cn/post/6954899532689702926)
- [CommonJS 和 ES6 Module 究竟有什么区别？](https://juejin.cn/post/6844904080955932680)
- [CommonJS 和 ES6 Module 模块规范原理浅析](https://juejin.cn/post/6844904159385239566)
- [ECMAScript 规范的中文翻译](https://ecma262.docschina.org/)
- [前端基础漫游指南](https://cheogo.github.io/learn-javascript/)
- [前端工程师手册](https://leohxj.gitbooks.io/front-end-database/content/index.html)
- [JS 内存模型](https://www.yuque.com/airing/fe-note/tm7iq0?language=zh-cn)
- [每周一个 npm 轮子学习之 lru-cache](https://juejin.cn/post/7017742339300917255)
- [codemirror](https://codemirror.net/)
- [debug](https://github.com/debug-js/debug)
- [perfect-scrollbar](https://github.com/mdbootstrap/perfect-scrollbar#options)
- [superagent](https://github.com/visionmedia/superagent)
- [jQuery](https://jquery.com/)
- [zTree](https://github.com/zTree/zTree_v3)
- [\[译\] SuperAgent 中文使用文档](https://cnodejs.org/topic/5378720ed6e2d16149fa16bd)
- [InversifyJS 中文文档](https://github.com/NeoYo/inversify.cn)
- [RxJS 中文](https://cn.rx.js.org/)
- [RxJS](https://rxjs.dev/)
- [Redux-observable](https://redux-observable.js.org/)
- [Redux-observable 中文](https://redux-observable-cn.js.org/)
- [使用 redux-observable 实现组件自治](https://juejin.cn/post/6844903661684932616)
- [RxJS 与 Redux 结合使用（一）：打造自己的 redux-observable](https://juejin.cn/post/6844903758334263309)
- [学习 RxJS](https://rxjs-cn.github.io/learn-rxjs-operators/)
- [moroshko/rxviz: Rx Visualizer - Animated playground for Rx Observables](https://github.com/moroshko/rxviz?spm=ata.13261165.0.0.63a274fcUITUH1)
- [RxViz - Animated playground for Rx Observables](https://rxviz.com/)
- [jaredly/rxvision: visualizer debugger for reactive streams](https://github.com/jaredly/rxvision)
- [staltz/rxmarbles: Interactive diagrams of Rx Observables](https://github.com/staltz/rxmarbles?spm=ata.13261165.0.0.63a274fcUITUH1)
- [RxMarbles: Interactive diagrams of Rx Observables](https://rxmarbles.com/#delayWhen)
- [渔人和 Rxjs 的故事,这次一定教会你前端必会的 Rxjs](https://juejin.im/post/5bc887ba6fb9a05d265991d5)
- [\[译\] 看动画，学 RxJS](https://juejin.im/post/58cd146a61ff4b0060277d32)
- [RxJS in Action](https://livebook.manning.com/book/rxjs-in-action/chapter-1/)
- [RxJS-CN/rxjs-articles-translation: RxJS 优质文章翻译](https://github.com/RxJS-CN/rxjs-articles-translation)
- [RxJS v6 学习指南](https://www.cnblogs.com/ang-/p/9514430.html)
- [RxJS 学习中文资料](https://zhuanlan.zhihu.com/learing-rxjs)
- [全面拥抱 Reactivity: RxJS, RSocket & Svelte](https://mp.weixin.qq.com/s/n2uJ3pLsvhzWI6noo-FrZw)
- [作为前端，你需要知道 RxJS](https://juejin.cn/post/6844904199461797895)
- [canvas 实践小实例二 —— 扇形](https://www.cnblogs.com/liugang-vip/p/5405276.html)
- [深入浅出 JavaScript 异步编程](https://zhuanlan.zhihu.com/p/57548254)
- [JavaScript 异步编程\_前端学习](https://segmentfault.com/a/1190000015711829)
- [JavaScript 知识图谱：ECMAScript、DOM、BOM、HTML5、计算机网络](https://tsejx.github.io/javascript-guidebook/)
- [从浏览器多进程到 JS 单线程，JS 运行机制最全面的一次梳理](https://mp.weixin.qq.com/s/vIKDUrbuxVNQMi_g_fiwUA)
- [如何实现一个深拷贝](https://juejin.im/post/5c45112e6fb9a04a027aa8fe)
- [Object()的方法一览](https://juejin.im/post/5937699efe88c20061eb412d)
- [Promise 之你看得懂的 Promise](https://juejin.im/post/5b32f552f265da59991155f0)
- [深入理解 JavaScript 的类型转换](https://juejin.im/post/5d1587f4e51d4510664d1715)
- [【JS 进阶】你真的掌握变量和类型了吗](https://juejin.im/post/5cec1bcff265da1b8f1aa08f)
- [记一次面试题，正则表达式(?=a)是什么意思？](https://juejin.im/post/5ceb7d9df265da1b8811ba7f)
- [【JS 迷你书】类型转换之拆箱操作](https://juejin.im/post/5ccfb58f518825405a198fcd)
- [《三分钟阅读》7 个有用的 JavaScript 技巧](https://juejin.im/post/5cc6f07ce51d456e3a5f089b)
- [我是如何将业务代码写优雅的](https://juejin.im/post/5cc7d540e51d456e537ef39e)
- [JS 中的 null 和 undefined,undefined 为啥用 void 0 代替?](https://juejin.im/post/5cc58a72e51d456e845b4289)
- [async/await 优雅的错误处理方法](https://juejin.im/post/5c49eb28f265da613a545a4b)
- [JavaScript 代码简洁之道](https://juejin.im/post/5c24b7a851882509a76875e8)
### HTML
- [利用废弃的 html rel import 实现页面 include 功能](https://www.zhangxinxu.com/wordpress/2021/07/html-rel-import-include/)
- [盘点 HTML 字符串转 DOM 的各种方法及细节](https://www.zhangxinxu.com/wordpress/2021/02/html-string-dom/)
- [Javascript Import maps](https://www.jianshu.com/p/b23d823a183a)
- [浏览器沙盒是什么](https://www.cnblogs.com/lovesong/p/5087423.html)
- [浏览器沙箱模型](https://www.cnblogs.com/slly/p/6639173.html)
- [你真的了解回流和重绘吗](https://juejin.im/post/5c6cb7b4f265da2dae511a3d)
- [浏览器的回流与重绘 (Reflow & Repaint)](https://juejin.im/post/5a9923e9518825558251c96a)
### iframe
- [X-Frame-Options](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/X-Frame-Options)
- [nginx 解决跨域问题嵌入第三方页面](https://juejin.cn/post/6996211874324824072)
- [终于搞懂了 Iframe （跨窗口通信）](https://juejin.cn/post/7127916577684471845)
- [iframe 跨域传递 cookie](https://juejin.cn/post/6904468647037632520)
- [你不了解的 iframe](https://juejin.cn/post/6994433279289999374#heading-9)
### Web Component
- [深入理解 Shadow DOM v1](https://segmentfault.com/a/1190000019115050)
- [你想要了解的 Shadow DOM 都在这里](https://juejin.cn/post/6979489951108825095)
- [声明式 Shadow DOM](https://developer.chrome.com/docs/css-ui/declarative-shadow-dom?hl=zh-cn)
- [在 React 中使用 WebComponents 组件的最佳实践](https://juejin.cn/post/7016870673658167310)
- [你不知道的 Web Components - 过去和未来](https://www.albertaz.com/blog/web-component-history-and-future)
- [polyfills](https://github.com/webcomponents/polyfills)
- [Web Component](https://developer.mozilla.org/zh-CN/docs/Web/Web_Components)
- [Web Components 入门实例教程](http://www.ruanyifeng.com/blog/2019/08/web_components.html)
### CSS
- [CSS Modules 用法教程](https://www.ruanyifeng.com/blog/2016/06/css_modules.html)
- [BEM](https://link.juejin.cn/?target=https%3A%2F%2Fen.bem.info%2F)（Class 命名规范）
- [CSS](https://link.juejin.cn/?target=https%3A%2F%2Fdeveloper.mozilla.org%2Fzh-CN%2Fdocs%2FLearn%2FCSS)（MDN web docs）
- [Flex 布局教程](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)
- [Less 中文网](https://less.bootcss.com/)
- [Sass](https://link.juejin.cn/?target=https%3A%2F%2Fsass-lang.com%2F)
- [PostCSS](https://link.juejin.cn/?target=https%3A%2F%2Fpostcss.org%2F)
- [SASS 用法指南](https://www.ruanyifeng.com/blog/2012/06/sass.html)
- [CSS in JS 简介](http://www.ruanyifeng.com/blog/2017/04/css_in_js.html)
- [FLEXBOX FROGGY](http://flexboxfroggy.com/#zh-cn)（学 Flex 的小游戏）

### React
- [Next.js](https://nextjs.org/docs/getting-started/installation)
- [手摸手实现 react-router](https://yingchenit.github.io/react/react-router/#%E5%89%8D%E7%AB%AF%E8%B7%AF%E7%94%B1%E5%88%9D%E8%AE%A4%E8%AF%86)
- [从路由原理出发，深入阅读理解 react-router 4.0 的源码](https://github.com/forthealllight/blog/issues/26)
- [前端路由实现与 react-router 源码分析](https://976500133.gitbooks.io/frontendbook/content/react/js-react-router.html)
- [「源码解析 」这一次彻底弄懂 react-router 路由原理](https://blog.csdn.net/zl_Alien/article/details/109231294)
- [30 分钟精通 React Hooks](https://juejin.cn/post/6844903709927800846)
- [react-worker-dom](https://github.com/web-perf/react-worker-dom)
- [react-app-rewired](https://github.com/timarney/react-app-rewired)（覆盖 Create React App 的 Webpack）
- [customize-cra](https://github.com/arackaf/customize-cra)（覆盖 Create React App 的 Webpack）
- [React Query](https://github.com/TanStack/query)（React Hook 请求库）
- [swr](https://github.com/vercel/swr)（React Hook 请求库）
- [React](https://zh-hans.reactjs.org/)
- [Create React App 中文文档](https://www.html.cn/create-react-app/)
- [React Router](https://reactrouter.com/)
- [Redux](https://redux.js.org/)
- [Redux Toolkit](https://redux-toolkit.js.org/introduction/quick-start)
- [React Lifecycle](http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/)
- [React Hooks 原理](https://github.com/brickspert/blog/issues/26)
- [How to fetch data with React Hooks?](https://www.robinwieruch.de/react-hooks-fetch-data)
- [React Hooks 完全上手指南](https://github.com/chemdemo/chemdemo.github.io/issues/15)
- [React 的性能优化（一）当 PureComponent 遇上 ImmutableJS](https://segmentfault.com/a/1190000011408775#articleHeader3)
- [React 源码解析](https://react.jokcy.me/)
- [React 源码系列(一): 总结看源码心得及方法感受 #1](https://github.com/jsonz1993/react-source-learn/issues/1)
- [\[译\] React-Redux 官方 Hooks 文档说明](http://react-china.org/t/topic/34076)
- [Redux Toolkit](https://redux-toolkit.js.org/)
- [reduxjs/cra-template-redux: The official Redux+JS template for Create React App](https://github.com/reduxjs/cra-template-redux)
- [redux-toolkit-example-ts](https://github.com/darylwalsh/redux-toolkit-example-ts/tree/master/src)(示例代码)
- [如何管理好 10 万行代码的前端单页面应用](https://juejin.im/post/59cb0d0b5188257e876a2d27)
- [React 的性能优化（一）当 PureComponent 遇上 ImmutableJS](https://segmentfault.com/a/1190000011408775#articleHeader3)
- [\[译\] React-Redux 官方 Hooks 文档说明](http://react-china.org/t/topic/34076)
- [Immutable 操作在 React 中的实践](https://juejin.im/post/5aefff6a518825672a02d7d8)
- [Redux 入门教程（一）：基本用法](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html)
- [Redux 入门教程（二）：中间件与异步操作](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html)
- [Redux 入门教程（三）：React-Redux 的用法](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_three_react-redux.html)
- [How to fetch data with React Hooks?](https://www.robinwieruch.de/react-hooks-fetch-data)
- [2020 年你应该知道的 React 库](https://juejin.im/post/5e4e1b07e51d4527143e44be)
- [React Hooks 究竟有多慢？](https://juejin.im/post/5e3ac653e51d45270b7d4e3d)
- [终于搞懂 React Hooks 了！！！！！](https://juejin.im/post/5e53d9116fb9a07c9070da44)
- [关于 Vue 和 React 的一些对比及个人思考（中）](https://juejin.im/post/5e292746e51d451c8771d16e)
- [React 开发必须知道的 34 个技巧【近 1W 字】](https://juejin.im/post/5dcb5a80e51d4520db19b906)
- [使用 70 行代码配合 hooks 重新实现 react-redux](https://juejin.im/post/5be6150551882511a8526955)
- [使用 React Hooks + Context 打造简版 Redux](https://juejin.im/post/5d5501cd6fb9a06aee362a9d)
- [2019 年了，整理了 N 个实用案例帮你快速迁移到 React Hooks](https://juejin.im/post/5d594ea5518825041301bbcb)
- [React Hooks 详解 【近 1W 字】+ 项目实战](https://juejin.im/post/5dbbdbd5f265da4d4b5fe57d)
- [React16：Hooks 总览，拥抱函数式 (这大概是最全的 React Hooks 吧)](https://juejin.im/post/5cb5705ee51d456e6e38921d)
- [React hooks 实践](https://juejin.im/post/5c4d7122e51d4556940c15cb)
- [30 分钟精通 React Hooks](https://juejin.im/post/5be3ea136fb9a049f9121014)
- [Redux-thunk 快速入门](https://juejin.im/post/5b035c0c51882565bd258f12)
- [Immutable 操作在 React 中的实践](https://juejin.im/post/5aefff6a518825672a02d7d8)
- [使用 redux-observable 实现组件自治](https://juejin.im/post/5b798501f265da43473130a1)
- [React 拾遗：从 10 种现在流行的 CSS 解决方案谈谈我的最爱 （下）](https://juejin.im/post/5b3dd2d25188251b193d2d7e)
- [React 拾遗：从 10 种现在流行的 CSS 解决方案谈谈我的最爱 （上）](https://juejin.im/post/5b39e63ae51d4562aa017c81)
- [\[译\] 关于 React Router 4 的一切](https://juejin.im/post/5995a2506fb9a0249975a1a4)
- [React 路由鉴权](https://juejin.im/post/5d6352116fb9a06ae8361932)
- [react-router4 基于 react-router-config 的路由拆分与按需加载](https://juejin.im/post/5a3880b56fb9a0451a767f07)
- [快速搭建你的 github pages 个人博客 —— 基于 Create-React-App 的单页面应用实践](https://juejin.im/post/5a6e364c518825733c144d67)
- [从 0 到 1 快速构建基于 create-react-app 的脚手架](https://juejin.im/post/5b0374f751882542ba0814f9)
- [【长文慎入】一文吃透 React SSR 服务端渲染和同构原理](https://juejin.im/post/5d7deef6e51d453bb13b66cd)
- [技术胖的 2019 新版 React 全家桶免费视频（84 集）](https://juejin.im/post/5d817a15f265da039929a761)
- [React 组件设计实践总结 02 - 组件的组织](https://juejin.im/post/5cd8fb916fb9a03218556fc1)
- [React 组件设计实践总结 01 - 类型检查](https://juejin.im/post/5cd7f2c4e51d453a7d63b715)
- [\[译\] 2019 React Redux 完全指南](https://juejin.im/post/5cac8ccd6fb9a068530111c7)
- [掘金最污的 React16.x 图文视频教程(2 万 5 千字长文-慎入)](https://juejin.im/post/5d085be0f265da1bac401937)
### Vue
- [尤雨溪 - 在框架设计中寻求平衡 | JSConf.Asia 2019](https://www.bilibili.com/video/av80042358/)
- [vue-markdown-loader](https://github.com/QingWei-Li/vue-markdown-loader)
- [vitepress](https://github.com/vuejs/vitepress)（静态文档生成）
- [Vue.js 3 中文](https://v3.cn.vuejs.org/)
- [Vuex](https://vuex.vuejs.org/zh/)
- [Vue Router](https://router.vuejs.org/zh/)
- [Vue CLI](https://cli.vuejs.org/zh/)
- [Vue Loader](https://vue-loader.vuejs.org/zh/guide/#vue-cli)
- [Vue.js](https://staging-cn.vuejs.org/)
- [Vue 插件开发指南](https://cli.vuejs.org/zh/dev-guide/plugin-dev.html)
- [eslint-plugin-vue](https://eslint.vuejs.org/)
- [VuePress](https://v2.vuepress.vuejs.org/zh/) (Vue 驱动的静态网站生成器)
- [剖析 Vue.js 内部运行机制](https://github.com/answershuto/learnVue)
- [DMQ/MVVM](https://github.com/DMQ/mvvm/issues)(剖析 Vue 实现原理，如何实现双向绑定 mvvm)
- [深度剖析：如何实现一个 Virtual DOM 算法](https://github.com/livoras/blog/issues/13)
- [Vue.js 技术揭秘](https://ustbhuangyi.github.io/vue-analysis/)
- [Vue SSR 指南](https://ssr.vuejs.org/zh/)
- [Nuxt](https://zh.nuxtjs.org/guide/installation/) (Vue.js 服务端渲染)
- [Vue Apollo](https://apollo.vuejs.org/zh-cn/) (在 Vue.js 应用中集成 GraphQL)
- [Vue I18n](http://kazupon.github.io/vue-i18n/) (国际化插件)
- [Vue Test Utils](https://vue-test-utils.vuejs.org/) （Vue.js 官方的单元测试实用工具库）
- [vue-cli-plugin-i18n](https://github.com/kazupon/vue-cli-plugin-i18n)
- [nuxt-property-decorator](https://github.com/nuxt-community/nuxt-property-decorator)
- [为什么 Proxy 可以优化 vue 的数据监听机制](https://juejin.im/post/5bfe3360518825653a231f33)
- [Vue.js 的 computed 和 watch 是如何工作的？](https://juejin.im/post/5b87f13bf265da436479f3c1)
- [深入理解 Vue 的 watch 实现原理及其实现方式](https://juejin.im/post/5af908ea5188254265399009)
- [vue + typescript 新项目起手式](https://segmentfault.com/a/1190000011744210)(Vue 2.x 版本)
- [vue + typescript 进阶篇](https://segmentfault.com/a/1190000011878086)(Vue 2.x 版本)
- [美团点评点餐 Nuxt.js 实战](https://juejin.im/post/598aabe96fb9a03c335a8dde#heading-10)(Vue 2.x 版本)
- [浅谈使用 Vue 构建前端 10w+ 代码量的单页面应用开发底层](https://juejin.im/post/5b29c3bde51d45588d4d7110)(Vue 2.x 版本)
- [Vue2.0 探索之路——生命周期和钩子函数的一些理解](https://segmentfault.com/a/1190000008010666)(Vue 2.x 版本)
- [vue-cli3 项目从搭建优化到 docker 部署](https://juejin.im/post/5c4a6fcd518825469414e062)(Vue 2.x 版本)
- [离职后才搞懂 vue 项目开发流程中的疑惑点](https://juejin.im/post/5c488a3cf265da615705cc2a)(Vue 2.x 版本)
- [Vuex 带来全新的编程体验](https://juejin.im/post/5c3c911ce51d455231347a7a)(Vue 2.x 版本)
- [vue-cli3 从搭建到优化](https://juejin.im/post/5c3c544c6fb9a049d37f5903)(Vue 2.x 版本)
- [少年，撸猫吗](https://juejin.im/post/5d5137066fb9a06b2a203214)(Vue 2.x 版本)
- [结合 vue-cli 来谈 webpack 打包优化](https://juejin.im/post/5c3c55aa51882524b4073394)(Vue 2.x 版本)
### Svelte
- [Svelte 官网](https://svelte.dev/)
- [Svelte 教程](https://learn.svelte.dev/tutorial/welcome-to-svelte)
- [Virtual DOM is pure overhead](https://www.svelte.cn/blog/virtual-dom-is-pure-overhead)
- [Rethinking reactivity](https://svelte.dev/blog/svelte-3-rethinking-reactivity)
- [Rethinking "Rethinking Reactivity" - Svelte 5 Introduces Runes](https://www.infoq.com/news/2023/10/svelte-5-runes/)
- [Introducing runes](https://svelte.dev/blog/runes)
- [The Svelte Compiler Handbook](https://lihautan.com/the-svelte-compiler-handbook/)（Svelte 编译原理手册）
- [看完 Svelte 纪录片才知道它为什么在国外比国内火](https://101.34.7.216/articles/2290)
- [前端新宠 Svelte 带来哪些新思想？赶紧学起来！](https://juejin.cn/post/7121759118070644772?searchId=2023110613460266324222B0B276D8AB10)
- [Svelte 的异步更新实现原理](https://lutaonan.com/blog/how-svelte-set-state-works/)

### HTTP
- [Hypertext Transfer Protocol (HTTP/1.1): Conditional Requests](https://httpwg.org/specs/rfc7232.html#weak.and.strong.validators)
- [HTTP/1.1: Caching in HTTP](https://www.w3.org/Protocols/rfc2616/rfc2616-sec13.html)
- [Resource Hints](https://www.w3.org/TR/2023/DISC-resource-hints-20230314/)
- [SameSite 那些事](https://juejin.cn/post/6972365776334536718)
- [深入理解 Cookie 的 SameSite 属性](https://juejin.cn/post/6963632513914765320)
- [本地 https 环境解决方案](https://www.cnblogs.com/himeka/p/16727954.html)
- [内网穿透神器-Serveo](https://www.jianshu.com/p/d0b3991a9ce1)
- [swr](https://github.com/vercel/swr)（React Hooks for Data Fetching）
- [缓存](https://alienzhou.github.io/fe-performance-journey/1-cache/#_1-%E6%9C%AC%E5%9C%B0%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8)
- [HTTP 缓存（附 Express 实现代码）](https://github.com/lilins/Blog/issues/4)
- [使用反向代理进行内网穿透](https://www.zhihu.com/tardis/zm/art/86886234?source_id=1003)
- [【PWA 学习与实践】(3) 让你的 WebApp 离线可用](https://juejin.cn/post/6844903588691443725)
- [HTTP/2 push is tougher than I thought](https://jakearchibald.com/2017/h2-push-tougher-than-i-thought/)
- [浏览器的强缓存和协商缓存](https://segmentfault.com/a/1190000021661656)
- [生产环境浏览器 Strict MIME TYPE Checking 问题解决](https://blog.csdn.net/zhuyiquan/article/details/52173735)
- [同站 和 同源 你理解清楚了么？](https://cloud.tencent.com/developer/article/1651506)
- [内容安全策略（CSP）](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/CSP)
- [计算机通识](https://yuchengkai.cn/docs/cs/#udp)
- [跨域资源共享 CORS 详解](http://www.ruanyifeng.com/blog/2016/04/cors.html)（阮一峰）
- [浏览器缓存知识小结及应用](http://www.cnblogs.com/lyzg/p/5125934.html?from=cnblogs)
- [GET 方法与 POST 方法的区别](https://www.cnblogs.com/sunny-sl/p/6529830.html)
- [图解：HTTP 范围请求，助力断点续传、多线程下载的核心原理](https://juejin.im/post/5b555f055188251af25700aa)
- [资源预加载 - 性能优化需知~](https://segmentfault.com/a/1190000022194251)
- [用 preload 预加载页面资源](https://juejin.cn/post/6844903562070196237)
- [preload 和 prefetch](https://juejin.cn/post/6844903721504079880#heading-3)
- [Cookie](https://github.com/YBFACC/blog/issues/9)
- [彻底明白 ip 地址，区分 localhost、127.0.0.1 和 0.0.0.0](https://blog.csdn.net/liyi1009365545/article/details/84780476)
- [前端跨域整理](https://juejin.im/post/5815f4abbf22ec006893b431)
### Git
- [Github Copilot](https://github.com/features/copilot/)
- [使用 git hooks 钩子实现 gitlab 的代码服务器自动更新](https://blog.csdn.net/qq_24909089/article/details/103770900)
- [ghooks](https://github.com/ghooks-org/ghooks)
- [AngularJS Git Commit Message Conventions](https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit)
- [A Note About Git Commit Messages](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)
- [Writing Git commit messages](https://365git.tumblr.com/post/3308646748/writing-git-commit-messages)
- [husky](https://github.com/typicode/husky)（Git 钩子配置工具）
- [Simple Git](https://github.com/steveukx/git-js)（Node.js 的 Git 命令封装）
- [Git 教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)(廖雪峰)
- [Your AI pair programmer](https://copilot.github.com/)
- [commit_msg](https://git-scm.com/docs/githooks#_commit_msg)(git 钩子文档)
- [语义化版本 2.0.0](https://semver.org/lang/zh-CN/)(语义化版本控制规范)
- [Git 分支 - 变基](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%8F%98%E5%9F%BA)
- [cz-cli](https://github.com/commitizen/cz-cli)(cz 工具)
- [cz-customizable](https://github.com/leonardoanalista/cz-customizable)(cz 适配器)
- [@commitlint/config-conventional](https://github.com/marionebl/commitlint/tree/master/@commitlint/config-conventional)(cz 适配器)
- [commitlint](https://github.com/marionebl/commitlint)(cz 校验工具)
- [commitlint-config-cz](https://github.com/whizark/commitlint-config-cz)(cz 校验工具的校验规则)
- [validate-commit-msg](https://github.com/Frikki/validate-commit-message)(cz 校验工具)
- [conventional-changelog](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog)(cz 日志生成器)

### NPM & Yarn
- [npm 的 package.json 和 package-lock.json 更新策略](https://blog.csdn.net/weixin_43820866/article/details/105232066)
- [Compare package download counts over time](https://npmtrends.com/)
- [Life Cycle Scripts](https://docs.npmjs.com/cli/v9/using-npm/scripts#life-cycle-scripts)
- [npm ci](https://docs.npmjs.com/cli/v7/commands/npm-ci)（CI / CD 依赖安装）
- [npm update](https://docs.npmjs.com/cli/v9/commands/npm-update)（依赖升级）
### 版本规范
- [semver 2.0.0](https://semver.org/lang/zh-CN/)
- [node-semver](https://github.com/npm/node-semver#versions)
- [semantic-release](https://github.com/semantic-release/semantic-release)
### Node.js
- [source-map](https://github.com/mozilla/source-map/)（Sourcemap 解析工具）
- [Security, Modules and Node.js](https://docs.google.com/presentation/d/1VUpxoxitZCINJI7jXec4i87YiYZsXr8pCSHdHY5pW30/edit#slide=id.g587899af2a_0_21)
- [How does Node.js work?](https://blog.ghaiklor.com/2015/08/23/how-does-node.js-work/)
- [nvm](https://github.com/nvm-sh/nvm)（Node 版本管理工具）
- [lint-md](https://github.com/lint-md/lint-md)（Markdown 格式校验工具）
- [minimist](https://github.com/minimistjs/minimist)（轻量的命令参数解析）
- [zx](https://github.com/google/zx)（Google 出品的 Shebang 助力器）
- [shelljs](https://github.com/shelljs/shelljs)（Shell 脚本封装）
- [tasklist](https://github.com/sindresorhus/tasklist)（Windows tasklist 命令封装）
- [taskkill](https://github.com/sindresorhus/taskkill)（Windows taskkill 命令封装）
- [execa](https://github.com/sindresorhus/execa)（child_process 增强）
- [open](https://github.com/sindresorhus/open)（打开浏览器 URL、文件和可执行文件）
- [ws](https://github.com/websockets/ws)（WebSocket 通信）
- [node-http-proxy](https://github.com/http-party/node-http-proxy)（代理转发）
- [ngrok](https://github.com/bubenshchykov/ngrok)（内网穿透 & 代理）
- [download](https://github.com/rndme/download)（下载提取文件）
- [abort-controller](https://github.com/mysticatea/abort-controller)（取消请求）
- [portfinder](https://github.com/http-party/node-portfinder)（空闲端口发现器）
- [node-ip](https://github.com/indutny/node-ip)（IP 地址工具）
- [http-proxy-middleware](https://github.com/chimurai/http-proxy-middleware)（网络代理中间件）
- [AnyProxy](https://github.com/alibaba/anyproxy)（Node.js 网络代理工具）
- [decompress](https://github.com/kevva/decompress)（文件解压缩）
- [compression](https://github.com/expressjs/compression)（文件压缩）
- [form-data](https://github.com/form-data/form-data)（表单数据流，可用于上传文件）
- [node-progress](https://github.com/visionmedia/node-progress)（进度条打印）
- [winston](https://github.com/winstonjs/winston)（日志）
- [find-root](https://github.com/junosuarez/find-root)（发现 package.json 所在目录层级）
- [dotenv](https://github.com/motdotla/dotenv)（环境变量处理）
- [ejs](https://github.com/mde/ejs)（模板引擎）
- [uid](https://github.com/lukeed/uid)（固定长度的 id 生成器）
- [parse-json](https://github.com/sindresorhus/parse-json)（解析 JSON 携带详细的错误信息）
- [node-qrcode](https://github.com/soldair/node-qrcode)（二维码生成器）
- [cheerio](https://github.com/cheeriojs/cheerio)（JQuery API 的服务端实现）
- [normalize-package-data](https://github.com/npm/normalize-package-data)（规范化 package.json 元数据）
- [strip-ansi](https://github.com/chalk/strip-ansi)（去除 ANSI 转义码）
- [url-join](https://github.com/jfromaniello/url-join)（URL 规范化拼接）
- [node-regedit](https://github.com/ironSource/node-regedit)（Windows 注册表）
- [htmlparser2](https://github.com/fb55/htmlparser2)（HTML & XML 解析器）
- [parse5](https://github.com/inikulin/parse5)（HTML 解析器）
- [Node.js](http://nodejs.cn/api/)
- [ts-node](https://github.com/TypeStrong/ts-node)
- [NodeJS 开发工具栈](https://adoyle.me/my-development-tools/nodejs/)\[Awesome\]（开发工具箱）
- [awesome-nodejs](https://github.com/sindresorhus/awesome-nodejs)\[Awesome\]
- [mongoose](https://mongoosejs.com/)
- [mongoose 中文](http://www.mongoosejs.net/)
- [ORM 实例教程](http://www.ruanyifeng.com/blog/2019/02/orm-tutorial.html)
- [TypeORM](https://github.com/typeorm/typeorm)
- [TypeORM 中文](https://typeorm.biunav.com/zh/)
- [linkerd2](https://linkerd.io/)
- [Express](https://expressjs.com/zh-cn/)
- [Koa](https://koa.bootcss.com/)
- [Egg](https://eggjs.org/zh-cn/index.html)
- [Socket.io](https://socket.io/#examples)
- [Node Redis](https://redis.js.org/)
- [Midway](https://midwayjs.org/)
- [GraphQL](https://graphql.github.io/)
- [Prisma OSS Documentation](https://oss.prisma.io/)
- [Apollo Client](https://www.apollographql.com/docs/react/)
- [node-inspector](https://github.com/node-inspector/node-inspector)（Node.js debugger based on Blink Developer Tools）
- [execa](https://github.com/sindresorhus/execa)
- [parse-json](https://github.com/sindresorhus/parse-json)
- [gitbeaker](https://github.com/jdalrymple/gitbeaker)
- [node-fetch](https://github.com/node-fetch/node-fetch)
- [node-inspector](https://github.com/node-inspector/node-inspector)
- [Mongoose the Typescript way…?](https://stackoverflow.com/questions/34482136/mongoose-the-typescript-way)
- [使用 TypeScript 开发 Node.js](https://juejin.im/entry/59c09867f265da06560457c3)
- [30 分钟理解 GraphQL 核心概念](https://segmentfault.com/a/1190000014131950)
- [Open Sourcing GraphQL Middleware - A Library to Simplify Your Resolvers](https://www.prisma.io/blog/graphql-middleware-zie3iphithxy/)
- [RPC vs REST vs GraphQL](https://segmentfault.com/a/1190000013961872)

### Lint & Prettier
- [TSLint in 2019](https://blog.palantir.com/tslint-in-2019-1a144c2317a9)
- [eslint-loader](https://github.com/webpack-contrib/eslint-loader)
- [eslint-webpack-plugin](https://github.com/webpack-contrib/eslint-webpack-plugin)
- [Why Prettier?](https://prettier.io/docs/en/why-prettier.html)
- [Prettier vs. Linters](https://prettier.io/docs/en/comparison.html)
- [eslint-plugin-jest](https://github.com/jest-community/eslint-plugin-jest)
- [eslint-plugin-tsdoc](https://www.npmjs.com/package/eslint-plugin-tsdoc)
- [markdownlint](https://github.com/DavidAnson/markdownlint)
- [markdownlint-cli](https://github.com/igorshubovych/markdownlint-cli)
- [markdown-it](https://github.com/markdown-it/markdown-it)（Markdown 解析为 HTML）
- [层叠配置](https://eslint.bootcss.com/docs/user-guide/configuring#configuration-cascading-and-hierarchy) (Monorepo 需要注意)
- [typescript-eslint](https://github.com/typescript-eslint/typescript-eslint)（TypeScript 的 ESLint 和 Prettier 工具集）
- [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier#cli-helper-tool)（检查格式规则配置是否存在冲突）
- [lint-staged](https://github.com/okonet/lint-staged)（Git 暂存区代码检查）
- [ESLint](https://cn.eslint.org/)(可组装的 JavaScript 和 JSX 检查工具)
- [ESLint couldn't determine the plugin uniquely.](https://github.com/eslint/eslint/issues/13385)
- [Prettier](https://prettier.io/)(An opinionated code formatter)
### Module Federation
- [Webpack / Module Federation](https://webpack.js.org/concepts/module-federation/)
- [Dynamic Remotes, Webpack Module Federation](https://h3manth.com/posts/dynamic-remotes-webpack-module-federation/)
- [Module Federation: streamline your microfrontends](https://module-federation.io/)
### Babel
- [Babel](https://www.babeljs.cn/)
- [@vue/babel-preset-app](https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/babel-preset-app)(Vue CLI3 的 Babel 插件集)
- [@babel/preset-env](https://github.com/babel/babel/tree/master/packages/babel-preset-env)(Babel 插件集)
- [Deploying ES2015+ Code in Production Today](https://philipwalton.com/articles/deploying-es2015-code-in-production-today/)
- [Why is Babel a monorepo?](https://github.com/babel/babel/blob/master/doc/design/monorepo.md)
### 构建工具
- [【webpack进阶】可视化展示webpack内部插件与钩子关系📈](https://juejin.cn/post/6844903686649413645?searchId=20240201170644FD2785C506B5F5356F20)
- [揭秘webpack loader](https://champyin.com/2020/01/28/%E6%8F%AD%E7%A7%98webpack-loader/)
- [揭秘webpack plugin](https://zhuanlan.zhihu.com/p/102917655)
- [Rspack](https://github.com/web-infra-dev/rspack/blob/main/README.zh-CN.md)
- [parcel](https://github.com/parcel-bundler/parcel)
- [rollup-starter-lib](https://github.com/rollup/rollup-starter-lib)
- [esbuild](https://esbuild.github.io/)（ES6+ 构建）
- [esno](https://github.com/esbuild-kit/esno)（类似于 tsx 的 esbuild 增强）
- [Vite](https://cn.vitejs.dev/)（esbuild + Rollup）
- [SWC](https://swc.rs/)（基于 Rust）
- [minidev](https://opendocs.alipay.com/mini/02q17j)（支付宝小程序构建工具）
### 静态站点生成器
- [dumi](https://d.umijs.org/guide)
- [react-markdown](https://github.com/remarkjs/react-markdown#readme)
- [react-static](https://github.com/react-static/react-static)
- [TSDoc](https://tsdoc.org/)
- [JSDoc](https://jsdoc.app/)
- [JSDoc 中文](https://www.jsdoc.com.cn/)
- [typedoc](https://github.com/TypeStrong/typedoc)
- [vuepress-plugin-typedoc](https://github.com/tgreyuk/typedoc-plugin-markdown/tree/master/packages/vuepress-plugin-typedoc#vuepress-plugin-typedoc)
- [typedoc-plugin-markdown](https://github.com/tgreyuk/typedoc-plugin-markdown/tree/master/packages/typedoc-plugin-markdown#typedoc-plugin-markdown)
- [Shields.io](https://shields.io/)（徽章生成器）
- [README Specification](https://github.com/RichardLitt/standard-readme/blob/main/spec.md#specification)
- [VuePress](https://v2.vuepress.vuejs.org/zh/) (Vue 驱动的静态网站生成器)
### CI / CD
- [Github Action Marketplace](https://github.com/marketplace?type=actions)
- [Learn YAML in five minutes!](https://www.codeproject.com/Articles/1214409/Learn-YAML-in-five-minutes)
- [DingTalk Release Notify](https://github.com/visiky/dingtalk-release-notify)
- [大公司里怎样开发和部署前端代码？](https://www.zhihu.com/question/20790576/answer/32602154)(张云龙)
- [GitHub Actions](https://docs.github.com/en/actions)
- [GitHub Actions 入门教程](http://www.ruanyifeng.com/blog/2019/09/getting-started-with-github-actions.html)（阮一峰）
- [pm2](https://pm2.io/)(The Most Advanced Production Process Manager for Node.js)
- [Jenkins](https://www.jenkins.io/zh/)
- [Jenkins 记录二：远程构建](https://www.jianshu.com/p/81785f65b1d3)
- [Jenkins+Node.js 持续集成](https://www.jianshu.com/p/64b498304d07)
- [nginx](https://nginx.org/en/)

### 测试
- [JavaScript 程序测试](https://javascript.ruanyifeng.com/tool/testing.html)
- [JavaScript unit testing frameworks in 2022: A comparison](https://raygun.com/blog/javascript-unit-testing-frameworks/)
- [javascript-testing-best-practices](https://github.com/goldbergyoni/javascript-testing-best-practices/blob/master/readme-zh-CN.md)
- [ts-jest](https://www.npmjs.com/package/ts-jest)
- [COVERALLS](https://coveralls.io/)（测试报告上传平台）
- [node-coveralls](https://github.com/nickmerwin/node-coveralls)
- [Puppeteer](https://github.com/puppeteer/puppeteer)（无头浏览器）
- [Jest](https://jestjs.io/)
- [javascript-testing-best-practices](https://github.com/goldbergyoni/javascript-testing-best-practices)
- [JavaScript 程序测试](https://javascript.ruanyifeng.com/tool/testing.html)
- [Nightwatch.js](http://nightwatchjs.org/)
- [Mocha](https://mochajs.org/)
- [Chai](https://www.chaijs.com/)
- [Karma](http://karma-runner.github.io/latest/index.html)
- [awesome-jest](https://github.com/jest-community/awesome-jest)\[Awesome\]
- [ui-testing-best-practices](https://github.com/NoriSte/ui-testing-best-practices)

### Chrome DevTools
- [Chrome DevTools Frontend 运行原理浅析](https://zhaomenghuan.js.org/blog/chrome-devtools-frontend-analysis-of-principle.html#%E5%89%8D%E8%A8%80)
- [深入理解 Chrome DevTools](https://zhaomenghuan.js.org/blog/chrome-devtools.html#chrome-devtools)
- [如何定制 chrome 开发者工具](https://songyaru.github.io/doc-backup/devtools/front-end/)
- [玩转 Chrome DevTools，定制自己的调试工具](https://www.51cto.com/article/716801.html)
- [Chrome DevTools 远程调试协议分析及实战](https://blog.csdn.net/LuckyWinty/article/details/105743305)
- [DevTools debugging workflow](https://docs.google.com/document/d/1COgCBWWuTh2o-Zbp6h_z0h0LtlJaimaEDsION4RZPxc/edit#)
- [Chrome DevTools 实现原理与性能分析实战](https://blog.csdn.net/LuckyWinty/article/details/122183667)
- [Chrome DevTools 远程调试协议分析及实战](https://cloud.tencent.com/developer/article/1620907)
- [Chrome DevTools Protocol](https://chromedevtools.github.io/devtools-protocol/)
- [Chrome DevTools Frontend 运行原理浅析](https://zhaomenghuan.js.org/blog/chrome-devtools-frontend-analysis-of-principle.html)
- [Chrome DevTools 中文手册](https://leeon.gitbooks.io/devtools/content/)
- [Chrome 开发工具指南](https://uprogrammer.cn/chrome-devtools/)
- [Chrome 开发者工具中文手册](https://github.com/CN-Chrome-DevTools/CN-Chrome-DevTools)
- [chii](https://github.com/liriliri/chii)（远程调试工具）
- [devtool](https://github.com/Jam3/devtool)
- [devtools-protocol](https://github.com/ChromeDevTools/debugger-protocol-viewer)
- [chrome-remote-interface](https://github.com/cyrus-and/chrome-remote-interface/)
- [awesome-chrome-devtools](https://github.com/ChromeDevTools/awesome-chrome-devtools#chrome-devtools-protocol)\[Awesome\]
- [devtools-frontend](https://github.com/ChromeDevTools/devtools-frontend)
### 调试
- [揭秘浏览器远程调试技术](https://fed.taobao.org/blog/taofed/do71ct/chrome-remote-debugging-technics/)
- [VS Code - Debugger for Chrome](https://lcsc-frontend.github.io/2018/01/31/VS-Code-Debugger-for-Chrome/)
- [远程调试原理及端智能场景下远程调试实现方案](https://juejin.cn/post/6979941358781857823)
- [利用 ADB 协议建立 PC 与手机端本地 unix 套接字的连接](https://blog.csdn.net/doon/article/details/78121955)
- [了解 adb 的基本原理](https://cloud.tencent.com/developer/article/1053774)
- [ADB 通信](https://blog.csdn.net/xing1716263268/article/details/8998192)
- [adb forward 的细节（1）：原理概述](https://blog.csdn.net/u013553529/article/details/80036227)
- [San DevTools 技术解析(上)](https://github.com/baidu/san/discussions/579)
- [San DevTools 技术解析(中)](https://github.com/baidu/san/discussions/580)
- [San DevTools 技术解析(下)](https://github.com/baidu/san/discussions/581)
- [移动端 WEB 真机调试全攻略](https://developer.aliyun.com/article/747677)
- [抖音小程序调试原理](https://forum.microapp.bytedance.com/mini-app/posts/61c183cba2bca35737f7f6b9)
- [云真机平台 H5 性能测试的设计与实现](https://testerhome.com/topics/13588)
- [揭秘浏览器远程调试技术](https://fed.taobao.org/blog/taofed/do71ct/chrome-remote-debugging-technics/)
- [深入理解 Node.js 的 Inspector](https://www.cnblogs.com/cangqinglang/p/15178838.html)
- [\[译\] 在 Chrome 开发者工具中调试 node.js](https://github.com/sqrthree/sqrthree.github.io/issues/8)
- [Node 调试指南 - Inspector 协议](https://juejin.cn/post/6844903504882499598)
### 扩展
- [什么是微内核架构设计？](https://developer.aliyun.com/article/779572)
- [插件开发指南 | Vue CLI](https://cli.vuejs.org/zh/dev-guide/plugin-dev.html#%E5%BC%80%E5%A7%8B)
- [Chrome Extension 官方](https://developer.chrome.com/docs/extensions/mv3/)
- [How to build a plugin system on the web and also sleep well at night](https://www.figma.com/blog/how-we-built-the-figma-plugin-system/)
- [大型 Web 应用插件化架构探索](https://mp.weixin.qq.com/s/EBI3NvirxKfRIRE9amJ4TQ)
### 组件库
- [React Flow](https://reactflow.dev/)
- [Svelte Material UI](https://sveltematerialui.com/)
- [Formliy](https://github.com/alibaba/formily)（可拓展组件库的动态表单解决方案）
- [form-render](https://xrender.fun/form-render)（动态表单解决方案）
- [react-error-boundary](https://github.com/bvaughn/react-error-boundary)（React 错误边界组件）
- [ant-motion](https://github.com/ant-design/ant-motion)（React 动效库）
- [pro-components](https://github.com/ant-design/pro-components)（Ant Design Pro）
- [Ant Design](https://ant.design/index-cn)
- [Element Plus](https://element-plus.gitee.io/zh-CN/)（基于 Vue 3，面向设计师和开发者的组件库）
- [Element](https://element.eleme.cn/#/zh-CN) (基于 Vue2.0 的饿了么桌面端组件库)
- [Ant Design Vue](https://antdv.com/docs/vue/introduce-cn/)
- [Ant Design Pro](https://pro.ant.design/zh-CN/) (开箱即用的中台前端/设计解决方案)
- [Antd ProComponents](https://procomponents.ant.design/components)
- [Salt UI](https://salt-ui.github.io/) (高效、简洁的移动端 UI 组件库)
- [Ant Design Mobile 5.0](https://mobile.ant.design/zh)
- [ant-design-pro-vue](https://pro.antdv.com/) (开箱即用的中台前端/设计解决方案)
- [vue-antd-admin](https://github.com/iczer/vue-antd-admin) (一个开箱即用的中后台前端/设计解决方案)
- [Fusion](https://fusion.design/pc/?themeid=2)
- [Muse-UI](https://muse-ui.org/#/zh-CN) (基于 Vue 2.0 优雅的 Material Design UI 组件库)
- [Vue Material](https://www.creative-tim.com/vuematerial/)
- [Bootstrap](https://v4.bootcss.com/)
- [Bootstrap Table](https://bootstrap-table.com/)
- [Bulma](https://bulma.io/)
### 性能优化
- [前端性能优化之旅](https://alienzhou.github.io/fe-performance-journey/)
- [使用 Proload/Prefetch 优化你的应用](https://github.com/happylindz/blog/issues/17)
- [preload-prefetch-and-priorities-in-chrome](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)
- [Preload，Prefetch 和它们在 Chrome 之中的优先级](https://github.com/xitu/gold-miner/blob/master/TODO/preload-prefetch-and-priorities-in-chrome.md)
- [得物 App H5 秒开优化实战](https://juejin.cn/post/7086284339364757517#heading-10)
- [First Contentful Paint (FCP)](https://web.dev/articles/fcp?hl=zh-cn)
- [Largest Contentful Paint (LCP)](https://web.dev/articles/lcp?hl=zh-cn#how-to-improve-lcp)
- [Faster page loads using server think-time with Early Hints](https://developer.chrome.com/blog/early-hints/)

### 工程化

- [Rollup 的基本使用](https://www.cnblogs.com/WindrunnerMax/p/14422971.html)
- [Git 中文](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%85%B3%E4%BA%8E%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6)
- [Webpack 中文](https://webpack.docschina.org/)
- [Gulp 中文](https://www.gulpjs.com.cn/docs/getting-started/quick-start/)
- [npm 中文](https://www.npmjs.cn/)
- [yarn 中文](https://yarn.bootcss.com/)
- [飞冰 - 基于 React 的研发解决方案](https://ice.work/)
- [深入浅出 Webpack](http://webpack.wuhaolin.cn/)
- [webpack-chain](https://github.com/neutrinojs/webpack-chain) (生成和修改 Webpack 配置信息的链式 API 集)
- [CKEditor 4](https://ckeditor.com/ckeditor-4/)(Smart WYSIWYG HTML editor)
- [75 Best Node.js Command Line Apps & Utilities | FireBear](https://firebearstudio.com/blog/node-js-command-line-apps-utilities.html)\[Awesome\]
- [Node.js CLI modules](https://nodejs.libhunt.com/modules/cli)
- [rollup.js 中文](https://rollupjs.org/guide/zh/)
- [gulp-typescript](https://github.com/ivogabe/gulp-typescript)
- [Module Federation](https://webpack.js.org/concepts/module-federation/)
- [Workspaces in Yarn](https://yarnpkg.com/blog/2017/08/02/introducing-workspaces/)
- [Why you should use a single repository for all your company’s projects](https://www.drmaciver.com/2016/10/why-you-should-use-a-single-repository-for-all-your-companys-projects/)(多项目单仓库思考)
### Monorepo
- [monorepo](https://monorepo.tools/#understanding-monorepos)
- [Lerna 中文](https://www.lernajs.cn/)
- [Lerna 文档](http://www.febeacon.com/lerna-docs-zh-cn/)
- [monorepo 新浪潮 | introduce lerna](https://github.com/pigcan/blog/issues/3)（Lerna 介绍）
- [Why is Babel a monorepo?](https://github.com/babel/babel/blob/master/doc/design/monorepo.md)

### 监控
- [7 天打造前端性能监控系统](http://fex.baidu.com/blog/2014/05/build-performance-monitor-in-7-days/)
- [把前端监控做到极致](https://juejin.im/post/5a52f138f265da3e5b32a41b)
- [UEM“探针”技术及用户体验管理](https://juejin.im/post/5d283c16f265da1b7004d647)
- [前端代码质量-圈复杂度原理和实践](https://juejin.im/post/5da34216e51d4578502c24c5)
- [要进大厂？前端灰度发布必须要知道](https://juejin.im/post/5da88d795188252f051e2b47)
- [从前端程序员的视角看小程序的稳定性保障](https://juejin.im/post/5c77ab516fb9a049ba424413)
### 运维
- [Kubernetes / Pod](https://kubernetes.io/zh-cn/docs/concepts/workloads/pods/)
- [Docker 中文网](https://www.dockerdocs.cn/get-started/overview/)
- [Docker 从入门到实践](https://yeasy.gitbook.io/docker_practice/)
- [深入浅出 Docker 技术](https://juejin.cn/post/7134631844103847973?searchId=2023121817155149B13D340123C977D516)
- [Docker 核心技术与实现原理](https://draveness.me/docker/)
- [Docker 入门教程](https://www.ruanyifeng.com/blog/2018/02/docker-tutorial.html)
### SSR
- [⚡️ 手把手带你将 CSR / SSR 应用迁移到 ESR 🚀](https://juejin.cn/post/7031570308293197837)
### 客户端
- [Flutter 中文网](https://flutterchina.club/)
- [Flutter 实战](https://book.flutterchina.club/)
- [简述 Chromium, CEF, Webkit, JavaScriptCore, V8, Blink](https://juejin.im/post/5c0492a36fb9a049e82b435a)
- [浅谈 Native、Web App、Hybrid、RN 和 Weex 优劣](https://juejin.im/post/59c0b5265188256bd871e9bd)
- [用 JS 开发跨平台桌面应用，从原理到实践](https://juejin.im/post/5cfd2ec7e51d45554877a59f)
- [Hybrid 开发：JsBridge - Web 和客户端的桥](https://juejin.im/post/58cdeba62f301e007e4af7e6)
- [JSBridge 实战](https://juejin.im/post/5bda6f276fb9a0226d18931f)
- [高并发 IM 系统架构优化实践](https://juejin.im/post/5b1e2cc15188257d4529804b)
- [再学 Android 之 WebView](https://juejin.im/post/5cff8c27f265da1bae38f1c1)

### 跨端
- [Yoga 跨平台布局引擎](https://github.com/facebook/yoga)
- [Yoga Layout](https://www.npmjs.com/package/yoga-layout)
- [跨平台布局引擎Yoga的学习和使用](https://www.jianshu.com/p/95bf92143141)
- [【翻译】Yoga 教程: 使用跨平台布局引擎](https://juejin.cn/post/6844903491165487118)
- [在项目中使用Yoga 布局引擎](https://tbfungeek.github.io/2019/11/05/%E5%9C%A8%E9%A1%B9%E7%9B%AE%E4%B8%AD%E4%BD%BF%E7%94%A8Yoga-%E5%B8%83%E5%B1%80%E5%BC%95%E6%93%8E/)
- [在项目中使用Yoga 布局引擎](https://tbfungeek.github.io/2019/11/05/%E5%9C%A8%E9%A1%B9%E7%9B%AE%E4%B8%AD%E4%BD%BF%E7%94%A8Yoga-%E5%B8%83%E5%B1%80%E5%BC%95%E6%93%8E/)
- [JavaScript Core](https://developer.apple.com/documentation/javascriptcore)
- [Android 中 JNI 的使用：java 调用 C++ C++调用 JAVA](https://www.jianshu.com/p/819aeb45fd83)
- [OC 与 C++相互调用](https://cloud.tencent.com/developer/article/1608870)
- [移动端 JS 引擎哪家强？](https://segmentfault.com/a/1190000039288517)
- [V8、JSCore、Hermes、QuickJS，hybrid 开发 JS 引擎怎么选](https://cloud.tencent.com/developer/article/1801742)
- [聊一聊桥接（JSBridge）的原理](https://juejin.cn/post/6940242236701409287)
- [Android 中 JSBridge 的原理与实现](https://www.jianshu.com/p/2ec3f06d6087)
- [Android JSBridge 原理与实现](https://www.viseator.com/2018/09/07/android_JSBridge/)
- [Android 混合开发之 JsBridge](https://juejin.cn/post/6844903989935341576)
- [Android 多线程：手把手教你使用 HandlerThread](https://www.jianshu.com/p/9c10beaa1c95)
- [JSI，V8 JS 引擎优化](https://juejin.cn/post/6882541851224752142#heading-21)
- [QuickJS](https://github.com/bellard/quickjs)
- [Design Of V8 bindings](https://chromium.googlesource.com/chromium/src/+/master/third_party/blink/renderer/bindings/core/v8/V8BindingDesign.md)
- [Getting started with embedding V8](https://v8.dev/docs/embed)
- [JS Binding 技术基础](https://hxxft.github.io/lynx-book/design-doc/js-binding/js-binding-part1.html)
- [JS Binding 技术进阶](https://hxxft.github.io/lynx-book/design-doc/js-binding/js-binding-part2.html)
- [v8pp](https://github.com/pmed/v8pp)
- [nbind](https://github.com/charto/nbind)
- [rusty_v8](https://github.com/denoland/rusty_v8)
- [J2V8](https://github.com/eclipsesource/J2V8)
- [LiquidCore](https://github.com/LiquidPlayer/LiquidCore)
- [nodejs-mobile](https://github.com/JaneaSystems/nodejs-mobile)
- [emscripten](https://github.com/emscripten-core/emscripten)
- [binaryen](https://github.com/WebAssembly/binaryen)
- [Hummer](https://github.com/bellard/quickjs)
- [lynx-native](https://github.com/hxxft/lynx-native)
- [libuv](https://github.com/libuv/libuv)
### WebAssembly
- [Webassembly 应用场景及其关键技术初探](https://zhuanlan.zhihu.com/p/339952783)
- [WebAssembly 生态及关键技术初探(续)](https://zhuanlan.zhihu.com/p/512605509)
- [c++项目转成 wasm 全过程](https://zhuanlan.zhihu.com/p/158586853)
- [在 WebAssembly 中实现回调的方式](https://segmentfault.com/a/1190000039142400)
- [WebAssembly 在 MOSN 中的探索与实践](https://gw.alipayobjects.com/os/bmw-prod/fbf09bcb-3c0f-4b66-af74-9dfa69966405.pdf)
- [深入 WebAssembly 之解释器实现篇](https://juejin.cn/post/7012121617664835614)
- [通过 WebAssembly 使用异步 Web API](https://web.dev/articles/asyncify?hl=zh-cn)
- [WebAssembly C++ 阻塞调用 JS 异步函数](https://zhuanlan.zhihu.com/p/444335335)
- [wasm3](https://github.com/wasm3/wasm3)
- [wasmer](https://github.com/wasmerio/wasmer)
- [wasmtime](https://github.com/bytecodealliance/wasmtime)
- [WAVM](https://github.com/WAVM/WAVM)
- [wabt](https://github.com/WebAssembly/wabt)
- [wasm-micro-runtime](https://github.com/bytecodealliance/wasm-micro-runtime)
- [wasm-c-api](https://github.com/WebAssembly/wasm-c-api)（WebAssembly C++ 封装）
- [WebAssembly Binding](https://github.com/wasm3/wasm3/blob/main/platforms/cpp/main.cpp#L46)
### 微前端
- [garfish（A powerful micro front-end framework）](https://github.com/web-infra-dev/garfish)
- [Micro Frontends: Building a modern webapp with multiple teams](https://speakerdeck.com/naltatis/micro-frontends-building-a-modern-webapp-with-multiple-teams?slide=44)
- [一起探討 Micro Frontends 的世界](https://blog.techbridge.cc/2019/01/12/micro-frontends-concept/)
- [让 iframe 焕发新生](https://zhuanlan.zhihu.com/p/442815952)
- [极致的微前端方案\_无界的源码剖析](https://juejin.cn/post/7158777745806196743)
- [一文读懂微前端架构](https://cloud.tencent.com/developer/article/1828684)
- [微前端架构的几种技术选型](https://z.itpub.net/article/detail/74E1FE471D792761354A24E491509AFC)
- [字节跳动是如何落地微前端的](https://juejin.cn/post/7016900744695513125)
- [微前端是否值得开发者采用？](https://www.infoq.cn/article/bccx5o3eyjogteaqnksq)
- [微前端如何落地？](https://segmentfault.com/a/1190000019663742)
- [微前端的核心价值](https://zhuanlan.zhihu.com/p/95085796)
- [将微前端做到极致-无界微前端方案](https://zhuanlan.zhihu.com/p/551206945)
- [将微前端做到极致-无界微前端方案](https://zhuanlan.zhihu.com/p/551206945)
- [如何在大型应用中架构设计微前端方案](https://zhuanlan.zhihu.com/p/197885919)
- [微服务架构设计模式](https://www.yuque.com/surfacew/daily-learn/lzhgk3#cOXoJ)
- [Why Not Iframe](https://www.yuque.com/kuitos/gky7yw/gesexv)
- [沙箱逃逸](https://websec.readthedocs.io/zh/latest/language/javascript/vm.html#)
- [Events not registered inside shadow dom](https://github.com/facebook/react/issues/10422)
- [基于 iframe 的全新微前端方案](https://cloud.tencent.com/developer/article/1919034)
- [这种微前端设计思维听说过吗？](https://segmentfault.com/a/1190000040456726)
- [如何在大型应用中架构设计微前端方案](https://zhuanlan.zhihu.com/p/197885919)
- [\[RFC\]微前端样式隔离方案](https://github.com/ice-lab/icestark/issues/413)
- [icestark](https://github.com/ice-lab/icestark)
- [import-html-entry](https://github.com/kuitos/import-html-entry)（HTML Entry）
- [single-spa](https://github.com/single-spa/single-spa)
- [single-spa-login-example-with-npm-packages](https://github.com/jualoppaz/single-spa-login-example-with-npm-packages)
- [micro-app](https://github.com/micro-zoe/micro-app)
- [micro-frontends](https://micro-frontends.org/)
- [micro-frontends](https://github.com/neuland/micro-frontends)
- [proposal-shadowrealm](https://github.com/tc39/proposal-shadowrealm)（隔离提案）
- [SES](https://github.com/endojs/endo/blob/master/packages/ses/README.md)
- [Endo (还在开发)](https://github.com/endojs/endo/blob/master/packages/ses/README.md)
- [LavaMoat](https://github.com/LavaMoat/LavaMoat)（安全沙箱）
- [Secure Modular Runtimes](https://guybedford.com/secure-modular-runtimes.html)
- [Import Maps 隔离提案](https://github.com/guybedford/import-maps-extensions#isolated-scopes)
- [Jailed — flexible JS sandbox](https://github.com/asvd/jailed)（浏览器和 Node.js 沙箱库）
- [微前端的核心价值](https://www.yuque.com/kuitos/gky7yw/rhduwc)
- [Thinking in Microfrontend (微前端的那些事儿)](https://github.com/phodal/microfrontends)
- [Micro Frontends](https://martinfowler.com/articles/micro-frontends.html)
- [qiankun](https://qiankun.umijs.org/zh)
- [single-spa](https://zh-hans.single-spa.js.org/docs/getting-started-overview/)
- [可能是你见过最完善的微前端解决方案](https://zhuanlan.zhihu.com/p/78362028)
- [探索微前端的场景极限](https://www.yuque.com/kuitos/gky7yw/uyp6wi)
- [微前端入门](https://juejin.cn/post/6844903953734336525)
- [了解什么是微前端](https://juejin.im/post/5d1f19e3f265da1bab29ce5f)
- [\[译\] 微前端](https://juejin.im/post/5d0e367b6fb9a07ebf4b781a)
### Rust
- [The Rust Programming Language](https://doc.rust-lang.org/book/title-page.html)
- [Rust by Example](https://doc.rust-lang.org/stable/rust-by-example/index.html#rust-by-example)
- [The Rust Edition Guide](https://doc.rust-lang.org/edition-guide/introduction.html)
- [The Rust Edition Guide](https://doc.rust-lang.org/edition-guide/introduction.html)
- [The rustc book](https://doc.rust-lang.org/rustc/what-is-rustc.html)
- [The rustdoc book](https://doc.rust-lang.org/rustdoc/index.html)
- [Command line apps in Rust](https://rust-cli.github.io/book/index.html)
- [Rust and WebAssembly](https://rustwasm.github.io/docs/book/introduction.html#rust--and-webassembly-)
- [Rust error codes index](https://doc.rust-lang.org/error_codes/error-index.html)
- [Rust Is The Future of JavaScript Infrastructure](https://leerob.io/blog/rust)
- [TOML](https://toml.io/en/)
- [cargo](https://github.com/rust-lang/cargo)
- [rust-clippy](https://github.com/rust-lang/rust-clippy)
- [Docs.rs](https://docs.rs/)
- [Ray Tracing in One Weekend](https://raytracing.github.io/books/RayTracingInOneWeekend.html)
- [Yew](https://yew.rs/zh-Hans/)
- [Rust](https://www.rust-lang.org/zh-CN/)
- [The Rust community’s crate registry](https://crates.io/)
- [Rust 程序设计语言(简体中文版)](https://kaisery.github.io/trpl-zh-cn/)
- [Rust by Example](https://doc.rust-lang.org/stable/rust-by-example/index.html)
- [Command line apps in Rust](https://rust-cli.github.io/book/index.html)
- [rustfmt](https://github.com/rust-lang/rustfmt)
### 低代码
- [JSON Schema](https://json-schema.org/overview/what-is-jsonschema)
- [面向复杂场景的表单解决方案](https://juejin.cn/post/6862869137710907405)
- [格式校验利器：JSON Schema 简介](https://juejin.im/post/5b5533e3e51d45195c0747b8)
- [JSON Schema 与表单验证](https://juejin.im/post/58bcdd4461ff4b006cf66c2c)
- [json-schema 可视化编辑器发布了](https://juejin.im/post/5aab954a518825557005c6cd)
### IDE
- [vscode-extension-samples](https://github.com/microsoft/vscode-extension-samples)
- [VS Code 插件中文开发文档](https://liiked.github.io/VS-Code-Extension-Doc-ZH/#/)
- [OpenSumi](https://github.com/opensumi/core/blob/main/README-zh_CN.md)
### 风格指南
- [JSDoc 中文](https://www.jsdoc.com.cn/)
- [JSDoc 中文](https://www.shouce.ren/api/view/a/13232)
- [TypeDoc](https://typedoc.org/api/#typedoc)
- [Google JavaScript 代码风格指南](https://juejin.im/post/5bd01d4a518825781e647e90)

### 编程指南
- [函数式编程指北](https://llh911001.gitbooks.io/mostly-adequate-guide-chinese/content/)
- [可伸缩的同构 Javascript 代码](https://efe.baidu.com/blog/isomorphic/)
- [界面之下：还原真实的 MV\* 模式](https://github.com/livoras/blog/issues/11)
- [函数式编程初探](http://www.ruanyifeng.com/blog/2012/04/functional_programming.html)
- [函数式编程入门教程](http://www.ruanyifeng.com/blog/2017/02/fp-tutorial.html)
- [Pointfree 编程风格指南](http://www.ruanyifeng.com/blog/2017/03/pointfree.html)
- [简明 JavaScript 函数式编程——入门篇](https://juejin.cn/post/6844903936378273799)
- [函数式编程，真香](https://juejin.cn/post/6844903743117361165)
- [Java SPI 机制详解](https://juejin.cn/post/6844903605695152142)
- [InversifyJS](https://chinabigpan.github.io/inversifyjs_docs_cn/)
- [InversifyJS/ecosystem.md](https://github.com/inversify/InversifyJS/blob/master/wiki/ecosystem.md)
- [如何基于 TypeScript 实现控制反转](https://juejin.cn/post/6898882861277904910)
- [reflect-metadata](https://github.com/rbuckton/reflect-metadata)
- [Reflect](https://es6.ruanyifeng.com/#docs/reflect)
- [Decorators for ES6 classes](https://github.com/tc39/proposal-decorators)
- [编程范式（Programming Paradigm）](https://www.imooc.com/article/14330)
- [What is the precise definition of programming paradigm?](https://softwareengineering.stackexchange.com/questions/166442/what-is-the-precise-definition-of-programming-paradigm#)
- [主要的编程范例](http://www.eecs.ucf.edu/~leavens/ComS541Fall97/hw-pages/paradigms/major.html#imperative)
- [再谈编程范式—程序语言背后的思想](https://juejin.cn/post/6844903834121142279)
- [面向接口编程详解（一）](https://www.cnblogs.com/leoo2sk/archive/2008/04/10/1146447.html)
- [那些年我们错过的响应式编程](https://github.com/kevinyaoo/android-tech-frontier/blob/master/androidweekly/%E9%82%A3%E4%BA%9B%E5%B9%B4%E6%88%91%E4%BB%AC%E9%94%99%E8%BF%87%E7%9A%84%E5%93%8D%E5%BA%94%E5%BC%8F%E7%BC%96%E7%A8%8B/readme.md)
- [响应式编程的实践](http://zhangyi.xyz/summary-of-reactive-programming/)
- [什么是响应式编程（Reactive Programming）](https://juejin.cn/post/6844903997745135623)
- [函数式编程 - 实现响应式框架](https://juejin.cn/post/6844903504377544717)
- [Reactive 响应式/反应式编程](https://www.jdon.com/reactive.html)
- [响应式编程到底是什么？](https://xie.infoq.cn/article/277867e2d5af56de29c6031a6)
- [响应式编程总览](https://juejin.cn/post/6844903482198065160)
- [面向 Model 编程的前端架构设计](https://mp.weixin.qq.com/s/peLNXa_PLQTfhTtLya3cpg?v_p=82&WBAPIAnalysisOriUICodes=10000011_10000011&launchid=10000365--x&wm=3333_2001&aid=01AzrSlevY37z6v38NDKadC8lPswcuCcNUXI8FE9Qmtp-qGZM.&from=10A6093010)
- [Understanding JavaServer Pages Model 2 architecture](https://www.javaworld.com/article/2076557/understanding-javaserver-pages-model-2-architecture.html)
- [GUI Architectures](https://martinfowler.com/eaaDev/uiArchs.html)
- [javascript 设计模式系列](https://www.cnblogs.com/webFrontDev/p/3553402.html)
### 解决方案
- [漫画：什么是中台？](https://juejin.im/post/5d995f82f265da5ba308389d#comment)
- [IaaS，PaaS，SaaS 的区别](http://www.ruanyifeng.com/blog/2017/07/iaas-paas-saas.html)
- [Serverless 掀起新的前端技术变革](https://zhuanlan.zhihu.com/p/65914436)
- [云计算的三种服务模式：IaaS，PaaS 和 SaaS](https://www.jianshu.com/p/b96d4ad71b57)

### 编译器相关
- [acorn](https://github.com/acornjs/acorn)
- [csstree](https://github.com/csstree/csstree)
- [astexplorer](https://astexplorer.net/)
- [前端编译原理浅析及应用场景(Babel、PostCSS)分析](https://zhuanlan.zhihu.com/p/100920334)
- [ANTLR 4 简明教程](https://wizardforcel.gitbooks.io/antlr4-short-course/content/)
- [ANTLR](https://www.antlr.org/)
- [MiniDecaf 编译实验](https://decaf-lang.github.io/minidecaf-tutorial/)
- [antlr4](https://github.com/antlr/antlr4)
- [grammars-v4](https://github.com/antlr/grammars-v4)
- [antlr4ts](https://github.com/tunnelvisionlabs/antlr4ts)
- [riscv-pk](https://github.com/riscv-software-src/riscv-pk)
- [minidecaf](https://github.com/equation314/minidecaf)
- [homebrew-riscv](https://github.com/riscv-software-src/homebrew-riscv)
- [ANTLR：在浏览器中玩语法解析](https://juejin.cn/post/6844903539978813453)
- [Antlr4 简介](http://icejoywoo.github.io/2019/01/16/intro-to-antlr4.html)
- [antlr4-demo](https://github.com/icejoywoo/antlr4-demo)
- [Antlr4 简易快速入门](https://zhuanlan.zhihu.com/p/114982293)
- [Antlr4 前端应用与实践](https://juejin.cn/post/6872931804362309640)
- [ANTLR：在浏览器中玩语法解析](https://github.com/sunxiuguo/blog-1/blob/master/201712/2.md)
### Mac App
- [Arc](https://arc.net/)（提效浏览器）
- [KeyCue](https://www.ergonis.com/keycue/switching/cheatsheet)（快速显示 App 的所有快捷键）
- [keycastr](https://github.com/keycastr/keycastr)（按键提示）
- [Rectangle](https://rectangleapp.com/)（窗口分屏工具）
- [Karabiner-Elements](https://karabiner-elements.pqrs.org/)（键盘映射）
- [Keyboard Maestro](https://www.keyboardmaestro.com/main/)（超级强大的键盘提效工具）
- [XMind](https://xmind.app/)（思维导图）
- [iHosts](https://github.com/toolinbox/iHosts)（域名代理）
- [lightproxy](https://github.com/alibaba/lightproxy)（系统代理）
- [ClashX](https://github.com/yichengchen/clashX)（科学上网）
- [whistle](https://github.com/avwo/whistle)（抓包调试）
- [Raycast](https://www.raycast.com/)（工作流）
- [Magnet](https://magnet.crowdcafe.com/)（窗口分屏）
- [Alfred](https://www.alfredapp.com/)（工作流）
- [dash](https://kapeli.com/dash)
- [uTools](https://u.tools/download.html)
- [WoX](https://github.com/Wox-launcher/Wox)
### Chrome 插件
- [Json Formatter](https://chromewebstore.google.com/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa?hl=en)
- [React Developer Tools](https://chromewebstore.google.com/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en)
- [XSwitch](https://chromewebstore.google.com/detail/xswitch/idkjhjggpffolpidfkikidcokdkdaogg?hl=en)（请求代理工具）
- [Google 翻译](https://chrome.google.com/webstore/detail/google-translate/aapbdbdomjkkjkaonfhkkikfgjllcleb?hl=zh-CN)
- [Header Editor](https://chrome.google.com/webstore/detail/header-editor/eningockdidmgiojffjmkdblpjocbhgh)（请求头携带处理）
- [Vue.js devtools](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd?hl=zh-CN)
- [Octotree](https://chrome.google.com/webstore/detail/octotree/bkhaagjahfmjljalopjnoealnfndnagc?hl=zh-CN)
### VS Code 插件
- [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)（单词拼写错误检查）
- [Code Time](https://marketplace.visualstudio.com/items?itemName=softwaredotcom.swdc-vscode)
- [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
- [Document This](https://marketplace.visualstudio.com/items?itemName=oouo-diogo-perdigao.docthis)（JS Doc 自动生成）
- [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)（AI 代码生成）
- [GitHub Copilot Chat](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat)
- [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [IntelliCode](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.vscodeintellicode)
- [Jest](https://marketplace.visualstudio.com/items?itemName=Orta.vscode-jest)
- [Pretty TypeScript Errors](https://marketplace.visualstudio.com/items?itemName=yoavbls.pretty-ts-errors)（格式 TypeScript 错误）
- [Search node_modules](https://marketplace.visualstudio.com/items?itemName=jasonnutter.search-node-modules)（快速搜索 NPM 库包）
- [Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode)
- [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
- [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur)
- [open in browser](https://marketplace.visualstudio.com/items?itemName=techer.open-in-browser)
- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
- [GitHub Actions](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-github-actions)
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Vuetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur)
### 终端
- [Z shell](https://zsh.sourceforge.io/)
- [zsh-z](https://github.com/agkozak/zsh-z)
- [autojump](https://github.com/wting/autojump)
- [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions/tree/master)
- [zsh-completions](https://github.com/zsh-users/zsh-completions)
- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
- [ohmyzsh - Themes](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)
- [zplug](https://github.com/zplug/zplug)
- [Fish Shell](https://fishshell.com/)
- [POSIX Shell](https://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html)
- [Shebang](https://zh.m.wikipedia.org/wiki/Shebang)
- [ngrok](https://github.com/bubenshchykov/ngrok#readme)（内网穿透）
- [mkcert](https://github.com/FiloSottile/mkcert)
- [hyper](https://hyper.is/)
- [warp](https://www.warp.dev/)
- [alacritty](https://github.com/alacritty/alacritty)
- [tabby](https://tabby.sh/)
- [Rio](https://raphamorim.io/rio/)
- [iTerm2-Color-Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes)
- [Homebrew](https://brew.sh/)
- [sindresorhus/emoj: Find relevant emoji from text on the command-line](https://github.com/sindresorhus/emoj)
- [bash(1) - Linux man page](https://linux.die.net/man/1/bash)
- [iterm2](https://www.iterm2.com/)
- [ohmyzsh](https://github.com/ohmyzsh/ohmyzsh)
- [powerlevel10k](https://github.com/romkatv/powerlevel10k)

### 总结
- [State of JavaScript 2022](https://2022.stateofjs.com/en-US/)
- [2021 JavaScript Rising Stars](https://risingstars.js.org/2021/zh)
- [State of JS 2020](https://2020.stateofjs.com/zh-Hant/)
- [State of JS 2021](https://2021.stateofjs.com/zh-Hans/)