---
abbrlink: 1c4cd1f0
date: 2021-06-03
description: Summer Code 2021 Seata Proposal
---
## 项目背景

在现在的版本，Seata 中 RM、TM 之间的通信，使用的是自定义的一个协议，再使用 ProtoBuf 来进行序列化的操作，协议的格式如下。
![seata_protobuf.png](seata_protobuf.png)
因为以后要支持多语言，出于多语言的兼容问题，现需要将 Seata 的通信协议拓展支持 HTTP2。

## HTTP2 跟 HTTP1.1 有什么区别

1. 多路复用
1. 头部压缩
1. 二进制分帧
1. 请求优先级
1. 服务器推送

## 方案描述

#### 打包、拆包（头部压缩、二进制分帧）

1. 修改 ProtocolV1Decoder、ProtocolV1Encoder，抽象为 ProtocolDecoder、ProtocolEncoder。
1. 增加 ProtocolHTTP2Decoder、ProtocolHTTP2Encoder
1. 将传输单元定义为 Frame，做进一步抽象。
1. 在源码中加入 HPACK 算法的实现，用于 Header Frame 的压缩。

#### HTTP 连接多路复用

1. 在 NettyBaseConfig、TransportProtocolType 等类中，加入 HTTP2 的支持。
1. 增加 AbstractNettyRemoting 中，对 Http2Stream 的创建

## 时间规划

- 尝试自己做一个 HTTP2 的 NettyServer 的 Demo
  - 7.1 - 7.10
  - 阅读 Netty 关于 HTTP2 相关文档，并实现 Demo
- 用 Wireshark 抓包分析并修改 Demo
  - 7.10 - 7.15
  - 主要看 Headers 是否压缩，是否实现二进制分帧等等
- 在 Seata 中尝试修改源码
  - 7.15 - 7.30
  - 尝试修改上述方案描述所提到的相关类
- 性能测试，若性能不佳则找出原因
  - 7.30 - 8.7
  - 会测试 HTTP2 和原本私有协议之间的性能差距
- 代码重构
  - 8.7 - 8.20
  - 结合 Seata 社区的意见，对提交的代码进行修改或者重构
- 书写相关的文档
  - 8.20 - 8.30
  - 针对两个月以来的成果书写文档

## 参考资料

[Use Protobuf as the codec of RPC（Seata Issues#823 ）](https://github.com/seata/seata/issues/823)
[New RPC protocol propose. （Seata Issues#893）](https://github.com/seata/seata/issues/893)
[RFC7540（HTTP/2）](https://datatracker.ietf.org/doc/html/rfc7540)
[RFC7541（HPACK）](https://datatracker.ietf.org/doc/html/rfc7541)
[gRPC over HTTP2](https://grpc.github.io/grpc/core/md_doc__p_r_o_t_o_c_o_l-_h_t_t_p2.html)
