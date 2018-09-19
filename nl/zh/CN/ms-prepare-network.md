---



copyright:
  years: 2017, 2018
lastupdated: "2018-07-12"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 4. 为三层设置准备网络
{: #network}

如果您计划安装三层设置，需要相应准备网络设置。对于样本设置，已部署 192 GB 数据库服务器（名为 `sdb192`）和 32 GB 应用程序服务器（名为 `e2e1270`）。数据库服务器还托管了 ABAP SAP Central Services (ASCS) 实例。将专用网络上的 IP 添加到 hosts 文件有助于执行后续步骤，并可确保 SAP 内部网络流量流经正确的网络。

已部署服务器的网络设置位于 Microsoft Windows 中的“网络连接”下。在样本设置中，`10.17.139.35` 是位于“网络连接 - 专用网络 Teamed”下的数据库服务器的专用 IP，并且是 RFC 1597 中的 IP 范围之一。您也可以确定应用程序服务器的 IP 地址，并将这两个 IP 添加到这两个服务器的 `C:\Windows\System32\drivers\etc` 下的 `hosts` 文件。

## 后续步骤

  * [向 {{site.data.keyword.baremetal_short}} 添加外部存储器](/docs/infrastructure/sap-netweaver-ms-qrg/ms-provisioning-external-storage-to-your-server.html)
  * [安装 SAP 应用程序和软件](/docs/infrastructure/sap-netweaver-ms-qrg/ms-installing-your-SAP-landscape.html)
