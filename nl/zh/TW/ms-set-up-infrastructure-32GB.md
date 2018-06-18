---



copyright:
  years: 2017
lastupdated: "2018-02-26"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. 訂購 32 GB 伺服器
{: #install_32GB}

## 訂購伺服器
{: #order_32GB}

1. 使用唯一的認證來登入 [{{site.data.keyword.cloud_notm}} 基礎架構客戶入口網站](https://control.softlayer.com)。
2. 在「帳戶摘要」頁面上，按一下**裝置**。
3. 在「裝置」頁面上，按一下「裸機伺服器」下的**每月**。即會出現「伺服器清單」對話框。
4. 按一下**每個月的起始價格**下的超鏈結，以選取伺服器 **BI.S1.NW32（OS 選項）**。

## 選取伺服器選項
{: #options_32GB}

1. 在**數量**欄位中，保留 **1**。
2. 針對**資料中心**，選取 **DAL10**。資料中心清單取決於特定資料中心內的產品可用性。
3. 根據伺服器選取項目，將**伺服器**預設為預定值，並且無法進行變更。
4. 按一下 **32 GB RAM**，即使根據伺服器選取項目，將 **RAM** 選取項目預設為預定值並且無法進行變更也是一樣。
5. 選取您選擇的 Microsoft Windows 版本作為**作業系統**。
6. 在**硬碟**下，選取類型與第一個磁碟相同的第二個磁碟，並從兩個磁碟中建立涵蓋儲存空間總數量的 RAID 儲存空間群組 RAID1，然後選擇 **Windows 基本**作為**分割區範本**。保留不勾選 **LVM**。
7. 針對**公用頻寬**，選取 **500 GB**。
8. 針對**上行鏈路埠速度**，選取 **1 Gbps 備援公用及專用網路上行鏈路**。
9. 針對此範例安裝，保留所有其他欄位的預設值。如需詳細選項說明，請參閱[設定裸機伺服器](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers)。
10. 按一下頁面底端的**新增至訂單**。驗證訂單之後，會將您重新導向至「結帳」頁面。

## 設定進階系統配置
{: #adv_config}

使用「表 1」中「進階系統配置」下欄位的值。如需相關資訊，請參閱[進階系統配置](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration)準則。

1. 向下捲動，並輸入「表 1」中**進階系統配置**下的值。

|              欄位                |      值                                                              |
| -------------------------------- | -------------------------------------------------------------------- |
|後端 VLAN                         | 從下拉清單中進行選取，例如，`dal10.bcr01a.981`                       |
|子網路                            | 從下拉清單中進行選取，例如，`10.177.119.192/26`                      |
|前端 VLAN                         | 從下拉清單中進行選取，例如，`dal10.fcr01a.926`                       |
|子網路                            | 從下拉清單中進行選取，例如，`169.46.15.96/27`                        |
|佈建 Script                       | 預設為「無」                                                         |
|SSH 金鑰                          | 新增                                                                 |
|主機名稱                          | 例如，`e2e1270`                                                      |
|網域                              | 例如，`saptest.com`                                                  |
{: caption="表 1. 32 GB 進階配置值" caption-side="top"}  

## 確認選取項目
{: #confirm_selections}

1. 在「結帳」頁面上確認您的選取項目，然後按一下頁面右側的**雲端服務條款**及**協力廠商軟體合約**。
2. 按一下表單右側的**提交訂單**。會將您重新導向至具有訂單號碼的頁面。您可以列印頁面，因為它也是訂單收據。此外，您還會收到主旨為*已核准 IBM Cloud 訂單 ##* 的確認電子郵件，而 ## 是您的訂單號碼。

提交訂單之後，可以在一到四個小時內使用伺服器（根據訂單）。您可以檢查主要「客戶入口網站」頁面上的「裝置詳細資料」畫面（**裝置** > **裝置清單**），以了解佈建步驟的狀態。按一下符合您給定「主機名稱」及「網域」的**裝置名稱**，以查看其狀態。

## 後續步驟

  [2. 準備伺服器進行 SAP 安裝](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-32GB.html)
  
  [3. 分割及檔案系統](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-32GB.html)
