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

# 1. 256-GB- und 32-GB-Server für ein dreischichtiges Setup bestellen
{: #install_three_tier}

Befolgen Sie die Schritte unter [32-GB-Server bestellen](/docs/infrastructure/sap-netweaver-ms-qrg/ms-set-up-infrastructure-32GB.html#order_32GB), um SAP NetWeaver Application Server zu bestellen. Die folgenden Schritte führen Sie durch die Bestellung des Datenbankservers. Externer Speicher als Backup-Bereich der Datenbank sowohl für archivierte Protokolldateien als auch für Online-Gesamtbackups wird in einem späteren Schritt bereitgestellt.

## Server bestellen
{: #order_servers}

1. Melden Sie sich mit Ihren eindeutigen Berechtigungsnachweisen beim [Kundenportal für die {{site.data.keyword.cloud}}-Infrastruktur](https://control.softlayer.com) an.
2. Klicken Sie auf der Seite "Konto - Zusammenfassung" auf das Symbol **Geräte**.
3. Klicken Sie auf der Seite "Geräte" unter **{{site.data.keyword.baremetal_long}}** auf **Monatlich**. Das Dialogfeld "Serverliste" wird angezeigt.
4. Klicken Sie auf den Hyperlink unter **AUSGANGSPREIS - MONATLICH**, um den Server **BI.S1.NW256 (Betriebssystemoptionen)** auszuwählen.

## Serveroptionen auswählen
{: #options_256GB}

1. Belassen Sie im Feld **Menge** den Wert **1**.
2. Wählen Sie als **Rechenzentrum** die Option **DAL10** aus. 
3. Das Feld **Server** ist standardmäßig mit einem vordefinierten Wert belegt, der von Ihrer Serverauswahl abhängig ist und nicht geändert werden kann.
4. Klicken Sie auf **32 GB RAM**, selbst wenn die **RAM**-Auswahl standardmäßig mit einem vordefinierten Wert entsprechend Ihrer Serverauswahl belegt ist und nicht geändert werden kann.
5. Wählen Sie eine beliebige Version von Microsoft Windows als **Betriebssystem** aus.
6. Wählen Sie unter **Festplattenlaufwerke** eine zweite Platte desselben Typs wie die erste aus, erstellen Sie eine RAID-Speichergruppe "RAID1" von beiden Platten, die den Gesamtspeicher abdeckt, und wählen Sie **Windows - Basic** als **Partitionsvorlage** aus. Belassen Sie **LVM** inaktiviert.
7. Wählen Sie als **Öffentliche Bandbreite** den Wert **500 GB** aus.
8. Wählen Sie **1 Gb/s Redundanz für Uplinks des öffentlichen und privaten Netzes** und **Uplink-Port-Geschwindigkeit** aus.
9. Belassen Sie für diese Beispielinstallation in allen übrigen Feldern die Standardwerte. Detaillierte Beschreibungen der Optionen finden Sie unter [Bare-Metal-Server einrichten](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers).
10. Klicken Sie unten auf der Seite auf **Zur Bestellung hinzufügen**. Nachdem Ihre Bestellung verifiziert wurde, werden Sie zur Kassenseite weitergeleitet.

## Erweiterte Systemkonfigurationen einrichten
{: #adv_config}

1. Zur Belegung der Felder unter "Erweiterte Systemkonfiguration" verwenden Sie die Werte aus Tabelle 1. Weitere Informationen sind in der Anleitung für die [Erweiterte Systemkonfiguration](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration) verfügbar.

|              Feld                |      Wert                                                            |
| -------------------------------- | -------------------------------------------------------------------- |
|Back-End-VLAN                     | Wählen Sie aus der Dropdown-Liste beispielsweise `dal10.bcr01a.981`      |
|Teilnetz                          | Wählen Sie aus der Dropdown-Liste beispielsweise `10.177.119.192/26`     |
|Front-End-VLAN                    | Wählen Sie aus der Dropdown-Liste beispielsweise `dal10.fcr01a.926`      |
|Teilnetz                          | Wählen Sie aus der Dropdown-Liste beispielsweise "169.46.15.96/27"         |
|Bereitstellungs-Scripts           | Standardmäßig "Keine"                                                     |
|SSH-Schlüssel                     | Hinzufügen (Wert belassen = kein SSH-Schlüssel)                                   |
|Benutzermetadaten                 | Leer lassen                                                          |
|Hostname Server1                  | Beispiel: `e2e2690`                                               |
|Domäne Server1                    | Beispiel: `saptest.com`                                           |
{: caption="Tabelle 1. Werte für erweiterte Systemkonfiguration" caption-side="top"}

## Auswahl bestätigen
{: #confirm_selections}

1. Bestätigen Sie Ihre Auswahl auf der Kassenseite und klicken Sie auf **Cloud-Servicebedingungen** und **Vereinbarung für Software anderer Anbieter** rechts auf der Seite.
2. Klicken Sie auf **Bestellung abschicken**. Sie werden zu einem Bildschirm mit Ihrer Bestellnummer weitergeleitet. Da dies auch Ihre Bestellbestätigung ist, können Sie den Bildschirm ausdrucken.

Nach der Übermittlung der Bestellung ist der Server - entsprechend der Bestellung - für ein bis vier Stunden verfügbar. Den Status der Bereitstellungsschritte können Sie auf der Seite "Gerätedetails" der Hauptseite des Kundenportals (**Geräte** > **Geräteliste**) überprüfen. Klicken Sie auf den **Gerätenamen**, der mit Ihren Angaben für Hostname und Domäne übereinstimmt, sodass dessen Status angezeigt wird.

## Nächste Schritte

  [2. Server für die SAP-Installation vorbereiten](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-256GB.html)
  
  [3. Partitionierung und Dateisysteme](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-256GB.html)
  
  [4. Netz vorbereiten](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-network.html#network)
