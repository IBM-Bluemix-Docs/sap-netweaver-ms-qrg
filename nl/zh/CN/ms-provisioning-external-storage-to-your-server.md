---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, database server, deployment

subcollection: sap-netweaver-ms-qrg

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 向服务器添加外部存储器
{: #storage}

## 设置外部存储器
{: #set_up_storage}

如果想要将外部存储器用作备份设备或使用快照在测试环境中快速复原数据库，那么可以向供应的一个或多个服务器添加外部存储器。在示例中，块存储器用于归档数据库的日志文件以及联机和脱机备份数据库。选择了最快的块存储器 (10 IOPS/GB)，这有助于确保备份时间最短。较慢的块存储器可能已足够满足您的需求。有关 {{site.data.keyword.blockstoragefull}} 的更多信息，请参阅 [Block Storage 入门](/docs/infrastructure/BlockStorage?topic=BlockStorage-getting-started#getting-started)。

1. 使用您的唯一凭证登录到 [{{site.data.keyword.cloud_notm}} 基础架构客户门户网站 ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){: new_window}。
2. 选择**存储器** > **Block Storage**。
3. 单击 Block Storage 页面右上角的**订购 Block Storage**。
4. 选择适合您的存储需求的具体规格。表 1 包含建议值，包括适合要求苛刻的数据库工作负载的 10 IOPS/GB。

|字段                |值                                           |
| -------------------------------- | ------------------------------------------------- |
|位置                              |DAL10                                             |
|计费方式                          |每月（缺省值）                                    |
|新存储器大小                      |1000 GB                                           |
|存储器 IOPS 选项                  |耐久性（分层 IOPS）（缺省值）                     |
|耐久性分层 IOPS                   |10 GB                                             |
|快照空间大小                      |0 GB                                              |
|操作系统类型                      |Windows 2008+                                     |
{: caption="表 1. 块存储器的建议值" caption-side="top"}

5. 单击两个复选框，然后单击**下订单**。

## 授权主机
{: #authorize-host}

1. 单击 LUN 右侧的**操作**，并选择**授权主机**以访问供应的存储器。
2. 选择**设备**；**设备类型**缺省为“裸机服务器”。单击**硬件**并选择数据库服务器的主机名。
3. 单击**提交**。
4. 在**设备** >（选择您的设备）> **存储器**选项卡下检查供应的存储器的状态。
5. 记下您的服务器（iSCSI 启动器）的**目标地址**和 iSCSI 限定名 (IQN)，以及**用户名**和**密码**，以用于授权 iSCSI 服务器。该信息用于将块存储器连接到数据库服务器。

在样本部署中，从“存储器”选项卡检索的数据是
   * 目标 IP：`10.2.62.78`
   * IQN：`iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * 用户：`SL01SU276540-H896345`
   * 密码：`EtJ79F4RA33dXm2q`

执行[连接到 Microsoft Windows 上的 MPIO iSCSCI LUN](/docs/infrastructure/BlockStorage?topic=BlockStorage-mountingWindows#mountingWindows) 中的步骤，以使用上述数据将块存储器连接到数据库服务器。请谨慎执行这些步骤；执行这些步骤后，将有一个新的“脱机”磁盘可用于您的 Windows 服务器。

现在您可以将磁盘联机并进行初始化。
