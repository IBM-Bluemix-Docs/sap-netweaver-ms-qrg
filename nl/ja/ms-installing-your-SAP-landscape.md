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

# SAP のインストールの状況
{: #install_landscape}

## SAP ソフトウェアのダウンロード
{: #download_software}

DVD のダウンロードには、SAP S-User ID とダウンロード許可が必要です。 SAP S-user ID について詳しくは、[S-user ID のセットアップ方法![外部リンクのアイコン](../icons/launch-glyph.svg "外部リンクのアイコン")](https://www.youtube.com/watch?v=4wICiRTP8u0/){: new_window}を参照してください。

1. [SAP Support Portal ![外部リンクのアイコン](../icons/launch-glyph.svg "外部リンクのアイコン")にログイン](https://support.sap.com/en/index.html){: new_window}し、**「Download Software」**をクリックして、必要な DVD をローカル共有ドライブにダウンロードします。
2. ファイルをプロビジョンされたサーバーに転送します。

もう 1 つのオプションは、[SAP Software Download Manager ![外部リンクのアイコン](../icons/launch-glyph.svg "外部リンクのアイコン")](https://support.sap.com/en/my-support/software-downloads.html#section_995042677){: new_window} をダウンロードし、それをターゲット・サーバーにインストールし、DVD イメージをサーバーに直接ダウンロードすることです。

## SAP ソフトウェアのインストール
{: #install_software}

インストール・メディアをダウンロードした後、使用する SAP バージョンおよびコンポーネント用の SAP インストール・ガイドに記載されている標準の SAP インストール手順と、対応する SAP ノートに従います。 詳しくは、[SAP Installation Guide (SAP インストール・ガイド)![外部リンクのアイコン](../icons/launch-glyph.svg "外部リンクのアイコン")](https://service.sap.com/instguides){: new_window} および [SAP Notes (SAP ノート) ![外部リンクのアイコン](../icons/launch-glyph.svg "外部リンクのアイコン")](https://support.sap.com){: new_window}を参照してください。両方とも SAP S-User ID が必要です。

1. 管理者として、SWPM-DVD またはインストール・マスター DVD のルート・フォルダーを開き、`sapinst` を実行します。 「SAP インストールへようこそ (Welcome to SAP Installation)」ページが表示されます。
2. **「SAP NetWeaver 7.5」** > **「IBM DB2 for Linux, Unix, and Windows」** > **「SAP システム (SAP Systems)」** > **「アプリケーション・サーバー ABAP (Application Server ABAP)」**を選択します。
3. **「分散システム (Distributed System)」**を開き、データベース・サーバーで**「ASCS インスタンス (ASCS Instance)」**および**「データベース・インスタンス (Database Instance)」**を実行します。
4. 次のステップを実行するために、ASCS インスタンスがインストールされた後に、`sapinst` がフォルダー `&#xa5;&#xa5;sapmnt` と `&#xa5;&#xa5;user&#xa5;sap&#xa5;trans` を正常に共有していることを確認します。
5. アプリケーション・サーバーで、**1 次側アプリケーション・サーバー・インスタンス**を実行します。 アプリケーション・サーバーのインストール時には、必ず ASCS のプライベート・アドレスとデータベース・ホスト名を使用してください。 これにより、アプリケーション・サーバーと ASCS またはデータベース間のネットワーク・トラフィックは、確実に、パブリック・ネットワーク経由ではなく、プライベート・ネットワーク経由でパスされます。

これで、SAP インストール手順に従って、SAP インストールを実行できるようになりました。
