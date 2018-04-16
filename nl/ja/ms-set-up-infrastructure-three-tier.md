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

# 1. 3 層セットアップ用の 256 GB サーバーおよび 32 GB サーバーの注文
{: #install_three_tier}

[32 GB サーバーの注文](/docs/infrastructure/sap-netweaver-ms-qrg/ms-set-up-infrastructure-32GB.html#order_32GB)のステップに従って、SAP NetWeaver アプリケーション・サーバーを注文します。次のステップでは、データベース・サーバーの注文について説明します。外部ストレージは、アーカイブされたログ・ファイルとオンラインのフルバックアップの両方について、データベースのバックアップ・スペースとして後のステップでプロビジョンされます。

## サーバーの注文
{: #order_servers}

1. ユーザー固有の資格情報を使用して、[{{site.data.keyword.cloud}} インフラストラクチャーのカスタマー・ポータル](https://control.softlayer.com)にログインします。
2. 「アカウント要約」ページで**「デバイス」**アイコンをクリックします。
3. 「デバイス」ページの**「{{site.data.keyword.baremetal_long}}」**の下の**「毎月」**をクリックします。「サーバー・リスト (Server List)」ダイアログ・ボックスが表示されます。
4. **「毎月の開始価格 (STARTING PRICE PER MONTH)」**の下のハイパーリンクをクリックして、サーバー**「BI.S1.NW256 (OS オプション)」**を選択します。

## サーバー・オプションの選択
{: #options_256GB}

1. **「数量」**フィールドは**「1」**のままにします。
2. **「データ・センター」**は**「DAL10」**を選択します。
3. **サーバー**は、サーバー選択に基づく事前定義のデフォルト値に設定されており、変更できません。
4. **「RAM」**の選択が、サーバー選択に基づく事前定義のデフォルト値に設定されていて変更できない場合であっても、**「32 GB RAM」**をクリックします。
5. **「オペレーティング・システム」**として、任意のバージョンの Microsoft Windows を選択します。
6. **「ハード・ディスク (Hard Drives)」**の下で、最初のディスクと同じタイプの 2 番目のディスクを選択し、両方のディスクから、ストレージの総量をカバーする RAID1 の RAID ストレージ・グループを作成し、**「パーティション・テンプレート (Partition Template)」**として**「Windows 基本」**を選択します。**「LVM」**はチェック・マークを外したままにします。
7. **「パブリック処理能力」**は**「500 GB」**を選択します。
8. **「アップリンク・ポート速度」**は**「1 Gbps 冗長パブリックおよびプライベート・ネットワーク・アップリンク (1 Gbps Redundant Public and Private Network Uplinks)」**を選択します。
9. このサンプル・インストールでは、他のすべてのフィールドはデフォルト値のままにします。詳しいオプションの説明は、[ベア・メタル・サーバーのセットアップ](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers)を参照してください。
10. ページの下部にある**「注文に追加 (Add to Order)」**をクリックします。注文が検証された後、「チェックアウト (Checkout)」ページにリダイレクトされます。

## 拡張システム構成のセットアップ
{: #adv_config}

1. 「拡張システム構成 (Advanced System Configuration)」の下のフィールドについては、表 1 の値を使用します。詳細情報が[拡張システム構成](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration)のガイドラインにあります。

|              フィールド               |      値                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|バックエンド VLAN                      | ドロップダウン・リストから選択。例えば、`dal10.bcr01a.981`      |
|サブネット                            | ドロップダウン・リストから選択。例えば、`10.177.119.192/26`     |
|フロントエンド VLAN                     | ドロップダウン・リストから選択。例えば、`dal10.fcr01a.926`      |
|サブネット                            | ドロップダウン・リストから選択。例えば、169.46.15.96/27         |
|プロビジョン・スクリプト                 | デフォルトの「なし」                                                     |
|SSH 鍵                          | 追加 (そのままにする。つまり、SSH 鍵なし)                                   |
|ユーザー・メタデータ                     | ブランクのまま                                                          |
|ホスト名 Server1                  | 例えば、`e2e2690`                                               |
|ドメイン Server1                    | 例えば、`saptest.com`                                           |
{: caption="表 1. 拡張システム構成の値" caption-side="top"}

## 選択内容の確認
{: #confirm_selections}

1. 「チェックアウト (Checkout)」ページで選択内容を確認し、ページの右側にある**「クラウド・サービスのご利用条件 (Cloud Service terms)」**と**「サード・パーティーのソフトウェアのご使用条件 (3rd Party Software Agreement)」**をクリックします。
2. **「注文の送信」**をクリックします。注文番号の画面にリダイレクトされます。この画面は、注文の受信を示すものでもあるため、印刷できます。

注文が送信された後、注文に応じて、サーバーは 1 時間から 4 時間以内で使用できます。プロビジョン・ステップのステータスについては、「カスタマー・ポータル」のメイン・ページの「デバイス詳細 (Device Details)」画面 (**「デバイス」** > **「デバイス・リスト」**) で確認できます。指定したホスト名とドメインに一致する**デバイス名**をクリックして、そのステータスを確認します。

## 次のステップ

  [2. SAP インストール用のサーバーの準備](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-256GB.html)
  
  [3. パーティショニングとファイル・システム](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-256GB.html)
  
  [4. ネットワークの準備](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-network.html#network)