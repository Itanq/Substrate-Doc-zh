# Overview
此页是substrate文档的入口。

>**一些专业知识**  
>为了更好的发挥substrate的潜能，你应该对区块链和基本的密码学要有一些了解。像（区块）头，区块，客户端，哈希，交易以及签名都应该要熟悉。目前你需要会rust编程知识，这样才有能力对substrate做任何有意义的定制/适配（尽管我们的目标并不是这个（译注：指深入学习rust））。

Substrate 是一个带有完全通用状态转换功能的区块链开发框架以及用于共识，网络和配置的模块组件。

尽管它是“完全通用”的，但它同时也自带了一个标准和规范 - 特别是 substrate 运行时模块库（a.k.a FRAME）- 由于底层数据结构对 STF 的支持，从而使得快速开发区块链成为可能。

## 用法
![usage](https://substrate.dev/docs/assets/technical-freedom.png)

Substrate被设计用在下面三种方式之一：
1. Substrate 节点：你可以运行预先设计的 substrate 节点并使用包含默认的节点运行时的创世块来配置它。这种情况，你仅仅需要配置一个 Json 文件就可以发起你自己的区块链了。这种定制化程度最小，仅允许你改变运行时模块的初始参数，比如：平衡，标定线（staking），区块周期，费用，治理，等等。。关于这部分的教程，请看 [使用 Substrate 启动私有网络](https://substrate.dev/docs/en/tutorials/start-a-private-network/)。
2. Substrate FRAME：使用FRAME你可以很简单的创建你自己自定义的区块链。 这种情况，你对你自己的区块链逻辑有很大的自由，允许你改变数据类型，选择模块中库，以及添加你自定义的模块。 大多数内容都是可以更改的，只要不触及区块创建的逻辑，因为他是通过链上逻辑进行定向的。如果是这种情况，那么可以使用现存的 substrate 二进制程序来进行区块创建和同步。如果需要更改区块创建的逻辑，那么这个新的区块创建程序必须被编译成一个独立的项目，并有验证器使用。这就是波卡中继链怎么被构建并满足未来几乎所有需求的原因。关于这方面更多的教程，请看 [创建你第一个 Substrate 链](https://substrate.dev/docs/en/tutorials/。creating-your-first-substrate-chain/)。
3. Substrate 核心：整个 FRAME 都可以被忽略，并且整个运行时都可以被重新设计和实现。这可以使用任何可被编译到 webassembly 的语言实现。如果运行时（指你自己重新设计和实现的）可以兼容 Substrate 节点创建区块的抽象逻辑，那么你可以简单的从wasm blob构造一个新的创世区块并且在现存的基于rust的 Substrate的客户端上启动你的（区块）链。否则的话，你就需要更改客户端创建区块的逻辑，甚至可能需要更改（区块）头和区块序列化的格式。就开发工作而言，这种是你使用substrate最困难的方式，但它给了你创新的最大自由。

## 下一步

### 了解更多
* 查看我们的开发者文档以便[使用 FRAME 来进行模块开发](https://substrate.dev/docs/en/development/module/)

### 样例
* 跟着我们的教程[使用 Substrate 创建你自己的第一个自定义的区块链](https://substrate.dev/docs/en/tutorials/creating-your-first-substrate-chain/index)。
* 跟着我们的教程[使用 Substrate 启动一个私有网络](https://substrate.dev/docs/en/tutorials/start-a-private-network-with-substrate)。
* 跟着我们的教程[在你自己的 Substrate 运行时里添加一个运行时模块](https://substrate.dev/docs/en/tutorials/adding-a-module-to-your-runtime)。