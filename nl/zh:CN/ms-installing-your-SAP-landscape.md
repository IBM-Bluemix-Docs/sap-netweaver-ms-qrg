---



copyright:
  years: 2017, 2018
lastupdated: "2018-02-09"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 安装 SAP 场景
{: #install_landscape}

## 下载 SAP 软件
{: #download_software}

您需要 SAP S 用户标识和“下载授权”才能下载 DVD。有关 SAP S 用户标识的更多信息，请参阅[如何设置 S 用户标识](https://www.sapappsdevelopmentpartnercenter.com/en/faq/program-faqs_2/how-to-receive-an-s-user-to-access-the-s_77)。

1. 登录到 [SAP Service Marketplace](https://websmp201.sap-ag.de/) 并将必需的 DVD 下载到本地共享驱动器。
2 将文件传输到为您供应的服务器。 

另一个选项是下载 [SAP Software Download Manager](https://support.sap.com/en/my-support/software-downloads.html#section_995042677)，将其安装在目标服务器上，然后直接将 DVD 映像下载到该服务器。 

## 安装 SAP 软件
{: #install_software}

下载安装介质后，请执行您的 SAP 版本和组件的 SAP 安装指南以及对应 SAP 说明中记录的标准 SAP 安装过程。有关更多信息，请参阅 [SAP 安装指南](https://service.sap.com/instguides)和 [SAP 说明](https://support.sap.com)。两者都需要 SAP S 用户标识。

1. 以 Administrator 身份打开 SWPM-DVD 或安装主 DVD 的根文件夹，然后运行 `sapinst`。将显示“欢迎安装 SAP”页面。
2. 选择 **SAP NetWeaver 7.5** > **IBM Db2 for Linux, Unix, and Windows** > **SAP Systems** > **应用程序服务器 ABAP**。
3. 打开**分布式系统**，然后运行数据库服务器上的 **ASCS 实例**和**数据库实例**。
4. 验证 `sapinst` 是否在安装 ASCS 实例后成功共享了文件夹 `\\sapmnt` 和 `\\user\sap\trans`，以使下一步能正常运作。
5. 在应用程序服务器上运行**主应用程序服务器实例**。请确保在应用程序服务器安装期间使用 ASCS 的专用地址和数据库主机名。这可确保应用程序服务器和 ASCS 或数据库之间的网络流量流经专用网络而非公用网络。

现在您可以根据 SAP 安装指示信息运行 SAP 安装。

