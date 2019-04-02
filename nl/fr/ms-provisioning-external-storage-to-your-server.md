---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, database server, deployment

subcollection: sap-netweaver-ms-qrg

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

Un stockage externe peut être ajouté aux serveurs mis à disposition si vous souhaitez l'utiliser comme unité de sauvegarde ou utiliser une image instantanée pour restaurer rapidement votre base de données dans un environnement de test. Dans notre exemple, un stockage par blocs est utilisé pour l'archivage des fichiers journaux de la base de données tout comme les sauvegardes en ligne et hors ligne de la base de données. Le stockage par blocs le plus rapide (10 IOPS par Go) a été sélectionné pour garantir un temps de sauvegarde minimal. Un stockage par blocs plus lent peut être suffisant pour vos besoins. Pour en savoir plus sur {{site.data.keyword.blockstoragefull}}, voir [Initiation au stockage par blocs](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted).

1. Connectez-vous au [portail client de l'infrastructure {{site.data.keyword.cloud_notm}}![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){: new_window} avec vos données d'identification uniques.
2. Sélectionnez **Stockage** > **Stockage par blocs**.
3. Cliquez sur **Commander du stockage par blocs** à l'angle supérieur droit de la page Stockage par blocs.
4. Sélectionnez vos besoins de stockage spécifiques. Le tableau 1 contient les valeurs recommandées, notamment 10 IOPS/Go pour une charge de travail de base de données exigeante.

|              Zone               |      Valeur                                        |
| -------------------------------- | ------------------------------------------------- |
|Emplacement                          | DAL10                                             |
|Facturation                    | Au mois (valeur par défaut)                                 |
|Nouvelle taille du stockage                  | 1000 Go                                           |
|Options IOPS du stockage              | Endurance (IOPS multiniveau) (valeur par défaut)                 |
|IOPS multiniveau Endurance             | 10 Go                                             |
|Taille de l'espace d'instantané               | 0 Go                                              |
|Type de système d'exploitation                           | Windows 2008+                                     |
{: caption="Tableau 1. Valeurs recommandées pour le stockage par blocs" caption-side="top"}

5. Cochez les deux cases, puis cliquez sur **Valider la commande**.

## Hôtes autorisés
{: #authorize-host}

1. Cliquez sur **Actions** à droite de votre numéro d'unité logique et sélectionnez **Hôte autorisé** pour accéder au stockage provisionné.
2. Sélectionnez **Unités**. Le **Type d'unité** prend la valeur par défaut Serveur physique. Cliquez sur **Matériel** et sélectionnez les noms d'hôte de votre serveur de bases de données.
3. Cliquez sur **Soumettre**.
4. Vérifiez le statut de votre stockage provisionné sous l'onglet **Unités** > (sélectionnez votre unité) > **Stockage**.
5. Notez les valeurs de **Adresse cible** et Nom qualifié iSCSI (IQN) pour votre serveur (initiateur iSCSI), ainsi que celles de **username** et **password** pour autorisation auprès du serveur iSCSI. Ces informations sont utilisées pour connecter le stockage par blocs à votre serveur de base de données.

Dans l'exemple de déploiement, les données extraites de l'onglet Storage étaient les suivantes :
   * IP cible : `10.2.62.78`
   * Nom qualifié iSCSI : `iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * Utilisateur : `SL01SU276540-H896345`
   * Mot de passe : `EtJ79F4RA33dXm2q`

Suivez les étapes de la page [Connexion à des numéros d'unité logique (LUN) MPIO iSCSCI sous Microsoft Windows](/docs/infrastructure/BlockStorage?topic=BlockStorage-mountingWindows#mountingWindows) pour connecter votre stockage par blocs à votre serveur de base de données en utilisant les informations ci-dessus. Suivez attentivement les instructions ; elles mènent à un nouveau disque “hors ligne” disponible pour votre serveur Windows.

Vous pouvez à présent faire passer le disque en ligne et l'initialiser.
