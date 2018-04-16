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

# 4. Préparation de votre réseau pour une configuration à trois niveaux
{: #network}

Si vous compter effectuer une installation à trois niveaux, vous aurez besoin de préparer en conséquence la configuration réseau. Dans l'exemple de configuration, un serveur de base de données avec 256 Go de RAM (nommé `e2e2690`) et un serveur d'application avec 32 Go de RAM (`nommé e2e1270`) ont été déployés. Le serveur de base de données héberge également l'instance ASCS (ABAP SAP Central Services). L'ajout des adresses IP au réseau privé dans vos fichiers d'hôtes vous aidera dans les étapes suivantes et garantira que le trafic réseau SAP interne soit acheminé au réseau approprié.

![Figure 1. Exemple de configuration à trois niveaux](/images/network-01.png "Exemple de configuration à trois niveaux")

La configuration réseau des serveurs déployés qui est décrite dans la Figure 1 figure sous Connexions réseau dans Microsoft Windows. Dans l'exemple de configuration, `10.17.139.35` désigne l'IP privée du serveur de base de données figurant sous Network Connections - Private Network-Teamed, et correspond à l'une des plages IP de la spécification RFC 1597. Vous pouvez également déterminer l'IP du serveur d'application et ajouter les deux IP aux entrées `host files` des deux serveurs sous `C:\Windows\System32\drivers\etc`.

## Etapes suivantes

  * [Ajout d'une mémoire externe à vos serveurs Bare Metal](/docs/infrastructure/sap-netweaver-ms-qrg/ms-provisioning-external-storage-to-your-server.html)
  * [Installation de vos logiciels et applications SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-installing-your-SAP-landscape.html)
