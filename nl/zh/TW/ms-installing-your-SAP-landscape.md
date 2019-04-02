---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, ABAP, ASCS Instance, Database Instance, ABAP SAP Central Services, SWPM, application server, database server

subcollection: sap-netweaver-ms-qrg


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

您需要 SAP S 使用者 ID 及「下載授權」來下載 DVD。如需 SAP S 使用者 ID 的相關資訊，請參閱[如何設定 S 使用者 ID ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](https://www.youtube.com/watch?v=4wICiRTP8u0/){: new_window}。

1. 登入 [SAP Support Portal ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](https://support.sap.com/en/index.html){: new_window}、按一下 **Download Software**，並將必要 DVD 下載至本端共用磁碟機。
2. 將檔案傳送至已佈建的伺服器。

另一個選項是下載 [SAP Software Download Manager ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](https://support.sap.com/en/my-support/software-downloads.html#section_995042677){: new_window}，並將它安裝至目標伺服器，然後將 DVD 映像檔直接下載至伺服器。

## 安裝 SAP 軟體
{: #install_software}

下載安裝媒體之後，請遵循您 SAP 版本及元件之 SAP 安裝手冊中所記錄的標準 SAP 安裝程序，以及對應的「SAP 注意事項」。如需相關資訊，請參閱 [SAP Installation Guide ![External link icon](../icons/launch-glyph.svg "External link icon")](https://service.sap.com/instguides){: new_window} and [SAP Notes ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](https://support.sap.com){: new_window}。兩者都需要 SAP S 使用者 ID。

1. 以「管理者」身分開啟 SWPM-DVD 或安裝主要 DVD 的根資料夾，然後執行 `sapinst`。即會顯示「歡迎使用 SAP 安裝」頁面。
2. 選取 **SAP NetWeaver 7.5** > **IBM Db2 for Linux, Unix, and Windows** > **SAP 系統** > **應用程式伺服器 ABAP**。
3. 開啟**分散式系統**，然後在資料庫伺服器上執行 **ASCS 實例**及**資料庫實例**。
4. 安裝「ASCS 實例」讓下一步運作之後，請驗證 `sapinst` 已順利共用資料夾 `\\sapmnt` 及 `\\user\sap\trans`。
5. 在應用程式伺服器上，執行**主要應用程式伺服器實例**。請務必在安裝應用程式伺服器期間使用 ASCS 及資料庫主機名稱的專用位址。這確保應用程式伺服器與 ASCS（或資料庫）路徑之間的網路資料流量（透過專用網路，而不是透過專用網路）。

您現在可以根據 SAP 安裝指示來執行 SAP 安裝。
