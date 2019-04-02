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

# SAP-Umgebung installieren
{: #install_landscape}

## SAP-Software herunterladen
{: #download_software}

Zum Herunterladen der DVDs benötigen Sie eine SAP S-Benutzer-ID sowie eine Downloadberechtigung. Weitere Informationen zur SAP S-Benutzer-ID finden Sie in [Vorgehensweise zum Einrichten einer S-Benutzer-ID ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://www.youtube.com/watch?v=4wICiRTP8u0/){: new_window}.

1. Melden Sie sich beim [SAP Support Portal ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://support.sap.com/en/index.html){: new_window} an, klicken Sie auf **Software herunterladen** und laden Sie die erforderlichen DVDs in ein lokales, gemeinsam genutztes Laufwerk herunter.
2. Übertragen Sie die Dateien auf Ihren bereitgestellten Server.

Eine andere Option besteht darin, den [Download-Manager für die SAP-Software ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://support.sap.com/en/my-support/software-downloads.html#section_995042677){: new_window} herunterzuladen, auf dem Zielserver zu installieren und die DVD-Images direkt auf den Server herunterzuladen. 

## SAP-Software installieren
{: #install_software}

Nach dem Herunterladen der Installationsmedien folgen Sie der Standardprozedur für die SAP-Installation, die im SAP-Installationshandbuch für Ihre SAP-Version und die Komponenten sowie in den SAP-Hinweisen dokumentiert ist. Weitere Informationen finden Sie in den Veröffentlichungen [SAP-Installationshandbuch ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://service.sap.com/instguides){: new_window} und [SAP-Hinweise ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://support.sap.com){: new_window}. Für beides ist eine SAP S-Benutzer-ID erforderlich.

1. Öffnen Sie den Stammordner Ihrer SWPM-DVD oder Ihrer Installations-Master-DVD als Administrator und führen Sie den Befehl `sapinst` aus. Die Willkommensseite für die SAP-Installation wird angezeigt.
2. Wählen Sie **SAP NetWeaver 7.5** > **IBM DB2 für Linux, Unix und Windows** > **SAP-Systeme** > **Anwendungsserver-ABAP**.
3. Öffnen Sie **Verteiltes System** und führen Sie auf dem Datenbankserver die **ASCS-Instanz** und die **Datenbankinstanz** aus.
4. Überprüfen Sie nach der Installation der ASCS-Instanz, ob mit `sapinst` die Ordner `\\sapmnt` und `\\user\sap\trans` erfolgreich freigegeben wurden, damit der nächste Schritt funktioniert.
5. Führen Sie auf dem Anwendungsserver die **primäre Anwendungsserverinstanz** aus. Achten Sie darauf, während der Installation des Anwendungsservers die privaten Adressen für ASCS und die Datenbank-Hostnamen zu verwenden. So wird sichergestellt, dass der Netzverkehr zwischen dem Anwendungsserver und ASCS oder der Datenbank über das private Netz und nicht über das öffentliche Netz läuft.

Sie können jetzt die SAP-Installation entsprechend den SAP-Installationsanweisungen ausführen.
