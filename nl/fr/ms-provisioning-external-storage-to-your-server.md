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

# Ajout d'une mémoire externe à votre serveur
{: #storage}

## Configuration de stockage externe
{: #set_up_storage}

Une mémoire externe peut être ajoutée aux serveurs mis à disposition si vous souhaitez l'utiliser comme unité de sauvegarde ou utiliser une image instantanée pour restaurer rapidement votre base de données dans un environnement de test. Dans notre exemple, un stockage par blocs est utilisé pour l'archivage des fichiers journaux de la base de données tout comme les sauvegardes en ligne et hors ligne de la base de données. Le stockage par blocs le plus rapide (4 IOPS par Go) a été sélectionné pour garantir un temps de sauvegarde minimal. Un stockage par blocs plus lent peut être suffisant pour vos besoins. Pour en savoir plus sur {{site.data.keyword.blockstoragefull}}, voir [Initiation au stockage par blocs](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage).

1. Connectez-vous au [Portail client d'{{site.data.keyword.cloud_notm}} infrastructure](https://control.softlayer.com/).
2. Sélectionnez **Storage** > **Block Storage**.
3. Cliquez sur **Order Block Storage** à l'angle supérieur droit de la page Block Storage.
4. Sélectionnez vos besoins de stockage spécifiques. Le tableau 1 contient les valeurs recommandées, notamment 4 IOPS/Go pour une charge de travail de base de données typique.

|              Zone               |      Valeur                                        |
| -------------------------------- | ------------------------------------------------- |
|Sélectionner le type de stockage               | Endurance (valeur par défaut)                               |
|Emplacement                          | DAL10                                             |
|Facturation                    | Au mois (valeur par défaut)                                 |
|Sélectionner un package de stockage            | 4 IOPS/Go                                         |
|Sélectionner la taille du stockage               | 1000 Go                                           |
|Indiquer la taille de l'espace d'instantané       | 0 Go                                              |
|Sélectionner le type de système d'exploitation                    | Microsoft Windows                                 |
{: caption="Tableau 1. Valeurs recommandées pour le stockage par blocs" caption-side="top"}

## Hôtes autorisés
{: authorize-hosts}

1. Cliquez sur **Continuer**.
2. Cliquez sur **I have read the Master Service Agreement** et sur **Place Order**.
3. Cliquez sur **Actions** à droite de votre numéro d'unité logique et sélectionnez **Authorize Host** pour accéder au stockage provisionné.
4. Sélectionnez **Unités**. Le **Type d'unité** prend la valeur par défaut Serveur physique. Cliquez sur **Hardware** et sélectionnez les noms d'hôte de votre serveur de bases de données.
5. Cliquez sur **Submit**.
6. Vérifiez le statut de votre stockage provisionné sous l'onglet **Devices** > (sélectionnez votre unité) > **Storage**.
7. Notez les valeurs de **Target Address** et iSCSI Qualified name (IQN) pour votre serveur (initiateur iSCSI), ainsi que celles de **username** et **password** pour autorisation auprès du serveur iSCSI. Ces informations sont utilisées pour connecter le stockage par blocs à votre serveur de base de données.

Dans l'exemple de déploiement, les données extraites de l'onglet Storage étaient les suivantes :
   * IP cible : `10.2.62.78`
   * Nom qualifié iSCSI : `iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * Utilisateur : `SL01SU276540-H896345`
   * Mot de passe : `EtJ79F4RA33dXm2q`

Suivez les étapes de la page [Connexion à des numéros d'unité logique (LUN) MPIO iSCSCI sous Microsoft Windows](https://console.bluemix.net/docs/infrastructure/BlockStorage/accessing-block-storage-windows.html#connecting-to-mpio-iscsi-luns-on-microsoft-windows) pour connecter votre stockage par blocs à votre serveur de base de données en utilisant les informations ci-dessus. Suivez attentivement les instructions ; elles mènent à un nouveau disque “hors ligne” disponible pour votre serveur Windows.

Vous pouvez à présent faire passer le disque en ligne et l'initialiser. 
