# KafkaLume

A Windows desktop GUI for Apache Kafka — cluster management, message browsing, and consumer lag monitoring.

Apache Kafka 桌面可视化管理工具，支持集群管理、消息浏览与消费积压监控。

KafkaLume 直接连接你指定的 Kafka 集群，无需部署额外的 Web 服务端。

## 主要功能

- **集群与主题管理**：保存多个连接，查看 Broker、主题、分区和副本，创建主题、增加分区及调整主题配置。
- **消息浏览与查询**：浏览历史消息、实时追踪新消息，按分区、偏移量等条件查询，并导出消息。
- **消息发送与重放**：发送消息，设置消息键和 Header，支持单条及批量重放。
- **消费组与积压分析**：查看成员、消费进度和分区积压，记录本机采样趋势，预览并调整消费位置。
- **集群健康诊断**：检查分区、副本及消费积压等风险，导出健康检查报告。
- **辅助运维**：告警记录、操作审计、Schema Registry 浏览与消息解码。

## 下载

当前提供 **Windows x64 免安装版**。

前往 [Releases](https://github.com/ludaming666/kafkalume/releases) 查看发布版本，下载 `KafkaLume-Portable-<版本号>.exe` 后运行。

如果 Releases 页面暂时没有版本或附件，说明发布包尚未上传，请稍后再查看。

KafkaLume 是 Kafka 客户端，不包含 Kafka Broker。使用前需要准备可访问的 Kafka 集群。

## 快速开始

1. 运行免安装版，点击“添加第一个 Kafka 连接”。
2. 填写连接名称和 Broker 地址，例如 `localhost:9092`；多个地址使用英文逗号分隔。
3. 如集群启用了认证，在高级设置中配置 SSL / TLS、SASL 等信息。
4. 测试连接并保存，即可浏览主题、消息和消费组。

连接远程集群时，除了填写的入口地址，Kafka 返回的 Broker 地址也必须能从你的电脑访问。请检查集群的 `advertised.listeners` 配置及网络连通性。

## 操作说明

- **浏览消息不会推进业务消费进度**：消息浏览不会加入业务消费组，也不会提交消费组偏移量。
- **写入操作需要谨慎**：发送、重放、删除主题、修改配置和调整消费位置等操作会改变 Kafka 数据或状态，请确认目标集群及影响范围。
- **监控依赖程序运行**：开启监控后，留在托盘可继续检查；退出程序或电脑关机后，监控停止，关闭期间不会补造趋势样本。
- **重要环境先验证**：请先在测试环境验证高风险操作，并保留必要备份。

## 免费测试版与源码

KafkaLume 当前以免费测试版提供，具体使用条件见 [使用条款](TERMS.md)。

本公开仓库用于项目介绍、版本分发及问题反馈，**目前未公开软件源码**；公开仓库不代表软件采用开源许可证。

## 隐私与安全

连接配置和本地历史记录保存在使用者电脑上。用户配置机器人通知后，相关告警信息会发送到所选第三方服务。详细的数据处理、保存和删除说明见 [隐私政策](PRIVACY.md)。

请勿在公开 Issues、截图、日志或导出文件中泄露密码、证书、消息正文及敏感业务信息。

当前发布构建尚未进行 Windows 代码签名，首次运行可能出现安全提示。请核对下载来源，不要为运行软件而长期关闭安全防护。

English documents: [Privacy Policy](PRIVACY.en.md) · [Terms of Use](TERMS.en.md)

## 问题反馈

请通过 [GitHub Issues](https://github.com/ludaming666/kafkalume/issues) 反馈问题，建议提供：

- KafkaLume 版本、Windows 版本及 Kafka 版本；
- 复现步骤、预期结果和实际结果；
- 经过脱敏处理的截图或错误日志。

联系邮箱：**kafkalume@gmail.com**

发布者：[ludaming666](https://github.com/ludaming666)

## 项目说明

KafkaLume 是独立桌面工具，不代表获得 Apache Software Foundation 或相关第三方的认可或授权。软件包含的第三方组件分别适用其自身许可证。
