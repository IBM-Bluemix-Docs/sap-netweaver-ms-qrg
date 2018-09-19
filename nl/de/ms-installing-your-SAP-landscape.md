---



copyright:
  years: 2017, 2018
lastupdated: "2018-07-09"


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

Zum Herunterladen der DVDs benötigen Sie eine SAP S-Benutzer-ID sowie eine Downloadberechtigung. Weitere Informationen zur SAP S-Benutzer-ID finden Sie unter [Vorgehensweise zum Einrichten einer S-Benutzer-ID](https://www.sapappsdevelopmentpartnercenter.com/en/faq/program-faqs_2/how-to-receive-an-s-user-to-access-the-s_77).

1. Melden Sie sich beim [SAP Support Portal](https://support.sap.com/en/index.html) an, klicken Sie auf **Software heruterladen** und laden Sie die erforderlichen DVDs in ein lokales, gemeinsam genutztes Laufwerk herunter.
2. Übertragen Sie die Dateien auf Ihren bereitgestellten Server. 

Eine andere Option besteht darin, den [Download-Manager für die SAP-Software](https://support.sap.com/en/my-support/software-downloads.html#section_995042677) herunterzuladen, ihn auf Ihrem Zielserver zu installieren und die DVD-Images direkt auf den Server herunterzuladen. 

## SAP-Software installieren
{: #install_software}

Nach dem Herunterladen der Installationsmedien folgen Sie der Standardprozedur für die SAP-Installation, die im SAP-Installationshandbuch für Ihre SAP-Version und die Komponenten sowie in den SAP-Hinweisen dokumentiert ist. Weitere Informationen finden Sie im [SAP-Installationshandbuch](https://service.sap.com/instguides) und in den [SAP-Hinweisen](https://support.sap.com). Für beides ist eine SAP S-Benutzer-ID erforderlich.

1. Öffnen Sie den Stammordner Ihrer SWPM-DVD oder Ihrer Installations-Master-DVD als Administrator und führen Sie den Befehl `sapinst` aus. Die Willkommensseite für die SAP-Installation wird angezeigt.
2. Wählen Sie **SAP NetWeaver 7.5** > **IBM DB2 für Linux, Unix und Windows** > **SAP-Systeme** > **Anwendungsserver-ABAP**.
3. Öffnen Sie **Verteiltes System** und führen Sie auf dem Datenbankserver die **ASCS-Instanz** und die **Datenbankinstanz** aus.
4. Überprüfen Sie nach der Installation der ASCS-Instanz, ob mit `sapinst` die Ordner `\\sapmnt` und `\\user\sap\trans` erfolgreich freigegeben wurden, damit der nächste Schritt funktioniert.
5. Führen Sie auf dem Anwendungsserver die **primäre Anwendungsserverinstanz** aus. Achten Sie darauf, während der Installation des Anwendungsservers die privaten Adressen für ASCS und die Datenbank-Hostnamen zu verwenden. So wird sichergestellt, dass der Netzverkehr zwischen dem Anwendungsserver und ASCS oder der Datenbank über das private Netz und nicht über das öffentliche Netz läuft.

Sie können jetzt die SAP-Installation entsprechend den SAP-Installationsanweisungen ausführen.

