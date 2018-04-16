---



copyright:
  years: 2017, 2018
lastupdated: "2018-02-26"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 將外部儲存空間新增至伺服器
{: #storage}

## 配置外部儲存空間
{: #set_up_storage}

如果您要使用外部儲存空間作為備份裝置，或在測試環境中使用 Snapshot 快速還原資料庫，則可以將外部儲存空間新增至一個以上已佈建的伺服器。在範例中，使用區塊儲存空間來保存資料庫的日誌檔以及資料庫的線上和離線備份。已選取最快速的區塊儲存空間（每 GB 4 IOPS），協助確保最短備份時間。較慢的區塊儲存空間可能就符合您的需求。如需 {{site.data.keyword.blockstoragefull}} 的相關資訊，請參閱[開始使用區塊儲存空間](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage)。

1. 登入 [{{site.data.keyword.cloud_notm}} 基礎架構客戶入口網站](https://control.softlayer.com/)。
2. 選取**儲存空間** > **區塊儲存空間**。
3. 按一下「區塊儲存空間」頁面右上角的**訂購區塊儲存空間**。
4. 選取您儲存空間需求的特性。表 1 包含建議值（包括 4 IOPS/GB 作為一般資料庫工作負載）。

|              欄位                |      值                                           |
| -------------------------------- | ------------------------------------------------- |
|選取儲存空間類型                  | 耐久性（預設值）                                  |
|位置                              | DAL10                                             |
|計費方法                          | 每月（預設值）                                    |
|選取儲存空間套件                  | 4 IOPS/GB                                         |
|選取儲存空間大小                  | 1000 GB                                           |
|指定 Snapshot 空間大小            | 0 GB                                              |
|選取 OS 類型                      | Microsoft Windows                                 |
{: caption="表 1. 區塊儲存空間的建議值" caption-side="top"}

## 授權主機
{: authorize-hosts}

1. 按一下**繼續**。
2. 按一下**我已閱讀主要服務合約**及**下單**。
3. 按一下 LUN 右側的**動作**，然後選取**授權主機**來存取已佈建的儲存空間。
4. 選取**裝置**；**裝置類型**預設為「裸機伺服器」。按一下**硬體**，然後選取您資料庫伺服器的主機名稱。
5. 按一下**提交**。
6. 在**裝置** >（選取裝置）> **儲存空間**標籤下，檢查已佈建儲存空間的狀態。
7. 記下伺服器（iSCSI 起始器）的**目標位址**及「iSCSI 完整名稱 (IQN)」，以及向 iSCSI 伺服器進行授權的**使用者名稱**及**密碼**。該資訊用來將區塊儲存空間連接至資料庫伺服器。

在範例部署中，擷取自「儲存空間」標籤的資料是：
   * 目標 IP：`10.2.62.78`
   * IQN：`iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * 使用者：`SL01SU276540-H896345`
   * 密碼：`EtJ79F4RA33dXm2q`

遵循[在 Microsoft Windows 上連接至 MPIO iSCSCI LUNS](https://console.bluemix.net/docs/infrastructure/BlockStorage/accessing-block-storage-windows.html#connecting-to-mpio-iscsi-luns-on-microsoft-windows) 中的步驟，以使用上面的資料將區塊儲存空間連接至資料庫伺服器。請仔細地遵循步驟；它們會導致可用於 Windows 伺服器的新「離線」磁碟。

您現在可以讓磁碟上線，並進行起始設定。 
