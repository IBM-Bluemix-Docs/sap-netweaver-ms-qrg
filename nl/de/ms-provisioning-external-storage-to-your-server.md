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

# Externen Speicher zum Server hinzufügen
{: #storage}

## Externen Speicher konfigurieren
{: #set_up_storage}

Sie können Ihrem/Ihren bereitgestellten Server(n) externen Speicher hinzufügen, wenn Sie ihn/sie als Backup-Einheit verwenden oder Ihre Datenbank mit einem Snapshot in einer Testumgebung schnell wiederherstellen möchten. Im Beispiel wird ein Blockspeicher sowohl zur Archivierung der Protokolldateien der Datenbank als auch für Online- und Offline-Backups für die Datenbank verwendet. Um eine minimale Sicherungszeit zu gewährleisten, wurde der schnellste Blockspeicher (4 E/A-Operationen pro Sekunde pro GB) ausgewählt. Für Ihren Bedarf könnte ein langsamerer Blockspeicher ausreichen. Weitere Informationen über {{site.data.keyword.blockstoragefull}} finden Sie unter [Einführung in Blockspeicher](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage).

1. Melden Sie sich beim [Kundenportal für die {{site.data.keyword.cloud_notm}}-Infrastruktur](https://control.softlayer.com/) an.
2. Wählen Sie **Speicher** > **Blockspeicher** aus.
3. Klicken Sie in der rechten oberen Ecke der Seite "Blockspeicher" auf **Blockspeicher bestellen**.
4. Wählen Sie die Spezifikationen für Ihren Speicherbedarf aus. Tabelle 1 enthält die empfohlenen Werte, einschließlich 4 E/A-Operationen pro Sekunde pro GB für eine typische Datenbank-Workload.

|              Feld                |      Wert                                         |
| -------------------------------- | ------------------------------------------------- |
|Speichertyp wählen                | Endurance (Standard)                              |
|Position                          | DAL10                                             |
|Abrechnungsmethode                | Monatlich (Standard)                              |
|Speicherpaket auswählen           | 4 E/A-Operationen pro Sekunde/GB                  |
|Speichergröße auswählen           | 1000 GB                                           |
|Speicherbereichsgröße für Snapshots angeben       | 0 GB                              |
|Betriebssystemtyp auswählen       | Microsoft Windows                                 |
{: caption="Tabelle 1. Empfohlene Werte für den Blockspeicher" caption-side="top"}

## Hosts autorisieren
{: authorize-hosts}

1. Klicken Sie auf **Weiter**.
2. Klicken Sie auf **Ich habe die Rahmenvereinbarung gelesen** und auf **Bestellen**.
3. Klicken Sie rechts von Ihrer LUN auf **Aktionen** und wählen Sie **Host autorisieren** aus, um auf den bereitgestellten Speicher zugreifen zu können.
4. Wählen Sie **Geräte** aus; der **Gerätetyp** ist standardmäßig auf "Bare-Metal-Server" eingestellt. Klicken Sie auf **Hardware** und wählen Sie die Hostnamen Ihres Datenbankservers aus.
5. Klicken Sie auf **Abschicken**.
6. Überprüfen Sie den Status Ihres bereitgestellten Speichers unter **Geräte** > (Gerät auswählen) > Registerkarte **Speicher**.
7. Vermerken Sie die **Zieladresse** und den qualifizierten iSCSI-Namen (IQN) für Ihren Server (iSCSI-Initiator) sowie **Benutzername** und **Kennwort** zur Autorisierung beim iSCSI-Server. Diese Informationen werden zur Herstellung der Verbindung zwischen dem Blockspeicher und dem Datenbankserver verwendet.

In der Beispielbereitstellung wurden folgende Daten aus der Registerkarte "Speicher" entnommen:
   * Ziel-IP: `10.2.62.78`
   * IQN: `iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * Benutzer: `SL01SU276540-H896345`
   * Kennwort: `EtJ79F4RA33dXm2q`

Befolgen Sie die Schritte in [Verbindung zu MPIO-iSCSCI-LUNs unter Microsoft Windows herstellen](https://console.bluemix.net/docs/infrastructure/BlockStorage/accessing-block-storage-windows.html#connecting-to-mpio-iscsi-luns-on-microsoft-windows), um Ihren Blockspeicher unter Verwendung der obigen Daten mit Ihrem Datenbankserver zu verbinden. Befolgen Sie die Schritte sorgfältig, sie führen zu einer neuen "Offline-"Platte, die für Ihren Windows-Server verfügbar ist.

Sie können die Platte jetzt online stellen und initialisieren. 
