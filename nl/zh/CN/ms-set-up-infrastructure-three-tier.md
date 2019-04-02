---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, bring your own license, BYOL, VLAN, application server, database server, three-tier, SAP certified servers

subcollection: sap-netweaver-ms-qrg

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. 订购三层设置的 192 GB 和 32 GB 服务器
{: #install_three_tier}

执行[订购 32 GB 服务器](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-install_32GB)中的步骤以订购 SAP NetWeaver 应用程序服务器。以下步骤将指导您执行订购数据库服务器的过程。在后续步骤中将供应外部存储器以作为数据库的备份空间，用于存储归档的日志文件和联机完全备份。

## 订购数据库服务器
{: #order_db_servers}

1. 使用您的唯一凭证登录到 [{{site.data.keyword.cloud}} 基础架构客户门户网站 ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com){: new_window}。
2. 单击“帐户摘要”页面上的**帐户** > **下订单**。
3. 在“设备”页面上的 **{{site.data.keyword.baremetal_long}}** 下单击**每月**。将显示“服务器列表”对话框。
4. “SAP 认证的服务器”位于列表顶部。单击**每月的起始价格**下的超链接以选择服务器 **BI.S3.NW192（操作系统选项）**。

BI.S3.NW32（操作系统选项）服务器也可用于**按小时**计费。
{: note}

## 配置数据库服务器
{: #configure_server}

1. 在**数量**字段中保留 **1** 不变。
2. 选择 **DAL10** 作为**数据中心**。数据中心列表取决于特定数据中心内的产品可用性。
3. **服务器**缺省为基于所选服务器的预定义值，并且无法更改。
4. 单击 **192 GB RAM**（尽管 **RAM** 选项缺省为基于所选服务器的预定义值并且无法更改）。
5. 选择所选的 Microsoft Windows 版本作为**操作系统**。**注**：如果您自带许可证 (BYOL) 用于操作系统，请选择**其他** > **无操作系统**。有关更多信息，请参阅[自带许可证](#byol)。

6. 通过验证**磁盘控制器 1** 是否缺省为 **2 TB SATA** 来添加第二个 2 TB SATA 驱动器。单击**添加磁盘**。
7. 单击**选择所有磁盘**，然后单击**创建 RAID 存储器组**。
8. 单击**类型**，然后选择 **RAID 1**。输入一个能涵盖所需总存储量的**大小**。
9. 保持 **LVM** 未选中，接受缺省**分区模板** (**Windows Basic**)。
10. 单击**完成**。

##选择其他服务器选项
{: #options_256GB}

1. 为**公用带宽**选择 **500 GB**。
2. 为**上行端口速度**选择 **1 Gbps 冗余公用和专用网络上行链路**。
3. 所有其他字段均采用缺省值即可。有关详细的选项描述，请参阅 [Building a custom bare metal server](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server)。
4. 单击页面底部的**添加到订单**。在验证订单后，您将重定向到“结帐”页面。

## 设置高级系统配置
{: #adv_config}

将表 1 中的值用于“高级系统配置”下的字段。[高级服务器配置选项](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server)准则中提供了更多信息。

|字段                |值                                                              |
| -------------------------------- | -------------------------------------------------------------------- |
|后端 VLAN                         |从下拉列表中进行选择，例如，`dal10.bcr01a.981`      |
|子网                              |从下拉列表中进行选择，例如，`10.177.119.192/26`     |
|前端 VLAN                         |从下拉列表中进行选择，例如，`dal10.fcr01a.926`      |
|子网                              |从下拉列表中进行选择，例如，169.46.15.96/27                          |
|供应脚本                          |保持为空                                                             |
|SSH 密钥                          |缺省为 `Add`，这意味着没有 SSH 密钥                 |
|主机名                            |例如，`sdb192`                                      |
|域                                |例如，`saptest.com`                                 |
{: caption="表 1. 高级系统配置值" caption-side="top"}

## 确认您的选择
{: #confirm_selections}

1. 在“结帐”页面上确认您的选择，然后单击页面右侧的**云服务条款**和**第三方软件协议**。
2. 单击**提交订单**。您将重定向到带有您的订单号的屏幕。可以打印此屏幕，因为这也是您的订单回执。

提交订单后，服务器将在一到四个小时（具体取决于您的订单）内可供使用。您可以在“客户门户网站”主页面上的“设备详细信息”屏幕（**设备 ** > 设备列表**）中检查供应步骤的状态。单击与您的给定“主机名”和“域”匹配的**设备名称**以查看其状态。

## 自带许可证
{: #byol}

如果有自己的操作系统许可证，请按照供应商的指示信息将其安装在 {{site.data.keyword.baremetal_short}} 上。有关更多信息，请参阅[无操作系统选项](/docs/bare-metal?topic=bare-metal-the-no-os-option)。

## 后续步骤

  [2. 准备服务器以用于 SAP 安装](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-prepare_256GB)

  [3. 分区和文件系统](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-3-partitioning-and-file-systems)

  [4. 准备网络](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-network)
