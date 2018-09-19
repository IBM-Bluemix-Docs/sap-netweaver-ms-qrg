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

# 4. Preparazione della tua rete per una configurazione su tre livelli
{: #network}

Se stai pianificando di installare una configurazione su tre livelli, devi preparare la configurazione di rete di conseguenza. Per questa configurazione di esempio, sono stati distribuiti un server database di 192 GB (denominato `sdb192`) e un server dell'applicazione di 32 GB (denominato `e2e1270`). Il server database inoltre ospita l'istanza ABAP SAP Central Services (ASCS). L'aggiunta degli IP nella rete privata ai tuoi file host ti aiuta con i prossimi passi e di garantisce che il traffico di rete interno SAP passi per la rete corretta.

La configurazione di rete dei server distribuiti si trova in Network Connections in Microsoft Windows. Nella configurazione di esempio, `10.17.139.35` è l'IP privato del server database trovato in Network Connections - Private Network-Teamed ed è uno degli intervalli di IP da RFC 1597. Puoi anche determinare l'IP del server dell'applicazione e aggiungere entrambi gli IP ad entrambi i `host files` dei server in `C:\Windows\System32\drivers\etc`.

## Passi successivi

  * [Aggiunta dell'archiviazione esterna al tuo {{site.data.keyword.baremetal_short}}](/docs/infrastructure/sap-netweaver-ms-qrg/ms-provisioning-external-storage-to-your-server.html)
  * [Installazione del software e delle applicazioni SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-installing-your-SAP-landscape.html)
