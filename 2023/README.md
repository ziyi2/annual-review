2024 已经到来，在 Web 前端这个岗位已经工作 6 年。这里将 2023 的学习内容做一些总结，并规划一下 2024 的学习计划。

## 历年技能树

[2019 年前端总结](https://juejin.cn/post/6844904038543130632#heading-2) 的年度关键词分为创新和实践两个部分，其中创新的关键词是「UI 框架 / 脚手架」和「低代码（Low Code）」，实践的关键词是「桌面端」。这一年在通用基础设施建设上获得了很多开发经验。如下所示，标红的部分是有所接触或深入的部分：

![image](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/574d98b0cb80459194c9b65178d690fe~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=1512&h=2206&s=1078346&e=png&b=fefefe)

[2021 年](https://juejin.cn/post/7069468539412807693)涉及内容包括 RxJS 响应式设计实践和原理解析（主要针对客户端的 IM 和通讯录）、CDP 调试协议感性认知、微前端业务实践以及 V8 编译原理认知等。如下所示，标绿的部分是有所接触或深入的部分：

![image](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f7cc899d3de642b388a823cd6d9e6231~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=1512&h=4745&s=2175606&e=png&b=fefefe)

[2022 年度总结](https://juejin.cn/post/7188890491188936762)深入研究了微前端的原理基础，额外衍生学习了 Chromium 和 V8 的一些基础知识。在 CDP 调试协议上研究了 Android 的 ADB 转发设计，在跨端方面则实现了在 Android 中嵌入 JS 引擎并实现桥接 Binding 设计，在 VS Code 的扩展上则设计实现了相应的 Devops 工具。这一年学习的内容相对深入和复杂，而且对 Java 和 C++ 等其它语言提出了要求。如下所示，标黄的部分是有所接触或深入的部分：

![image](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9062774636b84e01865fcc45fa227764~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=1512&h=5976&s=3490343&e=png&b=fefcfc)

以下给出学习过程中的粗略思维导图整理：

![image](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2fbfe9a58c834aa5847c7ab256dce482~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=1512&h=2979&s=1644976&e=png&b=f0f0f0)

> 温馨提示：如果需要 XMind 原版，可以下载 [2022 / Xmind](https://github.com/ziyi2/annual-review/tree/2022/2022/xmind) 文件。

## 2023 技能树

2023 年因为大部分时间在撰写《深入浅出微前端》小册，总体在技术上没有得到什么体系化的成长，虽然接触了一些其它领域，例如鸿蒙（ArkTS 和方舟编译器）、微服务（Spring Cloud、Nacos）和 AI（ChatPT）等，但都停留在认知和间接使用的层面，没有业务实践。2023 年的技能树如下所示，标蓝的部分是有所接触或深入的部分：

![image](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6af8c1c3b9724e01a80715fd4efcf865~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=1851&h=10000&s=2624553&e=png&b=fefdfd)

以下给出学习过程中的粗略思维导图整理：

![image](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9b12afbab8dc44d68ef0b4064f213854~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=2263&h=9288&s=2831517&e=png&b=f0f0f0)

> 温馨提示：如果需要 XMind 原版，可以下载 [2023 / Xmind](https://github.com/ziyi2/annual-review/tree/2023/2023/xmind) 文件。

## 2023 学习情况

2023 年整体上没有 2022 年专注，学习的内容也相对细琐。首先对 2022 年提到的 2023 学习计划进行一个总结，如下所示：

| **方向** | **细分** | **计划** | **优先级** | **完成情况** |
| - | - | -| - | - |
| Chromium 基础 | 架构 | DOM 渲染原理了解 | 低 | 未完成 |
| Chromium 基础 | V8 | C++ 绑定技术深入并实现 Demo | 高 | 完成 |
| Chromium 基础 | V8 | 断点调试原理 | 中 | 完成 |
| Chromium 基础 | Blink | 任务调度（Event Loop 原理） | 中 | 完成 |
| 微前端 | 隔离技术 | 各种隔离技术深入 & SES 可行性分析 | 高 | 完成 |
| 微前端 | 方案设计 | 各种方案技术深入 & Demo 实现 | 高 | 完成 |
| 微前端 | 方案设计 | 基于 Web Components 的设计 Demo 实现 | 高 | 完成 |
| Chrome DevTools | CDP 协议 | 捕捉分析 & 移动端调试模拟页面 | 高 | 未完成 |
| Chrome DevTools | Frontend | 定制 & 扩展调试面板 | 高 | 未完成 |
| Chrome DevTools | Backend | Mock 脚本原理分析 & 定制 | 高 | 未完成 |
| Chrome DevTools | 消息通道 | ADB 无线通信 & WebSocket 服务 | 高 | 未完成 |
| 跨端 | JS 引擎 | Andriod & iOS 嵌入 & 异步绑定技术 | 高 | 未完成 |
| 跨端 | JS 引擎 | Andiroid & iOS 绑定接口实现 | 高 | 未完成 |
| 跨端 | WebAssembly | Andiroid & iOS 异步绑定实现 | 低 | 未完成 |
| 跨端 | 框架 | 跨端框架 UI 绑定 & 渲染深入 | 低 | 未完成 |

由于工作业务上的变动，在 Chrome DevTools 和跨端侧没有再做一些深入研究。除此之外，由于 2022 年萌生了写一本微前端小册的想法，因此在 Chromium 和 V8 基础知识上做了更多深入研究，为小册的理论撰写奠定了基础。当然，今年在服务端技术方向上做了倾斜，更多的想往全栈的方向去靠。

### AI 学习

| **方向** | **细分** | **学习内容** |
| - | - | - |
| Open AI | ChatGPT 原理 | 输入输出编码（Tokenizer、Embedding）、Transformer（Self-Attention、Feed Forward）、训练策略（预训练、Finetune、Few-Shot、RLHF） |
| Open AI | ChatGPT 基础 | Prompt Engineering 生成（提示工程）、Temperature、Tokens、Models（训练模型）、Fine-tuning（微调模型）、Completion、Embeddings |

Open AI 能够提升开发者的生产力，也能快速提高学习的认知力。通过学习 ChatGPT 的原理，可以更好的了解 AI 的运行机制和具备的能力。学习 ChatGPT 的基础知识，可以更好的结合它和业务的使用场景并提升开发者工具和业务产品的智能化。当然，我们的侧重点不是去细致研究底层的 AI 模型如何实现，而是需要借助 AI 的智能化能力实现套壳的业务产品，例如：

- **阶段一**：卷 AI 的 UI 形态，调用 Open AI 接口，ChatGPT 回答什么，套壳产品回答什么
- **阶段二**：构建优质的 Prompt（提示工程），套壳产品卷 Prompt 的质量和分发
- **阶段三**：特定领域的 Embedding 数据集向量化，构建自己的向量数据库，解决 AI 无法触及的私人数据和垂直领域问题，例如 AI 答疑小助手
- **阶段四**：微调（Fine-Tuning）模型，相对于 Prompt 每次调用 Open AI 接口时需要携带大量的上下文信息并消耗大量的 Token，微调是训练模型本身，使用优质的数据对模型进行二次训练，让模型匹配对特定数据的理解，此时消耗的 Token 更少，响应的速度更快
- **阶段五**：AI Agent（人工智能代理），利用阶段一到阶段四的能力组合来设计一个软件实体，它可以自主决策任务的最优执行路线。 AI Agent 可以使用不同的微调模型来处理不同的任务和功能，最终通过智能决策来完成任务执行和结果展示。例如旅游 AI 助手，告诉助手什么时间段需要去哪里旅游，它可以根据历史数据自动订机票、订酒店以及订景点门票等，甚至还可以根据旅游攻略帮你定制体验更好的旅游路线并协助你避开高峰期

对于 AI 仅仅停留在认知和简单的使用层面，没有参与到实际的业务开发中，这一块事实上是自己落后的原因，如果自己早早进入布局，或许可以在之前的扩展框架对应的 VS Code 扩展 DevOps 开发工具上进行 AI 能力的集成，从而助力扩展业务的智能化开发，希望 2024 能够让自己在这一块有所研究和产出。

除此之外，推荐大家使用 Github Copilot & GIthub Copilot Chat（VS Code 插件）来提升编码效率，它可以智能的创建代码、补全代码、优化代码、分析源码以及快速提供配置解决方案等。当然，如果你会频繁撰写开发和技术相关的文档，特别推荐使用[钉钉的魔法棒](https://alidocs.dingtalk.com/i/p/Pl2AmoVbakq8Xdb9BpLmk7jYdkVEvm2g)功能，它可以非常智能的协助你完成文档设计（文案创作、大纲生成、语气润色、竞品分析等）。

### Chromium 基础学习

| **方向** | **细分** | **学习内容** |
| - | - | - |
| Chromium 基础 | 进程 | 进程间通信 Mojo & IPC |
| Chromium 基础 | 进程 | Threading And Tasks 感性认知、The Anatomy of a Frame |
| Chromium 基础 | Network | Chromium Network 源码运行分析 |
| Chromium 基础 | HTTP 缓存 | 缓存源码运行分析 |
| Chromium 基础 | V8 | Context 上下文（Window ）创建源码分析 |
| Chromium 基础 | V8 | 动态库 & 静态库编译（depot_tools、GN、gclinet、ninja） |
| Chromium 基础 | V8 | C++ 嵌入设计 & Context 切换（g++ 编译、cmake 编译套件） |
| Chromium 基础 | V8 | V8 的概念（Isolate、Handle & Context） |
| Chromium 基础 | V8 | 断点调试源码分析（chill 为什么不支持源码调试） |
| Chromium 基础 | V8 Binding | Web IDL 标准感性认知 |
| Chromium 基础 | CEF 框架 | 多进程运行示例（分离子进程执行体） |
| Chromium 基础 | CEF 框架 | Web 应用 JS Binding 设计 |

早期学习 Chromium 基础知识是因为在业务上需要设计跨端扩展框架，用于实现三方 JS 在 PC、Andriod & iOS 中的跨端 Runtime 设计，需要给三方 JS 运行时桥接 APP 底座的通用能力（例如 HTTP 请求、APP 弹框、新开 WebView 容器页面等），从而实现更加深层次的定制化扩展。为此，重点研究了运行 JS 所需要具备的 JS 引擎（为了提升轻量运行时的性能，甚至调研了 WebAssembly 的运行时能力）、JS 引擎在 Chromium 的渲染引擎、APP 中的运行机制以及分发 JS 需要具备的离线化能力等。因此在 Chromium 和 V8 层面做了一些深入调研，包括 Web API 的绑定设计、V8 在 C++ 中的嵌入、APP 内置语言（例如 Java 和 Objective-C）和 C++ 的相互操作、V8 实例和上下文的创建、V8 的编译、隔离、嵌入实践等。当然，仅仅运行 JS 还不够，还需要考虑 APP 如何将 [CDP 调试协议](https://chromedevtools.github.io/devtools-protocol/)透传到 VS Code 扩展开发工具上，支持扫码调试或者目标发现等，从而使得跨端扩展框架具备完整的 Devops 能力。

现在学习 Chromium 基础知识用于了解浏览器底层的运行原理，从而为撰写《深入浅出微前端》小册提供更为详细的理论基础，例如 V8 隔离和 iframe 运行机制等，使大家可以知其然并知其所以然。

> 温馨提示：由于 Chromium 的知识体系非常庞大，因此很难由点到面。如果有业务或者 Demo 实践，最好是基于实践进行学习，例如基于 [CEF](https://github.com/chromiumembedded/cef) 进行桌面端应用的混合开发设计，通过实践可以高效加深整个底层的学习。

### 微前端小册

| **方向** | **细分** | **学习内容** |
| - | - | - |
| 微服务 | 感性认知 | Nacos、Diamond、 Spring Cloud、Spring Cloud Alibaba、Spring Cloud Netflix Eureka（服务注册和发现）、HSF（High-Speed Service Framework）、RPC、SSO 单点登录原理 |
| Web 基础 | 构建工具 | Webpack 编译产物模块化 & import()运行时原理、Vie 原理解析 |
| Web 基础 | React | React Schedule 原理、React-router 原理 |
| 微前端小册 | 方案示例 | 动态 Script、Web Components 以及 iframe 等方案的示例设计 |
| 微前端小册 | 隔离原理 | 隔离技术示例设计（V8 Isolate & Context 隔离、iframe 隔离、Shadow DOM 隔离、Mock 隔离等） |
| 微前端小册 | 性能优化 | 性能优化示例设计（HTTP 缓存标准解析、Resource Hints 、预渲染 & 预加载） |
| 微前端小册 | 通信示例 | 观察者 & 发布订阅模式 |
| 微前端小册 | 框架解析 | single-spa 示例设计（import()动态按需加载、NPM 、动态 Script  & Fetch） |
| 微前端小册 | 框架解析 | single-spa 原理解析（状态机运行机制） |
| 微前端小册 | 框架解析 | qiankun 原理解析（基于 single-spa 的隔离和 html-entry 设计） |
| 微前端小册 | 工程化 | 构建、按需加载、版本发布、ESLint、Prettier、提交规范、更新日志、静态文档、CI / CD、README 说明等 |

2023 年 8 月正式在掘金平台发布了[《深入浅出微前端》](https://juejin.cn/book/7258893482318626868?utm_source=profile_book)小册，并获得了[掘金 2023 年度畅销好课](https://activity.juejin.cn/rank/2023/influence#course)。在撰写微前端小册的前期调研了大量的理论基础，包括 Chromium 知识体系（整体框架、运行机制、V8 的编译 & 运行 & 概念、其它局部知识体系）和微服务架构体系等。在真正撰写时，还研究了很多工程化的原理、Webpack 编译产物运行时原理、React Schedule 原理以及社区的微前端框架原理等，用于加强整个小册的深度和通用性设计。2024 年在小册的撰写方面，会从理论和通用性建设转移到社区框架解析和业务实践部分，从而使大家可以对微前端在业务层面的设计更加清晰。

为了使大家更好的了解微前端的知识体系，我还在冴羽的好青年社区群做了一次[《深入浅出沙箱隔离》的技术分享](https://juejin.cn/book/7258893482318626868/section/7300853723612315686)，感兴趣的同学可以私信获取分享视频和 PPT。2024 年也会做更多的微前端技术分享，从而通过视频使大家能够更加直观的了解微前端知识体系。

### Svelte 技术

| **方向** | **细分** | **学习内容** |
| - | - | - |
| Svelte Web 框架 | 基础认知 | Virtual DOM vs No Virtual DOM、JSX vs Template & Logic Block |
| Svelte Web 框架 | 产物运行时原理 | 整体运行流程、脏值检测算法、响应式原理分析、JS Label 计算属性原理分析、异步队列分析 |
| Svelte Web 框架 | 编译原理 | Parsing source code into AST（AST 解析）、Tracking references and dependencies（响应式依赖遍历收集）、Creating code blocks and fragments（生成 instance 和 create_fragment）、Generage code（生成运行时代码） |

[Svelte](https://svelte.dev/) Web 框架是对内部某个静态官网设计所做的技术选型，配合 [Tailwind CSS](https://tailwindcss.com/) 进行设计整体上而言使得构建的产物 Size 非常小，适合设计一些需要考虑页面性能的静态网站。除此之外，Svelte 本质上是一个编译器，编译后具备少量的通用运行时代码，拥有完备的 AOT 意图优化能力。关于 Svelte、Vue 和 React 的差异（例如 JSX vs Template & Logic Block、Vitrual DOM vs No Virtual DOM、React Hook & Class Constructor），在**冴羽**的社区群做了一次[《深入浅出 Svelte》的技术分享](https://juejin.cn/book/7258893482318626868/section/7300853723612315686)，感兴趣的同学可以私信获取分享视频和 PPT。

### Docker 技术

| **方向** | **细分** | **学习内容** |
| - | - | - |
| Docker | 基础知识 | 虚拟机、Linux 容器、沙箱 |
| Docker | 基础概念和命令 | Images、Containers（ Image 的运行时实例）、Docker Hub |
| Docker | 镜像制作 | Dockerfile & 指令 |
| Docker | 原理解析 | 感性认知 |
| K8S | 感性认知 | Ingress、Services、Pod、Containers |

Docker 主要用于前端静态资源的运维，分为镜像制作（利用 Node.js 聚合产物并设定 Niginx 运维配置）和容器运行时的 Nginx 静态服务启动。虽然在设计的过程中研究了一下 Docker 的技术原理（虽然也学习过 Golang，对 C 语言也非常熟悉），但是感觉学了又好像没学，等后续有时间可以好好再深入研究一下。除此之外，在真正的业务设计中还涉及了 K8S 的 Ingress（转发规则）、Service 以及 Pod 等运维概念，只不过这一块在实际的业务中只停留在认知层面，没有做过真正的实践。

### 工作和学习提效

| **方向** | **细分** | **学习内容** |
| - | - | - |
| 学习 & 工作提效 | 快捷键 | Mac 系统 & App & 终端快捷键提效（KeyCastr & Keyclu & Karabiner-Elements、Hyper Key） |
| 学习 & 工作提效 | Mac App | Rectangle、Arc、Raycast |
| 学习 & 工作提效 | 终端 | iTerm2、ohmyzsh、zplug、ohmyzsh 插件、powerlevel10k 主题 |
| 学习 & 工作提效 | VS Code 编程 | Github Copilot、GIthub Copilot Chat、IntelliCode、Tailwind CSS IntelliSense |

由于受到了 AI 降维打击的刺激，决定提升一下自己的工作和学习效能，从各个快捷键、App、终端配置、AI 编程等方面对自己进行了提效升级，相应的教程放在了微前端小册的[番外篇](https://juejin.cn/book/7258893482318626868/section/7292031353426542619)。其中，感觉最能提效的是 [Raycast](https://www.raycast.com/)，它具备了 Quicklinks、Extensions、Script Command 以及快捷键设置等诸多能力，当然个人现在用的还比较浅，如下所示：

![image](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7a577f5eefbb4c7ca52c12ab70b8f6f2~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=2748&h=1740&s=19003770&e=png&b=9e3efe)

> 温馨提示：Raycast 的同类型的软件包括 [Alfred](https://link.juejin.cn/?target=https%3A%2F%2Fwww.alfredapp.com%2F)，尽管 Alfred 的自定义工作流 Workflow 更为强大，但是不对免费用户开放。

## 2024 学习计划

通过 2023 以及往年的技术总结，我发现个人比较感兴趣并且可以深入的技术包括以下几块：

| **内容** | 学习优先级 | **说明** |
| - | - | - |
| Parse 解析 | 低 | 例如 ESLint 和 Svelte 的解析设计等，但是没有实际的业务开发需要，所以一直没有机会研究，如果大家有一些好的 idea 和业务开发经验可以分享一下，例如低代码和 Pro Code 的互相转换，可能会需要使用解析器的设计 |
| SSR CSR & ESR | 高 | 虽然早期使用过 [Nuxt](https://nuxt.com/)，但是基本上已经忘记了 SSR 的同构原理，说明学习的还不够深入和全面，同时对 [Next.js](https://nextjs.org/) 以及 [Vercel](https://vercel.com/) 非常感兴趣，希望有时间可以利用 Next.js 以及相应的服务技术重新打造一个全新的博客站点 |
| 微服务架构 | 高 | Spring Cloud 和 Nacos 的了解以及微服务架构的认知，希望能在业务层面参与其中的一个 Java 微服务的设计，从而可以深入理解服务发现、配置管理、API 网关、消息队列、容器化和编排技术（Docker & K8S）、服务间通信（HSF、gRPC & GraphQL）等后端技术 |
| Chromium 渲染引擎 | 中 | 深入了解 CSS、DOM 的运行原理以及页面渲染的实现细节，配合 V8 全面了解 Chromium 底层的运行机制。当然最好是能通过业务进行实践，例如可以借助 CEF 桌面端混合开发深入了解 Chromium 架构以及 C++, 或者也可以从小程序的双线程通信原理（渲染现场和 JS 线程通信）入手，了解小程序的运行机制和小程序 IDE 的 CDP 调试原理。 |
| AI Agent | 高 | 通过 Embeddings 嵌入技术或者 Fine-tuning 微调模型来训练个人的博客数据、聊天数据、健康数据等，打造个人的 AI 数字 IP（AI 智能体） |
| React 框架原理 | 低 | React 完整的原理分析、React 新语法特性 |

通过 2023 年以及往年的技术栈总结可以发现，自身学习的内容越来越碎片化，越来越难形成体系化的沉淀。如果没有业务需要，学习和技术的深入只会让自身知识面接收频率越来越低，并且学习效率越来越低。

2024 年不希望自己在技术深度上继续挖掘，除非是业务和小册撰写需要，更希望在广度上能够全面发展，因此希望自己往全栈的技术和业务方向去深入，包括 SSR 的原理解析、Next.js 的使用和微服务架构的认知，希望有机会可以实践一个微服务应用。

> 温馨提示：今年在服务端方向上进行了初步探索，原本想在微前端和微服务架构的基础上实现一个服务端应用，专门用于页面渲染、SSO 认证、前端 Diamond 配置和服务请求包装（类似于 BFF）等，但是由于种种现实问题最终没能落地，希望明年可以落地一个 Java 微服务应用（哪怕只是一个 Demo 示例），可以完整实现该功能。

## 2024 写作计划

2023 年因为忙于写小册基本上没有产出文章，这里罗列出 2024 年待写的文章：

- Svelte 框架技术（编译 & 运行时原理、框架竞品分析）
- 沙箱隔离技术（Chromium 站点隔离、操作系统沙箱、Linux 容器技术等）
- V8 系列（绑定技术、Web DSL、断点调试原理）
- Chrome DevTools （CDP 调试原理、Android ADB 调试转发 & 无线调试技术）
- RxJS（深入浅出 RxJS 原理 & IM 开发实践）
- WebAssembly 系列（C++ 嵌入示例、异步调用实现、绑定技术）
- VS Code 扩展开发指南（工程化内容、IDE 能力调用等）
- 面试系列（React 原理、微前端原理、工程化原理、混合开发等）

## 2023 书签

这里将平时学习时查阅的博客、文档、电子书、PPT、视频以及 Github 仓库等进行书签汇总，并按照收藏时间进行倒序排序。如果想浏览某一项技术，建议从低到高进行浏览。通过整理年度书签，可以用于分析自己在这一年中主要学习了哪些技术。

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
### Open AI
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
- [CSSOM 视图模式(CSSOM View Module)相关整理](https://www.zhangxinxu.com/wordpress/2011/09/cssom%E8%A7%86%E5%9B%BE%E6%A8%A1%E5%BC%8Fcssom-view-module%E7%9B%B8%E5%85%B3%E6%95%B4%E7%90%86%E4%B8%8E%E4%BB%8B%E7%BB%8D/)（张鑫旭）
- [CSS 相对定位|绝对定位(五)之 z-index 篇](https://www.zhangxinxu.com/wordpress/2011/08/css%E7%9B%B8%E5%AF%B9%E5%AE%9A%E4%BD%8D%E7%BB%9D%E5%AF%B9%E5%AE%9A%E4%BD%8D%E4%BA%94%E4%B9%8Bz-index%E7%AF%87/)（张鑫旭）
- [获取元素 CSS 值之 getComputedStyle 方法熟悉](https://www.zhangxinxu.com/wordpress/2012/05/getcomputedstyle-js-getpropertyvalue-currentstyle/)(张鑫旭)
- [我对 CSS vertical-align 的一些理解与认识](https://www.zhangxinxu.com/wordpress/2010/05/%E6%88%91%E5%AF%B9css-vertical-align%E7%9A%84%E4%B8%80%E4%BA%9B%E7%90%86%E8%A7%A3%E4%B8%8E%E8%AE%A4%E8%AF%86%EF%BC%88%E4%B8%80%EF%BC%89/)(张鑫旭)
- [CSS 实现单行、多行文本溢出显示省略号](http://www.daqianduan.com/6179.html)
- [我所知道的几种 display:table-cell 的应用](https://www.zhangxinxu.com/wordpress/2010/10/%E6%88%91%E6%89%80%E7%9F%A5%E9%81%93%E7%9A%84%E5%87%A0%E7%A7%8Ddisplaytable-cell%E7%9A%84%E5%BA%94%E7%94%A8/)(张鑫旭)
- [\[译\] 这些 CSS 命名规范将省下你大把调试时间](https://juejin.im/post/5a6c5881518825733201daf7)
- [等高分栏布局小结](https://www.cnblogs.com/lyzg/p/5164593.html)
- [css 写作建议和性能优化小结](https://segmentfault.com/a/1190000011390896)
- [CSS 定位属性详解](https://juejin.im/post/5a1bb35ff265da43231ab164)
- [\[译\] Web 流式文字排版的现状](https://juejin.im/post/5d267d9de51d45773d4686ab)
- [真正了解 CSS3 背景下的@font face 规则](https://www.zhangxinxu.com/wordpress/2017/03/css3-font-face-src-local/) (张鑫旭)
- [Web 字体简介: TTF, OTF, WOFF, EOT & SVG](https://zhuanlan.zhihu.com/p/28179203)
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
- [新兴前端框架 Svelte 从入门到原理](https://zhuanlan.zhihu.com/p/350507037)
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
- [git 如何修改已提交的 commit](https://github.com/uolcano/blog/issues/12)
- [commit_msg](https://git-scm.com/docs/githooks#_commit_msg)(git 钩子文档)
- [语义化版本 2.0.0](https://semver.org/lang/zh-CN/)(语义化版本控制规范)
- [Git submodule 简明使用指南](https://juejin.cn/post/6896524597722939399)
- [git 撤销 commit 并保存之前的修改](https://blog.csdn.net/mentalitys/article/details/81079761)
- [.gitignore 无效解决办法](https://www.jianshu.com/p/bc135b986d3f)
- [Git 钩子：自定义你的工作流](https://github.com/geeeeeeeeek/git-recipes/wiki/5.4-Git-%E9%92%A9%E5%AD%90%EF%BC%9A%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BD%A0%E7%9A%84%E5%B7%A5%E4%BD%9C%E6%B5%81)
- [Git 分支 - 变基](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%8F%98%E5%9F%BA)
- [cz-cli](https://github.com/commitizen/cz-cli)(cz 工具)
- [cz-customizable](https://github.com/leonardoanalista/cz-customizable)(cz 适配器)
- [@commitlint/config-conventional](https://github.com/marionebl/commitlint/tree/master/@commitlint/config-conventional)(cz 适配器)
- [commitlint](https://github.com/marionebl/commitlint)(cz 校验工具)
- [commitlint-config-cz](https://github.com/whizark/commitlint-config-cz)(cz 校验工具的校验规则)
- [validate-commit-msg](https://github.com/Frikki/validate-commit-message)(cz 校验工具)
- [conventional-changelog](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog)(cz 日志生成器)
- [如何让你的 GitHub 项目表面上更专业](https://juejin.im/post/5d312fb6f265da1b60293c51)
- [git-flow 的工作流程](https://www.git-tower.com/learn/git/ebook/cn/command-line/advanced-topics/git-flow)
- [如何使用 Issue 管理软件项目？](http://www.ruanyifeng.com/blog/2017/08/issue.html)
- [Git 工作流程](http://www.ruanyifeng.com/blog/2015/12/git-workflow.html)
- [为无线前端团队打造高效 git 工作流](https://juejin.im/post/5b2b76e251882574934c388d)
### NPM & Yarn
- [npm 的 package.json 和 package-lock.json 更新策略](https://blog.csdn.net/weixin_43820866/article/details/105232066)
- [一文搞懂 peerDependencies](https://segmentfault.com/a/1190000022435060?u_atoken=22ebaf50-4e28-4393-a9ee-921affb95c12&u_asession=01A9JNkai6MoBtFWnVqZB26Y9cDUAL0H9HgFC0V_k_yUkPxaWOSZ86ofJCeNMnUkae4_rRYCy7-8RsAT-_loBtytsq8AL43dpOnCClYrgFm6o&u_asig=05_UDHsNjsfU-Q4Sf8CfJcSDzapPlQ7s3Kr80LGfQyqjB2vsZb-4kSk-ITliEDT5xgVsTnp4CMnNXKgWlObP0gq2McCx6ZMiGkHVg-t68ZdOZWDRkBW6INXIsRBiG5NZt7Lav4XLcgfmu8cd7msd4dbbkOY0fjDi7e6K0XVfJ-NjJ-5mDskEyBqg11T7BpJ6geksmHjM0JOodanL5-M1Qs1S2ycTu7f-0UQa0xqUoNfmU-BTffTi6navYa_uCt_O3J63OjdMnwmYWlYnM9_QQPWqpVqC89iFyYoqTbHo3XUZPUpLHxH1iRKZmnjAu0Zefw&u_aref=gGZqyR1UtCFRnWCrcv4LdQguD7s%3D)
- [Compare package download counts over time](https://npmtrends.com/)
- [Life Cycle Scripts](https://docs.npmjs.com/cli/v9/using-npm/scripts#life-cycle-scripts)
- [npm ci](https://docs.npmjs.com/cli/v7/commands/npm-ci)（CI / CD 依赖安装）
- [npm update](https://docs.npmjs.com/cli/v9/commands/npm-update)（依赖升级）
### 版本规范
- [semver 2.0.0](https://semver.org/lang/zh-CN/)
- [node-semver](https://github.com/npm/node-semver#versions)
- [semantic-release](https://github.com/semantic-release/semantic-release)
### Node.js
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
- [阿里 Midway 正式发布 Serverless v1.0，研发提效 50%](https://github.com/midwayjs/midway/wiki/%E9%98%BF%E9%87%8C-Midway-%E6%AD%A3%E5%BC%8F%E5%8F%91%E5%B8%83-Serverless-v1.0%EF%BC%8C%E7%A0%94%E5%8F%91%E6%8F%90%E6%95%88-50%25)
- [浅析 Node.js 的 vm 模块以及运行不信任代码](https://segmentfault.com/a/1190000008284054)
- [node-inspector](https://github.com/node-inspector/node-inspector)（Node.js debugger based on Blink Developer Tools）
- [深入理解 Node.js 中的进程与线程](https://juejin.cn/post/6844903908385488903)
- [execa](https://github.com/sindresorhus/execa)
- [parse-json](https://github.com/sindresorhus/parse-json)
- [gitbeaker](https://github.com/jdalrymple/gitbeaker)
- [node-fetch](https://github.com/node-fetch/node-fetch)
- [node-inspector](https://github.com/node-inspector/node-inspector)
- [Forcing Garbage Collection in node.js and JavaScript](https://www.xarg.org/2016/06/forcing-garbage-collection-in-node-js-and-javascript/)(强制垃圾回收)
- [Mongoose the Typescript way…?](https://stackoverflow.com/questions/34482136/mongoose-the-typescript-way)
- [mongoose Population 连表／关联使用](https://www.jianshu.com/p/d700ad062083)
- [Node.js 环境性能监控](https://juejin.im/post/5c71324b6fb9a049d37fbb7c)
- [使用 TypeScript 开发 Node.js](https://juejin.im/entry/59c09867f265da06560457c3)
- [30 分钟理解 GraphQL 核心概念](https://segmentfault.com/a/1190000014131950)
- [Open Sourcing GraphQL Middleware - A Library to Simplify Your Resolvers](https://www.prisma.io/blog/graphql-middleware-zie3iphithxy/)
- [RPC vs REST vs GraphQL](https://segmentfault.com/a/1190000013961872)
- [GraphQL 从入门到实战](https://juejin.im/post/5cd68a9b51882568047fa6eb)
- [手把手教你做爬虫](https://blog.csdn.net/yezhenxu1992/article/details/50820629)
- [关于爬虫，就此封键盘](https://zhuanlan.zhihu.com/p/22097627)
- [PHP, Python, Node.js 哪个比较适合写爬虫？](https://www.zhihu.com/question/23643061)
- [简单高效的 nodejs 爬虫模型](https://cnodejs.org/topic/584a18289ff0dbf333450901)
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
- [使用 ESLint ＆ Prettier 美化 Vue 代码](https://nice.lovejade.cn/zh/article/beautify-vue-by-eslint-and-prettier.html#%E5%88%9D%E5%A7%8B%E5%8C%96-vue-%E9%A1%B9%E7%9B%AE%E6%8E%A8%E4%BB%8B)
- [eslint prettier 的配置选项（参数）官网直译](https://segmentfault.com/a/1190000012909159)
- [ESLint couldn't determine the plugin uniquely.](https://github.com/eslint/eslint/issues/13385)
- [Prettier](https://prettier.io/)(An opinionated code formatter)
- [Prettier 看这一篇就行了](https://zhuanlan.zhihu.com/p/81764012)
- [Prettier 看这一篇就行了](https://zhuanlan.zhihu.com/p/81764012)
### Module Federation
- [Webpack / Module Federation](https://webpack.js.org/concepts/module-federation/)
- [Dynamic Remotes, Webpack Module Federation](https://h3manth.com/posts/dynamic-remotes-webpack-module-federation/)
- [Module Federation: streamline your microfrontends](https://module-federation.io/)
### Babel
- [体验了一把 swc 替代 babel 和 tsc](https://juejin.cn/post/7000267162774405134#heading-4)
- [编译 ts 代码用 tsc 还是 babel？](https://juejin.cn/post/7084882650233569317)
- [Babel](https://www.babeljs.cn/)
- [@vue/babel-preset-app](https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/babel-preset-app)(Vue CLI3 的 Babel 插件集)
- [@babel/preset-env](https://github.com/babel/babel/tree/master/packages/babel-preset-env)(Babel 插件集)
- [你真的会用 Babel 吗？](https://juejin.im/post/59b9ffa8f265da06710d8e89#comment)(全面了解 Babel)
- [再见，babel-preset-2015](https://zhuanlan.zhihu.com/p/29506685)
- [Deploying ES2015+ Code in Production Today](https://philipwalton.com/articles/deploying-es2015-code-in-production-today/)
- ​[【建议改成】读完这篇你还不懂 Babel 我给你寄口罩](https://juejin.im/post/5e477139f265da574c566dda)
- [前端编译原理浅析及应用场景(Babel、PostCSS)分析](https://zhuanlan.zhihu.com/p/100920334)
- [Why is Babel a monorepo?](https://github.com/babel/babel/blob/master/doc/design/monorepo.md)
### 构建工具
- [在 vite 中加载远程模块](https://juejin.cn/post/7044144010532765726)
- [Vite 原理浅析](https://juejin.cn/post/6844904146915573773)
- [Vite 原理分析](https://juejin.cn/post/6881078539756503047)
- [深入理解 Vite 核心原理](https://juejin.cn/post/7064853960636989454)
- [面向未来的前端构建工具-vite](https://juejin.cn/post/6869915676501835783)
- [基于 esbuild 的 universal bundler 设计](https://juejin.cn/post/6940218189921910797)
- [前端构建新世代，Esbuild 原来还能这么玩！](https://juejin.cn/post/7049147751866564621)
- [parcel](https://github.com/parcel-bundler/parcel)
- [Rollup 打包工具的使用（超详细，超基础，附代码截图超简单）](https://juejin.cn/post/6844904058394771470)
- [rollup-starter-lib](https://github.com/rollup/rollup-starter-lib)
- [使用 Rollup 构建你的 Library](https://zhuanlan.zhihu.com/p/34218678)
- [《前端领域的转译打包工具链》上篇](https://juejin.cn/post/6956602138201948196)
- [前端领域的转译打包工具链（下）：工程化闭环](https://juejin.cn/post/6971070129345921032)
- [带你入门前端工程（五）：不同构建工具的功能和优势](https://www.freecodecamp.org/chinese/news/front-end-engineering-build-tools/)
- [前端打包工具](https://es-interview.js.org/articles/06-FE+Browser/03-pack-tool.html)
- [Webpack 模块引用中还有什么坑？](https://juejin.cn/post/6844903826592366600)
- [swc 作者为何选择 Go 语言来实现 TypeScript 的类型检查器？](https://www.zhihu.com/question/513453040/answer/2325410512)
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
- [使用 Github Action 来做自动化](https://zhuanlan.zhihu.com/p/648939706)
- [Github Action Marketplace](https://github.com/marketplace?type=actions)
- [Learn YAML in five minutes!](https://www.codeproject.com/Articles/1214409/Learn-YAML-in-five-minutes)
- [DingTalk Release Notify](https://github.com/visiky/dingtalk-release-notify)
- [大公司里怎样开发和部署前端代码？](https://www.zhihu.com/question/20790576/answer/32602154)(张云龙)
- [GitHub Actions](https://docs.github.com/en/actions)
- [GitHub Actions 入门教程](http://www.ruanyifeng.com/blog/2019/09/getting-started-with-github-actions.html)（阮一峰）
- [pm2](https://pm2.io/)(The Most Advanced Production Process Manager for Node.js)
- [GitHub 新出的 Actions 是什么? 用他做自动测试?](https://juejin.im/post/5d5378e9f265da03d72811a1)
- [Jenkins](https://www.jenkins.io/zh/)
- [jenkins 如何做到触发远程构建](https://blog.csdn.net/hwhua1986/article/details/48028581)
- [jenkins 构建触发器详解-不登录触发远程构建详解](https://www.cnblogs.com/Rocky_/p/8297260.html)
- [Jenkins 记录二：远程构建](https://www.jianshu.com/p/81785f65b1d3)
- [Jenkins+Node.js 持续集成](https://www.jianshu.com/p/64b498304d07)
- [nginx](https://nginx.org/en/)
- [Nginx 开发从入门到精通](http://tengine.taobao.org/book/#nginx)
- [前端必会的 Nginx 入门视频教程(共 11 集)](https://juejin.im/post/5bd7a6046fb9a05d2c43f8c7)
- [前端开发者必备的 Nginx 知识](https://juejin.im/post/5c85a64d6fb9a04a0e2e038c)
- [如何使用 docker 部署前端应用](https://juejin.im/post/5c83cbaa6fb9a04a0f65fdaa)
- [前端开发如何让持续集成/持续部署(CI/CD)跑起来](https://zhuanlan.zhihu.com/p/26701038)
- [从零搭建 docker+jenkins+node.js 自动化部署环境](https://juejin.im/post/5b8ddb70e51d45389153f288)
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
- [测试驱动开发（TDD）总结——原理篇](https://juejin.cn/post/6844903780970921991)
- [前端测试框架 Jest](https://juejin.cn/post/6844903489030586376)
- [刚开始接触前端测试？那就从金字塔顶端开始吧！](https://www.infoq.cn/article/ei01KYMCS0V2fo1R4SrG)
- [ui-testing-best-practices](https://github.com/NoriSte/ui-testing-best-practices)
- [测试框架 Mocha 实例教程](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html)
- [测试覆盖（率）到底有什么用？](https://www.infoq.cn/article/test-coverage-rate-role)
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
- [飞猪双十一会场再加速，营销域 SSR 解决方案的落地实践](https://developer.aliyun.com/article/778784?spm=a2c6h.13262185.profile.130.5e804b9f2963zl)
- [双十一会场体验 SSR 优化 - 走向更复杂的渲染架构](https://blog.csdn.net/Taobaojishu/article/details/109759586)
- [打造高可靠与高性能的 React 同构解决方案](https://github.com/alibaba/beidou/blob/master/packages/beidou-docs/articles/high-performance-isomorphic-app.md)
- [压缩 11000 条 key 减少 7.2M，飞书如何实现 i18n 前端体积优化](https://mp.weixin.qq.com/s/Qt6BL5pa7OJIBLH7Sl_WCA)
- [让老板虎躯一震的前端技术](https://juejin.im/post/5c3ff18b6fb9a04a0a5f76aa)
- [前端优化不完全指南](https://aotu.io/notes/2016/03/16/optimization/)

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
- [入门 Webpack，看这篇就够了](https://segmentfault.com/a/1190000006178770)
- [Webpack 入门指迷](https://segmentfault.com/a/1190000002551952)
- [Webpack 大法之 Code Splitting](https://zhuanlan.zhihu.com/p/26710831)(缩小打包体积)
- [彻底解决 Webpack 打包性能问题](https://zhuanlan.zhihu.com/p/21748318)
- [让你的 Webpack 起飞—考拉会员后台 Webpack 优化实战](https://zhuanlan.zhihu.com/p/42465502)
- [import、require、export、module.exports 混合使用详解](https://segmentfault.com/a/1190000012386576)
- [前端构建秘籍](https://juejin.im/post/5c9075305188252d5c743520)
- [结合 vue-cli 来谈 webpack 打包优化](https://juejin.im/post/5c3c55aa51882524b4073394)
- [html-webpack-plugin 使用总结](https://juejin.im/post/5ce96ad7e51d455a2f2201e1)
- [带你深度解锁 Webpack 系列(优化篇)](https://juejin.im/post/5e6cfdc85188254913107c1f)
- [玩转 webpack，使你的打包速度提升 90%](https://juejin.im/post/5e53dbbc518825494905c45f)
- [看完这篇，面试再也不怕被问 Webpack 热更新](https://juejin.im/post/5d8b755fe51d45781332e919)
- [webpack4 入门](https://juejin.im/post/5d6356faf265da03e1688423)
- [从 0 构建自己的脚手架/CLI 知识体系（万字）](https://juejin.cn/post/6966119324478079007#heading-19)
- [前端工程化实战 - 企业级 CLI 开发](https://juejin.cn/post/6982215543017193502)
- [前端工程化实战 - 可配置的模板管理](https://juejin.cn/post/6999397309180182564)
- [详解前端脚手架开发排坑全指南【前端提效必须上干货】](https://juejin.cn/post/6847902225025466376)
- [Node.js+commander 开发命令行工具](https://www.jianshu.com/p/2cae952250d1)
- [Node.js 命令行程序开发教程](http://www.ruanyifeng.com/blog/2015/05/command-line-with-node.html)
- [这是看过最优秀的 Vue-cli 源码分析，绝对受益匪浅](https://juejin.cn/post/6844903586929868813)
- [Vue ClI 源码探索 | Vue Learn Share](https://llccing.github.io/vue-learn-share/vue-cli/#%E8%B0%83%E8%AF%95)
- [rollup.js 中文](https://rollupjs.org/guide/zh/)
- [gulp-typescript](https://github.com/ivogabe/gulp-typescript)
- [你所需要的 npm 知识储备都在这了](https://juejin.cn/post/6844903870578032647)
- [如何 npm 发布特定文件夹作为包根目录](https://qastack.cn/programming/38935176/how-to-npm-publish-specific-folder-but-as-package-root)
- [Why your company shouldn’t use Git submodules](https://codingkilledthecat.wordpress.com/2012/04/28/why-your-company-shouldnt-use-git-submodules/)
- [浅谈 ES 模块和 Webpack Tree-shaking](https://zhuanlan.zhihu.com/p/43844419)
- [Tree-Shaking 进阶之路](https://smilesmith.github.io/201908/TreeShaking%E6%89%93%E6%80%AA%E5%8D%87%E7%BA%A7%E4%B9%8B%E8%B7%AF.html#%E4%B8%80%E3%80%81%E4%BB%80%E4%B9%88%E6%98%AF-tree-shaking%EF%BC%9F)
- [Tree-Shaking 性能优化实践 - 原理篇](https://juejin.cn/post/6844903544756109319)
- [Tree Shaking：从原理到实现](https://juejin.cn/post/6955383260759195678)
- [你的 Tree-Shaking 并没什么卵用](https://juejin.cn/post/6844903549290151949)
- [聊聊 package.json 文件中的 module 字段](https://loveky.github.io/2018/02/26/tree-shaking-and-pkg.module/)
- [热重载原理研究和探索](https://www.jianshu.com/p/656035085783)
- [揭秘 Flutter Hot Reload（原理篇）](https://www.yuque.com/xytech/flutter/uhw8vw#tx8udt)
- [Flutter 的 Hot Reload 是如何做到的](https://segmentfault.com/a/1190000020910463)
- [看完这篇，面试再也不怕被问 Webpack 热更新](https://juejin.cn/post/6844903953092591630)
- [webpack 插件拾趣 (1) —— webpack-dev-server](https://www.cnblogs.com/vajoy/p/7000522.html)
- [打破砂锅问到底：详解 Webpack 中的 sourcemap](https://segmentfault.com/a/1190000008315937)
- [package.json 中 你还不清楚的 browser，module，main 字段优先级](https://github.com/SunshowerC/blog/issues/8)
- [peerDependencies 介绍及简析](https://arayzou.com/2016/06/23/peerDependencies%E4%BB%8B%E7%BB%8D%E5%8F%8A%E7%AE%80%E6%9E%90/)
- [Module Federation](https://webpack.js.org/concepts/module-federation/)
- [你所不知道的模块调试技巧 - npm link](https://github.com/atian25/blog/issues/17)
- [关于你想知道的 package-lock.json 的一切](https://segmentfault.com/a/1190000017257298)
- [\[译\] npm 的经济风云 —— 上半部分](https://juejin.im/post/5d146225e51d4556db694a4b)
- [前端工程化（5）：你所需要的 npm 知识储备都在这了](https://juejin.im/post/5d08d3d3f265da1b7e103a4d)
- [Workspaces in Yarn](https://yarnpkg.com/blog/2017/08/02/introducing-workspaces/)
- [Why you should use a single repository for all your company’s projects](https://www.drmaciver.com/2016/10/why-you-should-use-a-single-repository-for-all-your-companys-projects/)(多项目单仓库思考)
### Monorepo
- [monorepo](https://monorepo.tools/#understanding-monorepos)
- [Lerna 中文](https://www.lernajs.cn/)
- [Lerna 文档](http://www.febeacon.com/lerna-docs-zh-cn/)
- [monorepo 新浪潮 | introduce lerna](https://github.com/pigcan/blog/issues/3)（Lerna 介绍）
- [Why is Babel a monorepo?](https://github.com/babel/babel/blob/master/doc/design/monorepo.md)
- [Open Sourcing CloudFlare’s UI Framework](https://blog.cloudflare.com/cf-ui/)(使用 Lerna 开源的 UI 框架设计)
- [lerna 管理前端 packages 的最佳实践](https://juejin.im/post/5a989fb451882555731b88c2)
### 监控
- [7 天打造前端性能监控系统](http://fex.baidu.com/blog/2014/05/build-performance-monitor-in-7-days/)
- [把前端监控做到极致](https://juejin.im/post/5a52f138f265da3e5b32a41b)
- [全景还原报错现场 | 应用实时监控 ARMS 上线用户行为回溯功能](https://juejin.im/post/5d5ba2c6f265da03a653195e)
- [“前端+应用”两大监控利器商业化首发 ARMS 领跑 APM 市场](https://juejin.im/post/5aa892ce518825558154aa8d)
- [通过页面埋点做监控却不影响性能？解密 ARMS 前端监控数据上报技术内幕](https://juejin.im/post/5afc3d0351882542664301d0)
- [UEM“探针”技术及用户体验管理](https://juejin.im/post/5d283c16f265da1b7004d647)
- [有赞前端质量保障体系](https://juejin.im/post/5d24096ee51d454d1d6285a1)
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
- [国内大厂在移动端跨平台的框架接入分析](https://juejin.im/post/6844904177949212680?spm=ata.13261165.0.0.3a90671f2kN4Sp)
- [flutter 凉了吗?](https://www.zhihu.com/question/374113031)
- [打破重重阻碍，Flutter 和 Web 生态如何对接？](https://mp.weixin.qq.com/s?__biz=MzAxNDEwNjk5OQ==&mid=2650405725&idx=1&sn=0b7476f7c7c01df7fdafda578f9ceb98&scene=21#wechat_redirect)
- [简述 Chromium, CEF, Webkit, JavaScriptCore, V8, Blink](https://juejin.im/post/5c0492a36fb9a049e82b435a)
- [从用 AngularJS 开发 PC 客户端说起](https://segmentfault.com/a/1190000004178969)
- [互联网:桌面客户端框架技术选型](https://www.sohu.com/a/251582457_100259554)
- [漫谈 windows 桌面客户端的 UI 框架](https://www.dazhuanlan.com/2019/09/29/5d8f936a633a2/)
- [小白必看，JSBridge 初探](https://juejin.im/post/5e5248216fb9a07cb0314fc9)
- [分享这半年的 Electron 应用开发和优化经验](https://juejin.im/post/5e0010866fb9a015fd69c645)
- [Electron 从零到一](https://juejin.im/post/5dad8141f265da5b873c778b)
- [浅谈 Native、Web App、Hybrid、RN 和 Weex 优劣](https://juejin.im/post/59c0b5265188256bd871e9bd)
- [用 JS 开发跨平台桌面应用，从原理到实践](https://juejin.im/post/5cfd2ec7e51d45554877a59f)
- [Hybrid APP 架构设计思路](https://segmentfault.com/a/1190000004263182)
- [前端构造桌面级应用（QQ 音乐）](https://juejin.im/post/5bfcb417e51d452e5e70ea8a)
- [Hybrid 开发：JsBridge - Web 和客户端的桥](https://juejin.im/post/58cdeba62f301e007e4af7e6)
- [JSBridge 实战](https://juejin.im/post/5bda6f276fb9a0226d18931f)
- [高并发 IM 系统架构优化实践](https://juejin.im/post/5b1e2cc15188257d4529804b)
- [给客户端同学的一份前端学习指南](https://juejin.im/post/5be2c66df265da61715dd19b)
- [2000 万日订单背后：美团外卖客户端高可用建设体系](https://juejin.im/post/5b10afc06fb9a01e39624d3d)
- [指尖下的 js —— 多触式 web 前端开发之三：处理复杂手势](https://www.cnblogs.com/pifoo/archive/2011/05/22/webkit-touch-event-3.html)
- [H5 键盘兼容性小结](https://juejin.im/post/5c6d1c8b6fb9a049de6df441)
- [再学 Android 之 WebView](https://juejin.im/post/5cff8c27f265da1bae38f1c1)
- [web 移动端布局的那些事儿](https://juejin.im/post/5b6575b0518825196b01fd85)
- [移动端布局适配](https://juejin.im/post/5d4574aff265da03e61af359)
- [关于移动端适配，你必须要知道的](https://juejin.im/post/5cddf289f265da038f77696c)
### 跨端
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
- [即时通讯（IM）开源项目 OpenIM 对 WebAssembly 支持，提升 web 端体验](https://www.toutiao.com/article/7235888524841910817/?app=news_article&timestamp=1684742692&use_new_style=1&req_id=202305221604514A2DC3BD4C2D4A0184B1&group_id=7235888524841910817&share_token=59FD29DA-920E-4184-B77F-ADE9DFA15A1E&tt_from=weixin_moments&utm_source=weixin_moments&utm_medium=toutiao_ios&utm_campaign=client_share&wxshare_count=1&source=m_redirect)
- [wasm3](https://github.com/wasm3/wasm3)
- [wasmer](https://github.com/wasmerio/wasmer)
- [wasmtime](https://github.com/bytecodealliance/wasmtime)
- [WAVM](https://github.com/WAVM/WAVM)
- [wabt](https://github.com/WebAssembly/wabt)
- [wasm-micro-runtime](https://github.com/bytecodealliance/wasm-micro-runtime)
- [wasm-c-api](https://github.com/WebAssembly/wasm-c-api)（WebAssembly C++ 封装）
- [WebAssembly Binding](https://github.com/wasm3/wasm3/blob/main/platforms/cpp/main.cpp#L46)
### 微前端
- [Micro Frontends: Building a modern webapp with multiple teams](https://speakerdeck.com/naltatis/micro-frontends-building-a-modern-webapp-with-multiple-teams?slide=44)
- [一起探討 Micro Frontends 的世界](https://blog.techbridge.cc/2019/01/12/micro-frontends-concept/)
- [加载第三方 JS 的各种姿势](https://juejin.cn/post/6844903447750262792)
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
- [Security, Modules and Node.js](https://docs.google.com/presentation/d/1VUpxoxitZCINJI7jXec4i87YiYZsXr8pCSHdHY5pW30/edit#slide=id.p)
- [Import Maps（导入映射）隔离提案](https://github.com/guybedford/import-maps-extensions#isolated-scopes)
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
- [第三届搞搭建|洛尘 - 如何设计实现 PC 站点搭建系统 - Schema](https://juejin.im/post/5e8835d0518825738a5ac929)
- [第三期 |《早早聊搞搭建》搞过搭建的我收获了什么？（上篇）](https://juejin.im/post/5e8160db51882573b435f5cc)
- [第三期 |《早早聊搞搭建》搞过搭建的我收获了什么？（下篇）](https://juejin.im/post/5e82e1156fb9a03c3c350a51)
- [React 无门槛实现拖拽布局、表单设计器](https://juejin.im/post/5dabb52bf265da5b616de75d)
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
- [JavaScript 代码简洁之道](https://juejin.im/post/5c24b7a851882509a76875e8)
- [前端团队代码评审 CheckList 清单](https://juejin.cn/post/6844903879604191246)
### 编程指南
- [函数式编程指北](https://llh911001.gitbooks.io/mostly-adequate-guide-chinese/content/)
- [可伸缩的同构 Javascript 代码](https://efe.baidu.com/blog/isomorphic/)
- [界面之下：还原真实的 MV\* 模式](https://github.com/livoras/blog/issues/11)
- [函数式编程初探](http://www.ruanyifeng.com/blog/2012/04/functional_programming.html)
- [函数式编程入门教程](http://www.ruanyifeng.com/blog/2017/02/fp-tutorial.html)
- [Pointfree 编程风格指南](http://www.ruanyifeng.com/blog/2017/03/pointfree.html)
- [简明 JavaScript 函数式编程——入门篇](https://juejin.cn/post/6844903936378273799)
- [函数式编程，真香](https://juejin.cn/post/6844903743117361165)
- [这一次，教你从零开始写一个 IoC 容器](https://mp.weixin.qq.com/s/g07BByYS6yD3QkLsA7zLYQ)
- [浅谈 IOC--说清楚 IOC 是什么](https://www.cnblogs.com/DebugLZQ/archive/2013/06/05/3107957.html)
- [IoC 和 DI 的基本概念及 InversifyJS 入门](https://juejin.cn/post/6844904119392534535)
- [Java SPI 机制详解](https://juejin.cn/post/6844903605695152142)
- [InversifyJS](https://chinabigpan.github.io/inversifyjs_docs_cn/)
- [InversifyJS/ecosystem.md](https://github.com/inversify/InversifyJS/blob/master/wiki/ecosystem.md)
- [如何基于 TypeScript 实现控制反转](https://juejin.cn/post/6898882861277904910)
- [Reflect Metadata](https://jkchao.github.io/typescript-book-chinese/tips/metadata.html#%E8%87%AA%E5%AE%9A%E4%B9%89-metadatakey)
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
- [迈入现代 Web 开发（GMTC 2021 演讲《字节跳动的现代 Web 开发实践》全文）](https://mp.weixin.qq.com/s/0VDBAgEvqB1xiUs540Fu9A)
- [漫画：什么是中台？](https://juejin.im/post/5d995f82f265da5ba308389d#comment)
- [IaaS，PaaS，SaaS 的区别](http://www.ruanyifeng.com/blog/2017/07/iaas-paas-saas.html)
- [中台是什么，到底要解决什么问题？](https://juejin.im/post/5d8093c251882579f24fb9ed)
- [MicroSoft Power Platform](https://www.bilibili.com/medialist/play/ml945180386/BV1gk4y167hv?oid=753143173&otype=2)
- [领域驱动设计在互联网业务开发中的实践](https://tech.meituan.com/2017/12/22/ddd-in-practice.html)
- [DDD 模式从天书到实践](https://zhuanlan.zhihu.com/p/91525839)
- [微服务架构入门](https://segmentfault.com/a/1190000015018291)
- [微服务简介](https://segmentfault.com/a/1190000015798054)
- [微服务下使用 GraphQL 构建 BFF](https://mp.weixin.qq.com/s/HSIp5PL-shvrcDdsVxQrmg?)
- [大前端架构思考与选择](https://www.jianshu.com/p/bb8ac7db7e2d)
- [支撑日活百万用户的高并发系统，应该如何设计其数据库架构？【石杉的架构笔记】](https://juejin.im/post/5c6a9f25518825787e69e70a)
- [Serverless 掀起新的前端技术变革](https://zhuanlan.zhihu.com/p/65914436)
- [云计算的三种服务模式：IaaS，PaaS 和 SaaS](https://www.jianshu.com/p/b96d4ad71b57)
- [「真 ® 全栈之路」Web 前端开发的后端指南](https://juejin.im/post/5cc02aacf265da039e1ff3fa)
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
- [oh-my-zsh 让终端好用到飞起~](https://juejin.im/post/5d773da76fb9a06aff5e9a99)
- [简明 VIM 练级攻略](https://coolshell.cn/articles/5426.html)
- [从前端开发攻城狮的角度打造更好用的 Mac OS](https://github.com/rccoder/blog/issues/22)
- [bash(1) - Linux man page](https://linux.die.net/man/1/bash)
- [iterm2](https://www.iterm2.com/)
- [ohmyzsh](https://github.com/ohmyzsh/ohmyzsh)
- [powerlevel10k](https://github.com/romkatv/powerlevel10k)
- [这篇 iTerm2 + Oh My Zsh 教程手把手让你成为这条街最靓的仔](https://juejin.cn/post/6844904178075058189?searchId=202309121646431F1B4C30A1AF40D63A5C)
### 总结
- [State of JavaScript 2022](https://2022.stateofjs.com/en-US/)
- [2021 JavaScript Rising Stars](https://risingstars.js.org/2021/zh)
- [State of JS 2020](https://2020.stateofjs.com/zh-Hant/)
- [State of JS 2021](https://2021.stateofjs.com/zh-Hans/)
- [16 年毕业的前端 er 在杭州求职 ing](https://juejin.im/post/5a64541bf265da3e2d338862)
- [我在淘宝做前端的这三年 — 第一年](https://juejin.im/post/5c74d4b9e51d4512c37ea03b)
- [我在淘宝做前端的这三年 — 第二年](https://juejin.im/post/5c7dafe8f265da2de25bab27)
- [我在淘宝做前端的这三年 — 第三年](https://juejin.im/post/5c811e426fb9a04a0c2f3bdb)
- [阿里前端社招面试总结一位前端 2018 绝地求生记](https://juejin.im/post/5c90f573e51d450a7d7dfc75)
- [今天聊：你晋升失败的原因是什么](https://juejin.im/post/5e847b295188257375467466)
- [如何成为公司独当一面的工程师](https://juejin.im/post/5dd4cc71f265da0bca7899cf)
- [一名合格的程序员应该是什么样子](https://juejin.im/post/5d1574275188251a966bda58)
- [25 岁，毕业写前端的这三年](https://juejin.im/post/5cd8c361f265da03a33c5521)
- [第二届搞基建|堂主 - 如何推动前端团队的基础设施建设](https://juejin.im/post/5e644a65518825495d69bca6)
- [前端 API 层架构，也许你做得还不够](https://juejin.im/post/5de7169451882512454b18d8)
- [if 我是前端 Leader，谈谈前端框架体系建设](https://juejin.im/post/5decf88f51882512327a510a)
- [有赞开源项目最佳实践](https://juejin.im/post/5b03871df265da0ba6102022)
- [技术栈：小菜前端的技术栈是如何规划和演进的](https://juejin.im/post/5c99c17df265da6129788ae2)
- [滴滴后市场前端技术体系](https://juejin.im/post/5a3dd19b6fb9a0452846b159)
- [大型项目前端架构浅谈（8000 字原创）](https://juejin.im/post/5cea1f705188250640005472)
- [前端生产方式：过去 10 年回顾和未来 10 年展望](https://juejin.im/post/5e81874be51d4546d23bf9b4)
- [2019 年前端大事件回顾：流年笑掷，未来可期](https://juejin.im/post/5def782ce51d4558181d27ce)
- [一套比较完整的前端技术选型，需要规整哪些东西，你知道不？](https://juejin.im/post/5b28d4fbe51d45587b47fd43)
- [前端技术全景展望](https://juejin.im/post/5b8df06fe51d4538b9427998)
- [前端技术体系大局观](https://zhuanlan.zhihu.com/p/23185351)
- [精读《前端未来展望》](https://juejin.im/post/5d2d207b5188257aa971ee33)
- [阿里前端委员会主席圆心：未来前端的机会在哪里？](https://mp.weixin.qq.com/s?__biz=MzIzOTU0NTQ0MA==&mid=2247490769&idx=1&sn=7ee6e01045a6fe7e15f16aa33afcc2ad&chksm=e92921dede5ea8c8e93489271e8877d2e8688bd511b32e22c287b6c468904c5466b40f6a2bec&xtrack=1&scene=90&subscene=93&sessionid=1562203458&clicktime=15622)
- [哪些技术会决定前端开发者的未来发展？](https://juejin.im/post/5d1589c8e51d45776031b02e)