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

# 4. 準備網路進行三層設定
{: #network}

如果您計劃安裝三層設定，則需要相應地準備網路設定。針對範例設定，已部署 192 GB 資料庫伺服器（名為 `sdb192`）及 32 GB 應用程式伺服器（名為 `e2e1270`）。資料庫伺服器也會管理「ABAP SAP 中央服務 (ASCS)」實例。將專用網路上的 IP 新增至 hosts 檔案，協助進行即將進行的步驟，並確保 SAP 內部網路資料流量通過正確的網路。

在 Microsoft Windows 中，於「網路連線」下找到已部署伺服器的網路設定。在範例設定中，`10.17.139.35` 是「網路連線 - 專用網路協作」下所找到之資料庫伺服器的專用 IP，而且是 RFC 1597 中的其中一個 IP 範圍。您也可以判斷應用程式伺服器的 IP，並將兩個 IP 新增至兩部伺服器之 `C:\Windows\System32\drivers\etc` 下的`主機檔`。

## 後續步驟

  * [將外部儲存空間新增至 {{site.data.keyword.baremetal_short}}](/docs/infrastructure/sap-netweaver-ms-qrg/ms-provisioning-external-storage-to-your-server.html)
  * [安裝 SAP 應用程式及軟體](/docs/infrastructure/sap-netweaver-ms-qrg/ms-installing-your-SAP-landscape.html)
