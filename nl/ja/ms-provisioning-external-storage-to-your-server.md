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

# サーバーへの外部ストレージの追加
{: #storage}

## 外部ストレージの構成
{: #set_up_storage}

外部ストレージをバックアップ・デバイスとして使用する場合や、スナップショットを使用してテスト環境でデータベースを迅速にリストアする場合は、プロビジョンされたサーバーに外部ストレージを追加できます。この例では、データベースのアーカイブ・ログ・ファイル、およびデータベースのオンライン/オフライン・バックアップの両方に、ブロック・ストレージが使用されています。バックアップ時間が確実に最小になるように、最速のブロック・ストレージ (1 GB あたり 4 IOPS) が選択されました。ブロック・ストレージの速度がこれより遅くても十分な場合もあります。{{site.data.keyword.blockstoragefull}}について詳しくは、[ブロック・ストレージの開始](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage)を参照してください。

1. [{{site.data.keyword.cloud_notm}} インフラストラクチャーのカスタマー・ポータル](https://control.softlayer.com/)にログインします。
2. **「ストレージ」** > **「ブロック・ストレージ」**を選択します。
3. 「ブロック・ストレージ」ページの右上隅の**「ブロック・ストレージの注文 (Order Block Storage)」**をクリックします。
4. ストレージのニーズに合わせて詳細を選択します。表 1 には、「一般的なデータベース・ワークロードに対しては 4 IOPS/GB」などの推奨値が含まれています。

|              フィールド               |      値                                        |
| -------------------------------- | ------------------------------------------------- |
|ストレージ・タイプの選択               | エンデュランス (デフォルト)                               |
|場所                          | DAL10                                             |
|請求方法                    | 毎月 (デフォルト)                                 |
|ストレージ・パッケージの選択            | 4 IOPS/GB                                         |
|ストレージ・サイズの選択               | 1000 GB                                           |
|スナップショット・スペース・サイズの指定       | 0 GB                                              |
|OS タイプの選択                    | Microsoft Windows                                 |
{: caption="表 1. ブロック・ストレージの推奨値" caption-side="top"}

## ホストの許可
{: authorize-hosts}

1. **「続行」**をクリックします。
2. **「マスター・サービス契約を読みました (I have read the Master Service Agreement)」**と**「注文の実行」**をクリックします。
3. LUN の右側にある**「アクション」**をクリックし、**「ホストの許可 (Authorize Host)」**を選択してプロビジョン済みのストレージにアクセスします。
4. **「デバイス」**を選択します。**「デバイス・タイプ (Device Type)」**は、デフォルトの「ベア・メタル・サーバー」に設定されます。**「ハードウェア」**をクリックし、データベース・サーバーのホスト名を選択します。
5. **「送信」**をクリックします。
6. **「デバイス」** > (デバイスを選択) > **「ストレージ」**タブで、プロビジョン済みのストレージのステータスを確認します。
7. サーバー (iSCSI イニシエーター) の**ターゲット・アドレス**と iSCSI 修飾名 (IQN)、および iSCSI サーバーで許可するための**ユーザー名**と**パスワード**を書き留めます。この情報は、ブロック・ストレージをデータベース・サーバーに接続するために使用されます。

サンプルのデプロイメントでは次のデータを「ストレージ」タブから取得しました。
   * ターゲット IP: `10.2.62.78`
   * IQN: `iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * ユーザー: `SL01SU276540-H896345`
   * パスワード: `EtJ79F4RA33dXm2q`

[Connecting to MPIO iSCSCI LUNS on Microsoft Windows (Microsoft Windows 上の MPIO iSCSCI LUNS への接続)](https://console.bluemix.net/docs/infrastructure/BlockStorage/accessing-block-storage-windows.html#connecting-to-mpio-iscsi-luns-on-microsoft-windows)の手順に従い、上記のデータを使用してブロック・ストレージをデータベース・サーバーに接続します。注意深く手順に従ってください。この手順により、新しい「オフライン」ディスクが Windows サーバーで使用可能になります。

これで、ディスクをオンラインにして初期化することができます。 
