---



copyright:
  years: 2017, 2018
lastupdated: "2018-07-09"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 安裝 SAP 態勢
{: #install_landscape}

## 下載 SAP 軟體
{: #download_software}

您需要 SAP S 使用者 ID 及「下載授權」來下載 DVD。如需 SAP S 使用者 ID 的相關資訊，請參閱[如何設定 S 使用者 ID](https://www.sapappsdevelopmentpartnercenter.com/en/faq/program-faqs_2/how-to-receive-an-s-user-to-access-the-s_77)。

1. 登入 [SAP Support Portal](https://support.sap.com/en/index.html)、按一下 **Download Software**，並將必要 DVD 下載至本端共用磁碟機。
2. 將檔案傳送至已佈建的伺服器。 

另一個選項是下載 [SAP 軟體下載管理員](https://support.sap.com/en/my-support/software-downloads.html#section_995042677)，並將它安裝至目標伺服器，然後將 DVD 映像檔直接下載至伺服器。 

## 安裝 SAP 軟體
{: #install_software}

下載安裝媒體之後，請遵循您 SAP 版本及元件之 SAP 安裝手冊中所記錄的標準 SAP 安裝程序，以及對應的「SAP 注意事項」。如需相關資訊，請參閱 [SAP 安裝手冊](https://service.sap.com/instguides)及 [SAP 注意事項](https://support.sap.com)。兩者都需要 SAP S 使用者 ID。

1. 以「管理者」身分開啟 SWPM-DVD 或安裝主要 DVD 的根資料夾，然後執行 `sapinst`。即會顯示「歡迎使用 SAP 安裝」頁面。
2. 選取 **SAP NetWeaver 7.5** > **IBM Db2 for Linux, Unix, and Windows** > **SAP 系統** > **應用程式伺服器 ABAP**。
3. 開啟**分散式系統**，然後在資料庫伺服器上執行 **ASCS 實例**及**資料庫實例**。
4. 安裝「ASCS 實例」讓下一步運作之後，請驗證 `sapinst` 已順利共用資料夾 `\\sapmnt` 及 `\\user\sap\trans`。
5. 在應用程式伺服器上，執行**主要應用程式伺服器實例**。請務必在安裝應用程式伺服器期間使用 ASCS 及資料庫主機名稱的專用位址。這確保應用程式伺服器與 ASCS（或資料庫）路徑之間的網路資料流量（透過專用網路，而不是透過專用網路）。

您現在可以根據 SAP 安裝指示來執行 SAP 安裝。

