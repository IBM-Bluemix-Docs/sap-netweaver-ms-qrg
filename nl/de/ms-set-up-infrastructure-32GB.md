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

# 1. 32-GB-Server bestellen
{: #install_32GB}

## Server bestellen
{: #order_32GB}

1. Melden Sie sich beim [Kundenportal der {{site.data.keyword.cloud_notm}}-Infrastruktur ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com){: new_window} mit den eindeutigen Berechtigungsnachweisen an. 
2. Klicken Sie auf **Konto** > **Bestellen** auf der Kontozusammenfassungsseite.
3. Klicken Sie auf der Seite "Geräte" unter {{site.data.keyword.baremetal_short}} auf **Monatlich**. Die Liste der Server wird angezeigt; die von SAP zertifizierten Server stehen am Listenanfang.
4. Klicken Sie auf den Hyperlink unter **Startpreis pro Monat**, um den Server **BI.S3.NW32 (Betriebssystemoptionen)** auszuwählen.

Der BI.S3.NW32-Server (Betriebssystemoptionen) ist ebenfalls für die Abrechnung auf **Stundenbasis** verfügbar.
{: note}

## Server konfigurieren
{: #configure_server}

1. Belassen Sie im Feld **Menge** den Wert **1**.
2. Wählen Sie als **Rechenzentrum** die Option **DAL10** aus. Welche Rechenzentren in der Liste aufgeführt werden, ist von der Produktverfügbarkeit der jeweiligen Rechenzentren abhängig.
3. Das Feld **Server** ist standardmäßig mit einem vordefinierten Wert belegt, der von Ihrer Serverauswahl abhängig ist und nicht geändert werden kann.
4. Klicken Sie auf **32 GB RAM**, selbst wenn die **RAM**-Auswahl standardmäßig mit einem vordefinierten Wert entsprechend Ihrer Serverauswahl belegt ist und nicht geändert werden kann.
5. Wählen Sie eine beliebige Version von Microsoft Windows als **Betriebssystem** aus. **Hinweis**: Wenn Sie eine eigene Lizenz für Ihr Betriebssystem verwenden (BYOL, Bring Your Own License), wählen Sie **Sonstige** > **Kein Betriebssystem** aus. Weitere Informationen finden Sie in [BYOL (Bring Your Own License)](#byol).
6. Fügen Sie ein zweites SATA-Laufwerk mit 2 TB hinzu, indem Sie sicherstellen, dass die Angabe für **Plattencontroller 1** standardmäßig **SATA (2 TB)** lautet. Klicken Sie auf **Platte hinzufügen**.
7. Klicken Sie auf **Alle Platten auswählen** und dann auf **RAID-Speichergruppe erstellen**.
8. Klicken Sie auf **Typ** und wählen Sie **RAID 1** aus. Geben Sie einen Wert für die **Größe** ein, der die gesamte benötigte Speichermenge abdeckt.
9. Wählen Sie **LVM** nicht aus und akzeptieren Sie den Standardwert für die **Partitionsvorlage**: **Windows (Basis)**.
10. Klicken Sie auf **Fertig**.

## Zusätzliche Serveroptionen auswählen
{: #options_32GB

1. Wählen Sie als **Öffentliche Bandbreite** den Wert **500 GB** aus.
2. Wählen Sie als **Uplink-Port-Geschwindigkeit** die Option **1 Gb/s Redundanz für Uplinks des öffentlichen und privaten Netzes** aus.
3. Belassen Sie die Standardwerte für alle anderen Felder. Detaillierte Beschreibungen der Optionen finden Sie in [Angepassten Bare-Metal-Server erstellen](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server).
10. Klicken Sie unten auf der Seite auf **Zur Bestellung hinzufügen**. Nachdem Ihre Bestellung verifiziert wurde, werden Sie zur Kassenseite weitergeleitet.

## Erweiterte Systemkonfigurationen einrichten
{: #adv_config}

Zur Belegung der Felder unter "Erweiterte Systemkonfiguration" verwenden Sie die Werte aus Tabelle 1. Weitere Informationen finden Sie in den Richtlinien zu [erweiterten Serverkonfigurationsoptionen](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server).

1. Blättern Sie abwärts und geben Sie unter **Erweiterte Systemkonfiguration** die Werte aus Tabelle 1 ein.

|              Feld               |      Wert                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|Back-End-VLAN                      | Auswahl in Dropdown-Liste, z. B. `dal10.bcr01a.981`      |
|Teilnetz                            | Auswahl in Dropdown-Liste, z. B. `10.177.119.192/26`     |
|Front-End-VLAN                     | Auswahl in Dropdown-Liste, z. B. `dal10.fcr01a.926`      |
|Teilnetz                            | Auswahl in Dropdown-Liste, z. B. `169.46.15.96/27`       |
|Bereitstellungsscripts            | Keine Angabe machen                                                          |
|SSH-Schlüssel                          | Standardwert `Add`, d. h. kein SSH-Schlüssel        |
|Hostname                          | Beispiel: `e2e1270`                                               |
|Domäne                            | Beispiel: `saptest.com`                                           |
{: caption="Tabelle 1. Erweiterte Konfigurationswerte für 32 GB" caption-side="top"}  

## Auswahl bestätigen
{: #confirm_selections}

1. Bestätigen Sie Ihre Auswahl auf der Kassenseite und klicken Sie auf **Cloud-Servicebedingungen** und **Vereinbarung für Software anderer Anbieter** rechts auf der Seite.
2. Klicken Sie rechts im Formular auf **Bestellung abschicken**. Sie werden zu einer Seite mit Ihrer Bestellnummer weitergeleitet. Da dies auch Ihre Bestellbestätigung ist, können Sie die Seite ausdrucken. Zusätzlich erhalten Sie eine Bestätigungs-E-Mail mit dem Betreff *Ihre IBM Cloud-Bestellung Nr. ## wurde genehmigt*, wobei ## Ihre Bestellnummer ist.

Nach der Übermittlung der Bestellung ist der Server - entsprechend der Bestellung - für ein bis vier Stunden verfügbar. Den Status der Bereitstellungsschritte können Sie auf der Seite "Gerätedetails" der Hauptseite des Kundenportals (**Geräte** > **Geräteliste**) überprüfen. Klicken Sie auf den **Gerätenamen**, der mit Ihren Angaben für Hostname und Domäne übereinstimmt, sodass dessen Status angezeigt wird.

## BYOL (Bring Your Own License)
{: #byol}

Wenn Sie über eine eigene Betriebssystemlizenz verfügen, installieren Sie sie auf dem {{site.data.keyword.baremetal_short}} anhand der Herstelleranweisungen. Weitere Informationen finden Sie in [Option 'Kein Betriebssystem'](/docs/bare-metal?topic=bare-metal-bm-no-os#bm-no-os).

## Nächste Schritte

  [2. Server für die SAP-Installation vorbereiten](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-2-preparing-your-server-for-your-sap-installation-32-gb-)

  [3. Partitionierung und Dateisysteme](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-partition_32GB)
