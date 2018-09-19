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

# 4. 3 層セットアップのためのネットワークの準備
{: #network}

3 層セットアップのインストールを計画している場合は、それに応じてネットワーク・セットアップを準備する必要があります。 サンプルのセットアップでは、192 GB のデータベース・サーバー (名前は `sdb192`) と、32 GB のアプリケーション・サーバー (名前は `e2e1270`) がデプロイされています。データベース・サーバーは ABAP SAP Central Services (ASCS) インスタンスもホストします。 プライベート・ネットワーク上の IP を hosts ファイルに追加しておくと今後のステップに役立ち、SAP 内部ネットワーク・トラフィックが確実に適切なネットワークを通過します。

デプロイ済みサーバーのネットワーク・セットアップは、Microsoft Windows の「ネットワーク接続」の下にあります。サンプル・セットアップでは、`10.17.139.35` は、「ネットワーク接続」-「プライベート・ネットワーク」-「チーミング」の下のデータベース・サーバーのプライベート IP であり、RFC 1597 の IP 範囲の 1 つです。 また、アプリケーション・サーバーの IP も確認し、両方の IP を `C:&#xa5;Windows&#xa5;System32&#xa5;drivers&#xa5;etc` の下の両方のサーバーの `hosts` ファイルに追加できます。

## 次のステップ

  * [{{site.data.keyword.baremetal_short}}への外部ストレージの追加](/docs/infrastructure/sap-netweaver-ms-qrg/ms-provisioning-external-storage-to-your-server.html)
  * [SAP アプリケーションおよびソフトウェアのインストール](/docs/infrastructure/sap-netweaver-ms-qrg/ms-installing-your-SAP-landscape.html)
