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

# 4. Netz für ein dreischichtiges Setup vorbereiten
{: #network}

Wenn Sie vorhaben, ein dreischichtiges Setup zu installieren, müssen Sie die Netzkonfiguration entsprechend vorbereiten. Für das Beispiel-Setup wurden ein 256-GB-Datenbankserver (mit dem Namen `e2e2690`) und ein 32-GB-Anwendungsserver (mit dem Namen `e2e1270`) bereitgestellt. Der Datenbankserver hostet außerdem die ASCS-Instanz (ABAP SAP Central Services). Das Hinzufügen der IPs im privaten Netz zu Ihrer Datei 'hosts' ist hilfreich für die nachfolgenden Schritte und stellt sicher, dass der interne SAP-Netzverkehr das richtige Netz durchläuft.

![Abb. 1. Beispiel eines dreischichtigen Setups](/images/network-01.png "Beispiel eines dreischichtigen Setups")

Die Netzkonfiguration der bereitgestellten Server, wie in Abb. 1 dargestellt, ist unter den Netzverbindungen in Microsoft Windows zu finden. Im Beispiel-Setup ist `10.17.139.35` die private IP des Datenbankserver, wie unter den Netzverbindungen zu finden, "Private Network-Teamed" und ist einer der IP-Bereiche aus RFC 1597. Sie können auch die IP des Anwendungsservers bestimmen und beide IPs zu den `Hostdateien` beider Server unter `C:\Windows\System32\drivers\etc` hinzufügen.

## Nächste Schritte

  * [Externen Speicher zu {{site.data.keyword.baremetal_short}}n hinzufügen](/docs/infrastructure/sap-netweaver-ms-qrg/ms-provisioning-external-storage-to-your-server.html)
  * [SAP-Anwendungen und -Software installieren](/docs/infrastructure/sap-netweaver-ms-qrg/ms-installing-your-SAP-landscape.html)
