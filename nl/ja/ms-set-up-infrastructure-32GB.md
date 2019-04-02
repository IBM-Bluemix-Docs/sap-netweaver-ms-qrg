---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, bring your own license, BYOL, VLAN

subcollection: sap-netweaver-ms-qrg

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. 32 GB サーバーの注文
{: #install_32GB}

## サーバーの注文
{: #order_32GB}

1. ユーザー固有の資格情報を使用して、[{{site.data.keyword.cloud_notm}} インフラストラクチャーのカスタマー・ポータル ![外部リンクのアイコン](../icons/launch-glyph.svg "外部リンクのアイコン")](https://control.softlayer.com){: new_window}にログインします。
2. 「アカウント要約」ページで**「アカウント」** > **「注文の実行」**をクリックします。
3. 「デバイス」ページの{{site.data.keyword.baremetal_short}}の下の**「毎月」**をクリックします。 サーバー・リストが表示されます。SAP 認定サーバーは、リストの一番上にあります。
4. **「毎月の開始価格 (STARTING PRICE PER MONTH)」**の下のハイパーリンクをクリックして、サーバー**「BI.S3.NW32 (OS オプション)」**を選択します。

BI.S3.NW32 (OS オプション) サーバーも**「毎時」**の請求で利用できます。
{: note}

## サーバーの構成
{: #configure_server}

1. **「数量」**フィールドは**「1」**のままにします。
2. **「データ・センター」**は**「DAL10」**を選択します。 データ・センターのリストは、特定のデータ・センター内の製品の可用性によって異なります。
3. **サーバー**は、サーバー選択に基づく事前定義のデフォルト値に設定されており、変更できません。
4. **「RAM」**の選択が、サーバー選択に基づく事前定義のデフォルト値に設定されていて変更できない場合であっても、**「32 GB RAM」**をクリックします。
5. **「オペレーティング・システム」**として、任意のバージョンの Microsoft Windows を選択します。 **注**: 使用しているオペレーティング・システムの独自のライセンス (BYOL) がある場合は、**「その他」** > **「オペレーティング・システムなし (No Operating System)」**を選択します。 詳しくは、[独自ライセンスの使用](#byol)を参照してください。
6. **「ディスク・コントローラー 1 (Disk Controller 1)」**がデフォルトの**「2 TB SATA」**に設定されていることを確認して、2 つ目の 2 TB SATA ドライブを追加します。 **「ディスクの追加 (Add Disk)」**をクリックします。
7. **「すべてのディスクを選択 (Select All Disks)」**をクリックし、**「RAID ストレージ・グループの作成 (Create RAID storage group)」**をクリックします。
8. **「タイプ」**をクリックし、**「RAID 1」**を選択します。**「サイズ」**に、必要なストレージの総量をカバーするサイズを入力します。
9. **「LVM」**はチェック・マークを外したままにし、**「パーティション・テンプレート (Partition Template)」**はデフォルトの**「Windows Basic」**を受け入れます。
10. **「完了」**をクリックします。

## 追加のサーバー・オプションの選択
{: #options_32GB

1. **「パブリック処理能力」**は**「500 GB」**を選択します。
2. **「アップリンク・ポート速度」**は**「1 Gbps 冗長パブリックおよびプライベート・ネットワーク・アップリンク (1 Gbps Redundant Public and Private Network Uplinks)」**を選択します。
3. 他のすべてのフィールドはデフォルト値のままにします。 詳しいオプションの説明は、[カスタム・ベアメタル・サーバーの作成](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server)を参照してください。
10. ページの下部にある**「注文に追加 (Add to Order)」**をクリックします。 注文が検証された後、「チェックアウト (Checkout)」ページにリダイレクトされます。

## 拡張システム構成のセットアップ
{: #adv_config}

「拡張システム構成 (Advanced System Configuration)」の下のフィールドについては、表 1 の値を使用します。 詳細情報が[拡張サーバー構成オプション (Advanced server configuration options)](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server)のガイドラインにあります。

1. スクロールダウンして、表 1 の**「拡張システム構成 (Advanced System Configuration)」**の下の値を入力します。

|              フィールド               |      値                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|バックエンド VLAN                      | ドロップダウン・リストから選択。例えば、`dal10.bcr01a.981`      |
|サブネット                            | ドロップダウン・リストから選択。例えば、`10.177.119.192/26`     |
|フロントエンド VLAN                     | ドロップダウン・リストから選択。例えば、`dal10.fcr01a.926`      |
|サブネット                            | ドロップダウン・リストから選択。例えば、`169.46.15.96/27`       |
|プロビジョン・スクリプト                 | ブランクのまま                                                          |
|SSH 鍵                          | デフォルトは `Add` で、SSH 鍵がないことを意味する                            |
|ホスト名                          | 例えば、`e2e1270`                                               |
|ドメイン                            | 例えば、`saptest.com`                                           |
{: caption="表 1. 32 GB 拡張構成の値" caption-side="top"}  

## 選択内容の確認
{: #confirm_selections}

1. 「チェックアウト (Checkout)」ページで選択内容を確認し、ページの右側にある**「クラウド・サービスのご利用条件 (Cloud Service terms)」**と**「サード・パーティーのソフトウェアのご使用条件 (3rd Party Software Agreement)」**をクリックします。
2. フォームの右側にある**「注文の送信 (Submit Order)」**をクリックします。 注文番号のページにリダイレクトされます。 このページは、注文の受信を示すものでもあるため、印刷できます。 さらに、件名が「*お客様の IBM Cloud 注文 ## は承認されました*」(## は注文番号) という確認の E メールを受け取ります。

注文が送信された後、注文に応じて、サーバーは 1 時間から 4 時間以内で使用できます。 プロビジョン・ステップのステータスについては、「カスタマー・ポータル」のメイン・ページの「デバイス詳細 (Device Details)」画面 (**「デバイス」** > **「デバイス・リスト」**) で確認できます。 指定したホスト名とドメインに一致する**デバイス名**をクリックして、そのステータスを確認します。

## 独自ライセンスの使用
{: #byol}

独自のオペレーティング・システム・ライセンスを持っている場合は、ベンダーの指示に基づいて、そのライセンスを {{site.data.keyword.baremetal_short}} にインストールします。 詳しくは、[「オペレーティング・システムなし」オプション](/docs/bare-metal?topic=bare-metal-the-no-os-option)を参照してください。

## 次のステップ

  [2. SAP インストール用のサーバーの準備](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-2-preparing-your-server-for-your-sap-installation-32-gb-)

  [3. パーティショニングとファイル・システム](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-partition_32GB)
