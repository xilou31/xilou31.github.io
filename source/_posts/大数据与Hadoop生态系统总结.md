---
abbrlink: 1842b797
date: 2021-06-05
description: 大数据
---
# 大数据概念理解

## 什么是大数据？

大数据（big data）：指无法在一定时间范围内用常规软件工具进行捕捉、管理和处理的数据集合，是需要新处理模式才能具有更强的决策力、洞察发现力和流程优化能力的海量、高增长率和多样化的信息资产。

主要解决：海量数据的存储和海量数据的分析计算问题。

按顺序给出数据存储单位：bit、Byte、KB、MB、GB、TB、PB、EB、ZB、YB、BB、NB、DB。

换算：1Byte = 8bit 1K = 1024Byte 1MB = 1024K 1G = 1024M 1T = 1024G 1P = 1024T

## 大数据特征

Volume（大量）：截至目前，人类生产的所有印刷材料的数据量是 200PB，而历史上全人类总共说过的话的数据量大约是 5EB。当前，典型个人计算机硬盘的容量为 TB 量级，而一些大企业的数据量已经接近 EB 量级。

Velocity（高速）：这是大数据区分于传统数据挖掘的最显著特征。根据 IDC 的“数字宇宙”的报告，预计到 2020 年，全球数据使用量将达到 35.2ZB。在如此海量的数据面前，处理数据的效率就是企业的生命。

Variety（多样）：这种类型的多样性也让数据被分为结构化数据和非结构化数据。相对于以往便于存储的以数据库/文本为主的结构化数据，非结构化数据越来越多，包括网络日志、音频、视频、图片、地理位置信息等，这些多类型的数据对数据的处理能力提出了更高要求。

Value（低价值密度）：价值密度的高低与数据总量的大小成反比。比如，在一天监控视频中，我们只关心健身那一分钟，如何快速对有价值数据“提纯”成为目前大数据背景下待解决的难题。

## 大数据应用场景？

物流仓储：大数据分析系统助力商家精细化运营、提升销量、节约成本。

零售：分析用户消费习惯，为用户购买商品提供方便，从而提升商品销量。

旅游：深度结合大数据能力与旅游行业需求，共建旅游产业智慧管理、智慧服务和智慧营销的未来。

商品广告推荐：给用户推荐可能喜欢的商品。

保险：海量数据挖掘及风险预测，助力保险行业精准营销，提升精细化定价能力。

金融：多维度体现用户特征，帮助金融机构推荐优质客户，防范欺诈风险。

房产：大数据全面助力房地产行业，打造精准投策与营销，选出更合适的地，建造更合适的楼，卖给更合适的人。

## 大数据有哪些部分组成？

### 大数据平台运维

平台软件(hadoop、spark、flink、kafka)的安装和维护
​

关于平台的性能的监测
​

平台的性能的调优

### 数据仓库

ETL 工程师：数据清洗
​

Hive 工程师:数据分析

### 数据挖掘

算法、建模

### 可视化

echarts、kylin、kibina
​

# Hadoop 深入理解

## 什么是 Hadoop?

Hadoop 是一个由 Apache 基金会所开发的分布式系统基础架构。
​

有三个组成：
​

1. hdfs:分布式的文件系统，主要解决大数据的储存问题

​

2. mapreduce:分布式的批量计算

​

3. yarn:分布式的资源管理组件

​

## Hadoop 的发展和发行版本？

#### ​

### Hadoop 发展历史

Lucene 是 Doug Cutting 开创的开源软件，用 java 书写代码，实现与 Google 类似的全文搜索功能，它提供了全文检索引擎的架构，包括完整的查询引擎和索引引擎
​

2001 年年底成为 Apache 基金会的一个子项目
​

对于大数量的场景，Lucene 面对与 Google 同样的困难
​

学习和模仿 Google 解决这些问题的办法 ：微型版 Nutch
​

可以说 Google 是 hadoop 的思想之源(Google 在大数据方面的三篇论文)
​

GFS —>HDFS
Map-Reduce —>MR
BigTable —>Hbase
​

2003-2004 年，Google 公开了部分 GFS 和 Mapreduce 思想的细节，以此为基础 Doug Cutting 等人用了 2 年业余时间实现了 DFS 和 Mapreduce 机制，使 Nutch 性能飙升
​

