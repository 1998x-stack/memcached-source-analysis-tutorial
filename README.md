# ⚙️ Memcached 源码分析

> ⚙️ 28章 实战体系

一套完整的 **Memcached 源码分析** 全中文实战课程体系，共 **28 章**。本课程以 HTML 可视化的形式呈现，从基础原理到工程实践循序渐进，适合系统性学习与复习。

## 🚀 快速开始

无需安装任何依赖，直接用浏览器打开 `index.html` 即可在线阅读全部章节：

```bash
open index.html   # macOS
# 或在浏览器中直接打开 index.html
```

## 📖 章节目录

| # | 章节 | 核心主题 |
|---|------|----------|
| 01 | 为什么要读Memcached源码 | 高性能缓存的意义、源码阅读方法论、C项目代码审美 |
| 02 | 环境搭建与源码获取 | 源码获取与编译、调试环境配置、版本选择与依赖 |
| 03 | 源码全景：目录结构与模块划分 | 文件结构一览、核心模块职责、模块间调用关系 |
| 04 | 启动流程：main函数逐行解析 | settings初始化、命令行解析、daemonize与信号 |
| 05 | 配置系统：settings与命令行 | settings结构体、growth_factor影响、-o扩展选项 |
| 06 | 日志与统计系统 | logger环形缓冲、stats三大体系、自定义stats指标 |
| 07 | 内存管理概览：slab allocator设计哲学 | malloc碎片问题、slab三层模型、slabclass_t结构体 |
| 08 | Slab Allocator初始化与分配 | slabs_init逐行解析、chunk对齐算法、page分配与切割 |
| 09 | Slab Allocator回收与平衡 | slots空闲链表、slab_rebalancer、slab_automove策略 |
| 10 | Item：数据存储的基本单元 | item结构体解析、CAS版本号机制、item内存布局 |
| 11 | Item生命周期：分配、访问与删除 | do_item_alloc流程、refcount引用计数、lazy expiration |
| 12 | LRU淘汰机制：三级队列 | HOT/WARM/COLD队列、lru_bump状态机、LRU crawler线程 |
| 13 | 哈希表：assoc模块详解 | 链地址法实现、assoc_find解析、MurmurHash3 |
| 14 | 哈希表扩容：渐进式rehash | 扩容触发条件、maintenance线程、双表查找逻辑 |
| 15 | 事件驱动：libevent集成 | event_base架构、event_handler回调、EV_PERSIST模式 |
| 16 | 连接状态机：drive_machine详解 | conn_states枚举、状态转换路径、transmit/try_read |
| 17 | 多线程模型：Master-Worker架构 | LIBEVENT_THREAD、管道唤醒机制、Round-Robin分发 |
| 18 | 并发控制：锁策略与无锁设计 | item分段锁、cache_lock、无锁路径分析 |
| 19 | ASCII协议：proto_text详解 | GET/SET/DELETE命令、noreply优化、CAS协议实现 |
| 20 | 二进制协议：proto_bin详解 | 24字节Header、opcode一览、SASL认证 |
| 21 | Meta Protocol：新一代协议 | 模式标志(M)、stale-while-revalidate、竞态条件防护 |
| 22 | External Storage：混合存储 | extstore架构、RAM+SSD分层、page管理与compaction |
| 23 | Built-in Proxy：Lua路由 | Proxy嵌入架构、路由策略实现、故障转移逻辑 |
| 24 | 测试体系：t目录与测试框架 | prove+Test::More、测试文件剖析、Valgrind集成 |
| 25 | 性能调优与生产踩坑 | 参数调优实战、hot_key解决方案、NUMA与TIME_WAIT |
| 26 | Memcached vs Redis/Valkey源码对比 | 架构与内存模型对比、rehash与I/O差异、Valkey开源格局 |
| 27 | Memcached的未来与社区生态 | 2025-2026路线图、替代方案对比、社区贡献指南 |
| 28 | 综合项目：手写Mini-Memcached | Slab+Hash+LRU实现、libevent网络层、压测与代码Review |

## 📂 项目结构

```text
memcached-source-analysis-tutorial/
├── index.html      # 课程主入口（在线阅读全部章节）
├── 01.html ~ 28.html   # 各章节正文
├── courses.json    # 课程元数据（标题/章节/主题）
└── theme.css       # 统一主题样式
```

## ✨ 课程特色

- **全中文实战体系**：面向中文读者，由浅入深，覆盖原理与工程实践
- **28 章完整内容**：系统化章节编排，形成完整知识闭环
- **可视化呈现**：HTML 图文并茂，适合快速浏览与重点回顾
- **即开即用**：无需构建、无需服务器，纯静态页面随开随看

---
*本课程由 `memcached-source-analysis-tutorial/` 项目维护。*