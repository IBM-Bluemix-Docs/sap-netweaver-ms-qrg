---



copyright:
  years: 2017, 2018
lastupdated: "2018-08-13"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. 3 層セットアップ用の 192 GB サーバーおよび 32 GB サーバーの注文
{: #install_three_tier}

[32 GB サーバーの注文](/docs/infrastructure/sap-netweaver-ms-qrg/ms-set-up-infrastructure-32GB.html#order_32GB)のステップに従って、SAP NetWeaver アプリケーション・サーバーを注文します。 次のステップでは、データベース・サーバーの注文について説明します。 外部ストレージは、アーカイブされたログ・ファイルとオンラインのフルバックアップの両方について、データベースのバックアップ・スペースとして後のステップでプロビジョンされます。

## データベース・サーバーの注文
{: #order_db_servers}

1. ユーザー固有の資格情報を使用して、[{{site.data.keyword.cloud}} インフラストラクチャーのカスタマー・ポータル](https://control.softlayer.com)にログインします。
2. 「アカウント要約」ページで**「アカウント」** > **「注文の実行」**をクリックします。
3. 「デバイス」ページの**「{{site.data.keyword.baremetal_long}}」**の下の**「毎月」**をクリックします。 「サーバー・リスト (Server List)」ダイアログ・ボックスが表示されます。
4. SAP 認定サーバーは、リストの一番上にあります。**「毎月の開始価格 (STARTING PRICE PER MONTH)」**の下のハイパーリンクをクリックして、サーバー**「BI.S3.NW192 (OS オプション)」**を選択します。

## データベース・サーバーの構成
{: #configure_server}

1. **「数量」**フィールドは**「1」**のままにします。
2. **「データ・センター」**は**「DAL10」**を選択します。 データ・センターのリストは、特定のデータ・センター内の製品の可用性によって異なります。
3. **サーバー**は、サーバー選択に基づく事前定義のデフォルト値に設定されており、変更できません。
4. **「RAM」**の選択が、サーバー選択に基づく事前定義のデフォルト値に設定されていて変更できない場合であっても、**「192 GB RAM」**をクリックします。
5. **「オペレーティング・システム」**として、任意のバージョンの Microsoft Windows を選択します。**注**: 使用しているオペレーティング・システムの独自のライセンス (BYOL) がある場合は、**「その他」** > **「オペレーティング・システムなし (No Operating System)」**を選択します。詳しくは、[独自ライセンスの使用](#byol)を参照してください。
6. **「ディスク・コントローラー 1 (Disk Controller 1)」**がデフォルトの**「2 TB SATA」**に設定されていることを確認して、2 つ目の 2 TB SATA ドライブを追加します。**「ディスクの追加 (Add Disk)」**をクリックします。
7. **「すべてのディスクを選択 (Select All Disks)」**をクリックし、**「RAID ストレージ・グループの作成 (Create RAID storage group)」**をクリックします。
8. **「タイプ」**をクリックし、**「RAID 1」**を選択します。**「サイズ」**に、必要なストレージの総量をカバーするサイズを入力します。
9. **「LVM」**はチェック・マークを外したままにし、**「パーティション・テンプレート (Partition Template)」**はデフォルトの**「Windows Basic」**を受け入れます。
10. **「完了」**をクリックします。

##追加のサーバー・オプションの選択
{: #options_256GB}

1. **「パブリック処理能力」**は**「500 GB」**を選択します。
2. **「アップリンク・ポート速度」**は**「1 Gbps 冗長パブリックおよびプライベート・ネットワーク・アップリンク (1 Gbps Redundant Public and Private Network Uplinks)」**を選択します。
3. 他のすべてのフィールドはデフォルト値のままにします。詳しいオプションの説明は、[カスタム・ベアメタル・サーバーの作成](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html#addl-server-options)を参照してください。
10. ページの下部にある**「注文に追加 (Add to Order)」**をクリックします。 注文が検証された後、「チェックアウト (Checkout)」ページにリダイレクトされます。

## 拡張システム構成のセットアップ
{: #adv_config}

「拡張システム構成 (Advanced System Configuration)」の下のフィールドについては、表 1 の値を使用します。 詳細情報が[拡張サーバー構成オプション (Advanced server configuration options)](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html#adv-system-config)のガイドラインにあります。

|            フィールド            |        値                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|バックエンド VLAN                      | ドロップダウン・リストから選択。例えば、`dal10.bcr01a.981`      |
|サブネット                            | ドロップダウン・リストから選択。例えば、`10.177.119.192/26`     |
|フロントエンド VLAN                     | ドロップダウン・リストから選択。例えば、`dal10.fcr01a.926`      |
|サブネット                            |ドロップダウン・リストから選択。例えば、169.46.15.96/27         |
|プロビジョン・スクリプト                 | ブランクのまま。                                                         |
|SSH 鍵                          | デフォルトは `Add` で、これは SSH 鍵がないことを意味する                           |
|ユーザー・メタデータ                     |ブランクのまま                                                          |
|ホスト名 Server1                  | 例えば、`sdb192`                                                |
|ドメイン Server1                    | 例えば、`saptest.com`                                           |
{: caption="表 1. 拡張システム構成の値" caption-side="top"}

## 選択内容の確認
{: #confirm_selections}

1. 「チェックアウト (Checkout)」ページで選択内容を確認し、ページの右側にある**「クラウド・サービスのご利用条件 (Cloud Service terms)」**と**「サード・パーティーのソフトウェアのご使用条件 (3rd Party Software Agreement)」**をクリックします。
2. **「注文の送信」**をクリックします。 注文番号の画面にリダイレクトされます。 この画面は、注文の受信を示すものでもあるため、印刷できます。

注文が送信された後、注文に応じて、サーバーは 1 時間から 4 時間以内で使用できます。 プロビジョン・ステップのステータスについては、「カスタマー・ポータル」のメイン・ページの「デバイス詳細 (Device Details)」画面 (**「デバイス」** > **「デバイス・リスト」**) で確認できます。 指定したホスト名とドメインに一致する**デバイス名**をクリックして、そのステータスを確認します。

## 独自ライセンスの使用
{: #byol}

独自のオペレーティング・システム・ライセンスを持っている場合は、ベンダーの指示に基づいて、そのライセンスを {{site.data.keyword.baremetal_short}} にインストールします。詳しくは、[「オペレーティング・システムなし」オプション](https://console.bluemix.net/docs/bare-metal/introduction-no-os.html#how-to-install-an-operating-system-on-a-no-os-server-)を参照してください。

## 次のステップ

  [2. SAP インストール用のサーバーの準備](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-256GB.html)
  
  [3. パーティショニングとファイル・システム](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-256GB.html)
  
  [4. ネットワークの準備](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-network.html#network)