2005 年 Hadoop 作为 Lucene 的子项目 Nutch 的一部分正式引入 Apache 基金会。2006 年 3 月份，Map-Reduce 和 Nutch Distributed File System (NDFS) 分别被纳入称为 Hadoop 的项目中
​

名字来源于 Doug Cutting 儿子的玩具大象
​

Hadoop 就此诞生并迅速发展，标志这云计算时代来临

### Hadoop 三大发行版本

Hadoop 三大发行版本：Apache、Cloudera、Hortonworks。
​

Apache 版本最原始（最基础）的版本，对于入门学习最好。
​

Cloudera 在大型互联网企业中用的较多。
​

Hortonworks 文档较好。

## Hadoop 的优点？

1. 高可靠性：Hadoop 底层维护多个数据副本，所以即使 Hadoop 某个计算元素或存储出现故障，也不会导致数据的丢失。

​

2. 高扩展性：在集群间分配任务数据，可方便的扩展数以千计的节点。

​

3. 高效性：在 MapReduce 的思想下，Hadoop 是并行工作的，以加快任务处理速度。

​

4. 高容错性：能够自动将失败的任务重新分配。

## Hadoop 组成

在 Hadoop1.x 时代，Hadoop 中的 MapReduce 同时处理业务逻辑运算和资源的调度，耦合性较大。

HDFS（数据存储） Hadoop HDFS：一个高可靠、高吞吐量的分布式文件系统。
​

MapReduce（资源调度+计算） Hadoop MapReduce：一个分布式的资源调度和离线并行计算框架。
​

Common（辅助工具） Hadoop Common：支持其他模块的工具模块（Configuration、RPC、序列化机制、日志操作）。
​

在 Hadoop2.x 时代，增加了 Yarn。Yarn 只负责资源的调度，MapReduce 只负责运算。

### HDFS 架构概述

NameNode（nn）（主节点）：存储文件的元数据，如文件名，文件目录结构，文件属性（生成时间、副本数、文件权限），以及每个文件的块列表和块所在的 DataNode 等。

DataNode(dn)：在本地文件系统存储文件块数据，以及块数据的校验和。

Secondary NameNode(2nn)：用来监控 HDFS 状态的辅助后台程序，每隔一段时间获取 HDFS 元数据的快照。

### YARN 架构概述

ResourceManager(rm)：处理客户端请求、启动/监控 ApplicationMaster、监控 NodeManager、资源分配与调度；

NodeManager(nm)：单个节点上的资源管理、处理来自 ResourceManager 的命令、处理来自 ApplicationMaster 的命令；

ApplicationMaster：数据切分、为应用程序申请资源，并分配给内部任务、任务监控与容错。

Container：对任务运行环境的抽象，封装了 CPU、内存等多维资源以及环境变量、启动命令等任务运行相关的信息。

### MapReduce 架构概述

MapReduce 将计算过程分为两个阶段：Map 和 Reduce
​

Map 阶段：并行处理输入数据
​

Reduce 阶段：对 Map 结果进行汇总

## Hadoop 生态圈理解

​

### 协调与管理（Coordination and Management）

#### HCatalog

主要用来进行元数据管理。
概括来说，HCatalog 提供了一个统一的元数据服务，允许不同的工具如 Pig、MapReduce 等通过 HCatalog 直接访问存储在 HDFS 上的底层文件。

HCatalog 使用了 Hive 的元数据存储，这样就使得像 MapReduce 这样的第三方应用可以直接从 Hive 的数据仓库中读写数据。同时，HCatalog 还支持用户在 MapReduce 程序中只读取需要的表分区和字段，而不需要读取整个表。也就是提供一种逻辑上的视图来读取数据，而不仅仅是从物理文件的维度。

HCatalog 还提供了一个消息通知服务，这样对于 Oozie 这样的工作流工具，在数据仓库提供新数据时，可以通知到这些工作流工具。

HCatalog 主要解决了这样一个问题：将以前各自为政的数据处理工具（如 Hive、Pig、MapReduce）有机的整合在一起，使其相互之间能够顺畅合作，进而提升效率。

#### Ambari

主要是基于 web 管理 hadoop 的工具。
Apache Ambari 是一种基于 Web 的工具，支持 Apache Hadoop 集群的供应、管理和监控。

Apache Ambari 支持大多数 Hadoop 组件，包括 HDFS、MapReduce、Hive、Pig、Hbase、Zookeepr、Sqoop 和 Hcatalog 等的集中管理。也是 5 个顶级 hadoop 管理工具之一。

