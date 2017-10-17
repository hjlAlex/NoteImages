# MongoDB 简介 #

### 本页面对以下知识简介 ###
> * [文档型数据库](https://docs.mongodb.com/manual/introduction/#document-database "https://docs.mongodb.com/manual/introduction/#document-database")
> * [主要特性](https://docs.mongodb.com/manual/introduction/#key-features "https://docs.mongodb.com/manual/introduction/#key-features")

MongoDB是一个开源的文档数据库，可提供高性能，高可用性和自动缩放等特性。

## 文档型数据库 ##
> MongoDB中的一个记录是一个文档，它是一个由字段和值对组成的数据结构。MongoDB的文档类似于JSON对象。其字段的值可能包括其他文档，数组和文档数组。

![MongoDB文档结构](images/mongodb-document.svg "MongoDB文档结构")

> ### 使用文档记录的优点有: ###
 * 文档（即对象）对应于许多编程语言中的本机数据类型。
 * 嵌入式文档和数组减少了昂贵的连接的需要。
 * 动态模式支持流畅的多态(不同于关系型数据库，字段模式固定)。

## 主要特性 ##
### 高性能 ###
MongoDB提供高性能数据持久性。尤其是：
> * 支持嵌入式数据模型可减少数据库系统上的I / O活动。
> * 索引支持更快的查询，并且可以包括来自嵌入文档和数组的键。
### 丰富的查询语言 ###
MongoDB支持丰富的查询语言来支持读写操作（CRUD）以及：
> * 数据汇总(聚合)。
> * 文本搜索和地理空间查询。
### 高可用性 ###
MongoDB的复制工具，称为副本集，提供：
> * 自动故障转移。
> * 数据冗余。

复制集是一组MongoDB服务器，它们保持相同的数据集，提供冗余和增加数据可用性。
### 水平可扩展性 ###
MongoDB提供了可扩展性，作为其核心功能的一部分：
> * 分片通过一组机器分发数据。
> * MongoDB 3.4支持基于分片键创建数据区域。在平衡的集群中，MongoDB将区域覆盖的读写操作仅指向区域内的分片。有关详细信息，请参阅“区域”手册页。
### 支持多存储引擎 ###
MongoDB支持多种存储引擎，如：
> * WiredTiger存储引擎
> * MMAPv1存储引擎

此外，MongoDB还提供可插拔的存储引擎API，允许第三方为MongoDB开发存储引擎。



----------
# 入门 #
## MongoDB Atlasl ##
> MongoDB Atlas是一个云托管服务，用于配置，运行，监控和维护MongoDB部署。 MongoDB是一种快速，简单，自由的方式。要在本地安装和运行MongoDB，请参阅安装MongoDB。**本教程使用本地按照的MongoDB作为例子**

## Mongo Shell ##
以下教程使用mongo shell连接到本地的MongoDB，插入数据和执行查询操作。

## 文档和集合 ##
MongoDB将数据存储为集合中的BSON文档（JSON的二进制表示）。 MongoDB数据库包含文档集合。

## 插入文档 ##
db.collectionName.insertMany()可以将多个文档插入到集合中，可以将一系列文档传递给该方法。如往集合inventory中添加多个文档记录，使用下面语句:   
<blockquote>
db.inventory.insertMany([   
   { item: "journal", qty: 25, status: "A",
       size: { h: 14, w: 21, uom: "cm" }, tags: [ "blank", "red" ] },
   { item: "notebook", qty: 50, status: "A",
       size: { h: 8.5, w: 11, uom: "in" }, tags: [ "red", "blank" ] },
   { item: "paper", qty: 100, status: "D",
       size: { h: 8.5, w: 11, uom: "in" }, tags: [ "red", "blank", "plain" ] },
   { item: "planner", qty: 75, status: "D",
       size: { h: 22.85, w: 30, uom: "cm" }, tags: [ "blank", "red" ] },
   { item: "postcard", qty: 45, status: "A",
       size: { h: 10, w: 15.25, uom: "cm" }, tags: [ "blue" ] }
]);
</blockquote>
insertMany()返回包含新插入的文档_id字段值的文档。如图:
![插入多条文档记录](images/insertmany.png "插入多条文档记录")

使用db.collectionName.insertOne（）插入单个文档。

有关更多信息和示例，请参阅在CRUD部分插入文档。

未完待续https://docs.mongodb.com/manual/tutorial/getting-started/

