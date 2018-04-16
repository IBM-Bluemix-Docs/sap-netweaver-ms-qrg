---



copyright:
  years: 2017
lastupdated: "2018-02-26"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. 32-GB-Server bestellen
{: #install_32GB}

## Server bestellen
{: #order_32GB}

1. Melden Sie sich mit Ihren eindeutigen Berechtigungsnachweisen beim [Kundenportal für die {{site.data.keyword.cloud_notm}}-Infrastruktur](https://control.softlayer.com) an.
2. Klicken Sie auf der Seite "Konto - Zusammenfassung" auf **Geräte**.
3. Klicken Sie auf der Seite "Geräte" unter "Bare-Metal-Server" auf **Monatlich**. Das Dialogfeld "Serverliste" wird angezeigt.
4. Klicken Sie auf den Hyperlink unter **AUSGANGSPREIS - MONATLICH**, um den Server **BI.S1.NW32 (Betriebssystemoptionen)** auszuwählen.

## Serveroptionen auswählen
{: #options_32GB}

1. Belassen Sie im Feld **Menge** den Wert **1**.
2. Wählen Sie als **Rechenzentrum** die Option **DAL10** aus. Welche Rechenzentren in der Liste aufgeführt werden, ist von der Produktverfügbarkeit der jeweiligen Rechenzentren abhängig.
3. Das Feld **Server** ist standardmäßig mit einem vordefinierten Wert belegt, der von Ihrer Serverauswahl abhängig ist und nicht geändert werden kann.
4. Klicken Sie auf **32 GB RAM**, selbst wenn die **RAM**-Auswahl standardmäßig mit einem vordefinierten Wert entsprechend Ihrer Serverauswahl belegt ist und nicht geändert werden kann.
5. Wählen Sie eine beliebige Version von Microsoft Windows als **Betriebssystem** aus.
6. Wählen Sie unter **Festplattenlaufwerke** eine zweite Platte desselben Typs wie die erste aus, erstellen Sie eine RAID-Speichergruppe "RAID1" von beiden Platten, die den Gesamtspeicher abdeckt, und wählen Sie **Windows - Basic** als **Partitionsvorlage** aus. Belassen Sie **LVM** inaktiviert.
7. Wählen Sie als **Öffentliche Bandbreite** den Wert **500 GB** aus.
8. Wählen Sie als **Uplink-Port-Geschwindigkeit** die Option **1 Gb/s Redundanz für Uplinks des öffentlichen und privaten Netzes** aus.
9. Belassen Sie für diese Beispielinstallation in allen übrigen Feldern die Standardwerte. Detaillierte Optionsbeschreibungen finden Sie unter [Bare-Metal-Server einrichten](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers).
10. Klicken Sie unten auf der Seite auf **Zur Bestellung hinzufügen**. Nachdem Ihre Bestellung verifiziert wurde, werden Sie zur Kassenseite weitergeleitet.

## Erweiterte Systemkonfigurationen einrichten
{: #adv_config}

Zur Belegung der Felder unter "Erweiterte Systemkonfiguration" verwenden Sie die Werte aus Tabelle 1. Weitere Informationen sind in der Anleitung für die [Erweiterte Systemkonfiguration](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration) verfügbar.

1. Blättern Sie abwärts und geben Sie unter **Erweiterte Systemkonfiguration** die Werte aus Tabelle 1 ein.

|              Feld                |      Wert                                                            |
| -------------------------------- | -------------------------------------------------------------------- |
|Back-End-VLAN                     | Wählen Sie aus der Dropdown-Liste beispielsweise `dal10.bcr01a.981`      |
|Teilnetz                          | Wählen Sie aus der Dropdown-Liste beispielsweise `10.177.119.192/26`     |
|Front-End-VLAN                    | Wählen Sie aus der Dropdown-Liste beispielsweise `dal10.fcr01a.926`      |
|Teilnetz                          | Wählen Sie aus der Dropdown-Liste beispielsweise `169.46.15.96/27`       |
|Bereitstellungs-Scripts           | Standardmäßig "Keine"                                                     |
|SSH-Schlüssel                     | Hinzufügen|
|Hostname                          | Beispiel: `e2e1270`                                               |
|Domäne                            | Beispiel: `saptest.com`                                           |
{: caption="Tabelle 1. Erweiterte Konfigurationswerte für 32 GB" caption-side="top"}  

## Auswahl bestätigen
{: #confirm_selections}

1. Bestätigen Sie Ihre Auswahl auf der Kassenseite und klicken Sie auf **Cloud-Servicebedingungen** und **Vereinbarung für Software anderer Anbieter** rechts auf der Seite.
2. Klicken Sie rechts im Formular auf **Bestellung abschicken**. Sie werden zu einer Seite mit Ihrer Bestellnummer weitergeleitet. Da dies auch Ihre Bestellbestätigung ist, können Sie die Seite ausdrucken. Zusätzlich erhalten Sie eine Bestätigungs-E-Mail mit dem Betreff *Ihre IBM Cloud-Bestellung Nr. ## wurde genehmigt*, wobei ## Ihre Bestellnummer ist.

Nach der Übermittlung der Bestellung ist der Server - entsprechend der Bestellung - für ein bis vier Stunden verfügbar. Den Status der Bereitstellungsschritte können Sie auf der Seite "Gerätedetails" der Hauptseite des Kundenportals (**Geräte** > **Geräteliste**) überprüfen. Klicken Sie auf den **Gerätenamen**, der mit Ihren Angaben für Hostname und Domäne übereinstimmt, sodass dessen Status angezeigt wird.

## Nächste Schritte

  [2. Server für die SAP-Installation vorbereiten](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-32GB.html)
  
  [3. Partitionierung und Dateisysteme](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-32GB.html)