#### Zookepper

主要是配置信息数据同步。
​

Zookeeper 是 Google 的 Chubby 一个开源的实现。它是一个针对大型分布式系统的可靠协调系统，提供的功能包括：配置维护、名字服务、 分布式同步、组服务等。

ZooKeeper 的目标就是封装好复杂易出错的关键服务，将简单易用的接口和性能高效、功能稳定的系统提供给用户。

### 询问（Query）

#### Impala

主要是基于内存运算，大平台，数据更快。
​

Impala 是 Cloudera 公司主导开发的新型查询系统，它提供 SQL 语义，能查询存储在 Hadoop 的 HDFS 和 HBase 中的 PB 级大数据。已有的 Hive 系统虽然也提供了 SQL 语义，但由于 Hive 底层执行使用的是 MapReduce 引擎，仍然是一个批处理过程，难以满足查询的交互性。相比之下，Impala 的最大特点也是最大卖点就是它的快速。

Impala 支持内存中数据处理，它访问/分析存储在 Hadoop 数据节点上的数据，而无需数据移动。支持各种文件格式，如 LZO、序列文件、Avro、RCFile 和 Parquet。

#### Presto

主要是基于 sql 语句。
​

Presto 是一个开源的分布式 SQL 查询引擎，适用于交互式分析查询，是一种 Massively parallel processing (MPP)架构，多个节点管道式执⾏，⽀持任意数据源（通过扩展式 Connector 组件），数据量支持 GB 到 PB 字节。

#### Hive

主要是基于 sql 语句。
​

Hive 是基于 Hadoop 的一个数据仓库工具，可以将结构化的数据文件映射为一张数据库表，并提供简单的 sql 查询功能，可以将 sql 语句转换为 MapReduce 任务进行运行。

其优点是学习成本低，可以通过类 SQL 语句快速实现简单的 MapReduce 统计，不必开发专门的 MapReduce 应用，十分适合数据仓库的统计分析。

#### Pig

主要基于 sql 脚本。
​

Apache Pig 是 MapReduce 的一个抽象。它是一个工具/平台，用于分析较大的数据集，并将它们表示为数据流。Pig 通常与 Hadoop 一起使用；我们可以使用 Apache Pig 在 Hadoop 中执行所有的数据处理操作。

要编写数据分析程序，Pig 提供了一种称为 Pig Latin 的高级语言。该语言提供了各种操作符，程序员可以利用它们开发自己的用于读取，写入和处理数据的功能。

要使用 Apache Pig 分析数据，程序员需要使用 Pig Latin 语言编写脚本。所有这些脚本都在内部转换为 Map 和 Reduce 任务。Apache Pig 有一个名为 Pig Engine 的组件，它接受 Pig Latin 脚本作为输入，并将这些脚本转换为 MapReduce 作业。

优点：

不太擅长 Java 的程序员通常习惯于使用 Hadoop，特别是在执行任一 MapReduce 作业时。Apache Pig 是所有这样的程序员的福音。
​

使用 Pig Latin ，程序员可以轻松地执行 MapReduce 作业，而无需在 Java 中键入复杂的代码。
Apache Pig 使用多查询方法，从而减少代码长度。

### 数据管道（Data piping）

#### Sqoop

Sqoop 是一款开源的工具，主要用于在 Hadoop(Hive)与传统的数据库(mysql)间进行数据的传递，可以将一个关系型数据库（例如 ： MySQL ,Oracle 等）中的数据导进到 Hadoop 的 HDFS 中，也可以将 HDFS 的数据导进到关系型数据库中。

#### Flume

Flume 是 Cloudera 提供的一个高可用的，高可靠的，分布式的海量日志采集、聚合和传输的系统，Flume 支持在日志系统中定制各类数据发送方，用于收集数据；同时，Flume 提供对数据进行简单处理，并写到各种数据接受方（可定制）的能力。

### 核心 Hadoop（Core Hadoop）

#### HDFS

Hadoop HDFS：一个高可靠、高吞吐量的分布式文件系统。

HDFS （Hadoop Distributed File System）是 Hadoop 下的分布式文件系统，具有高容错(fault-tolerant)、高吞吐量(high throughput)等特性，可以部署在低成本(low-cost)的硬件上。

#### MapReduce

MapReduce 是一个分布式计算框架，用于编写批处理应用程序。编写好的程序可以提交到 Hadoop 集群上用于并行处理大规模的数据集。

MapReduce1.0:一个分布式的资源调度和离线并行计算框架。

MapReduce2.1:一个分布式的离线并行计算框架。

#### Yarn

Hadoop YARN：作业调度与集群资源管理的框架。

Apache YARN (Yet Another Resource Negotiator) 是 hadoop 2.0 引入的集群资源管理系统。用户可以将各种服务框架部署在 YARN 上，由 YARN 进行统一地管理和资源分配。

### 机器学习（Machine Learning）

#### Mahout

Apache Mahout 是个可扩展的机器学习和数据挖掘库，当前 Mahout 支持主要的 4 个用例：

推荐挖掘：搜集用户动作并以此给用户推荐可能喜欢的事物。
​

聚集：收集文件并进行相关文件分组。
​

分类：从现有的分类文档中学习，寻找文档中的相似特征，并为无标签的文档进行正确的归类。
​

频繁项集挖掘：将一组项分组，并识别哪些个别项会经常一起出现。

### NoSQL 数据库（NoSQL Database）

#### Hbase

HBase 是一个分布式的、面向列的开源数据库。

HBase 不同于一般的关系数据库，它是一个适合于非结构化数据存储的数据库。

### 扩展

#### Spark

Spark 是当前最流行的开源大数据内存计算框架。可以基于 Hadoop 上存储的大数据进行计算。 现在形成一个高速发展应用广泛的生态系统。

Apache Spark 是专为大规模数据处理而设计的快速通用的计算引擎。
​

Spark 是 UC Berkeley AMP lab (加州大学伯克利分校的 AMP 实验室)所开源的类 Hadoop MapReduce 的通用并行框架，Spark，拥有 Hadoop MapReduce 所具有的优点；但不同于 MapReduce 的是——Job 中间输出结果可以保存在内存中，从而不再需要读写 HDFS，因此 Spark 能更好地适用于数据挖掘与机器学习等需要迭代 MapReduce 的算法。

Spark 主要有三个特点 :

首先，高级 API 剥离了对集群本身的关注，Spark 应用开发者可以专注于应用所要做的计算本身。
​

其次，Spark 很快，支持交互式计算和复杂算法。
​

最后，Spark 是一个通用引擎，可用它来完成各种各样的运算，包括 SQL 查询、文本处理、机器学习等，而在 Spark 出现之前，我们一般需要学习各种各样的引擎来分别处理这些需求。

#### Tez

Tez 是一个 Apache 的开源项目，意在构建一个应用框架，能通过复杂任务的 DAG 来处理数据。
​

它是基于当前的 Hadoop Yarn 之上，换句话就是 Yarn 为其提供资源。

Tez 主要的两个设计目标:

增强终端用户使用 : 灵活的数据流定义 API；灵活的输入输出运行时模型(强调处理模型)；数据类型无关；简洁部署 。
​

高性能执行 ： 通过 MapReduce 提高性能；资源优化管理；执行时计划重定义；物理数据流的动态决策 。

#### Kafka

Kafka 是一种高吞吐量的分布式发布订阅消息系统，有如下特性：
​

1. 通过 O(1)的磁盘数据结构提供消息的持久化，这种结构对于即使数以 TB 的消息存储也能够保持长时间的稳定性能。

2. 高吞吐量：即使是非常普通的硬件 Kafka 也可以支持每秒数百万的消息。

3. 支持通过 Kafka 服务器和消费机集群来分区消息。

4. 支持 Hadoop 并行数据加载。

#### Storm

Storm 为分布式实时计算提供了一组通用原语，可被用于“流处理”之中，实时处理消息并更新数据库。这是管理队列及工作者集群的另一种方式。

Storm 也可被用于“连续计算”（continuous computation），对数据流做连续查询，在计算时就将结果以流的形式输出给用户。

#### Oozie

Oozie 是一个管理 Hdoop 作业（job）的工作流程调度管理系统。

Oozie 协调作业就是通过时间（频率）和有效数据触发当前的 Oozie 工作流程。

#### R 语言

R 是用于统计分析、绘图的语言和操作环境。R 是属于 GNU 系统的一个自由、免费、源代码开放的软件，它是一个用于统计计算和统计制图的优秀工具。
​
