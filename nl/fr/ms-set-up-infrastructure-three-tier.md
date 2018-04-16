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

# 1. Commande des serveurs 256 Go et 32 Go dans une configuration à trois niveaux
{: #install_three_tier}

Suivez les étapes de la section [Commande de votre serveur 32 Go](/docs/infrastructure/sap-netweaver-ms-qrg/ms-set-up-infrastructure-32GB.html#order_32GB) pour commander le serveur d'applications SAP NetWeaver. Les étapes qui suivent vous guident à travers la commande du serveur de base de données. Le stockage externe est provisionné lors d'une étape ultérieure comme espace de sauvegarde tant pour les fichiers journaux archivés que pour les sauvegardes en ligne intégrales.

## Commande de vos serveurs
{: #order_servers}

1. Connectez-vous au portail [{{site.data.keyword.cloud}} Infrastructure Customer Portal](https://control.softlayer.com) avec vos données d'identification uniques.
2. Cliquez sur l'icône **Unités** dans la page Récapitulatif de compte.
3. Cliquez sur **Au mois** sous Serveurs Bare Metal sur la page Unités. La boîte de dialogue présentant la liste des serveurs s'ouvre.
4. Cliquez sur l'hyperlien sous **STARTING PRICE PER MONTH** afin de sélectionner le serveur **BI.S1.NW256 (OS Options)**.

## Sélection de vos options de serveur
{: #options_256GB}

1. Laissez **1** dans la zone **Quantity**.
2. Sélectionnez **DAL10** pour **Data Center**.
3. Par défaut, la zone **Serveur** affiche une valeur prédéfinie basée sur votre sélection de serveur qui ne peut pas être modifiée.
4. Cliquez sur **32 Go RAM** même si la sélection de **RAM** affiche par défaut une valeur prédéfinie basée sur votre sélection de serveur qui ne peut pas être modifiée.
5. Sélectionnez la version Microsoft Windows de votre choix pour **Operating System**.
6. Sous **Hard Drives**, sélectionnez un second disque du même type que le premier, créez un groupe de stockage RAID de niveau RAID1 à partir des deux disques et couvrant le volume total d'espace de stockage et sélectionnez **Windows Basic** pour **Partition Template**. Laissez l'option **LVM** non cochée.
7. Sélectionnez **500 GB** pour **Public Bandwidth**.
8. Sélectionnez **1 Gbps Redundant Public and Private Network Uplinks** et **Uplink Port Speed**.
9. Pour cet exemple d'installation, conservez les valeurs par défaut pour toutes les autres zones. Vous pouvez consulter [Configuration de vos serveurs physiques](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers) pour obtenir une description détaillée des options.
10. Cliquez sur **Ajouter à la commande** au bas de la page. Vous êtes redirigé vers la page Checkout une fois que votre commande a été vérifiée.

## Définition de configurations système avancées
{: #adv_config}

1. Utilisez les valeurs du tableau 1 dans les zones de Configuration système avancée. Vous trouverez des informations supplémentaires dans les directives fournies sous [Configuration système avancée](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration).

|              Zone               |      Valeur                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|VLAN back end                      | Sélectionnez une valeur dans la liste déroulante, par exemple : `dal10.bcr01a.981`      |
|Sous-réseau                            | Sélectionnez une valeur dans la liste déroulante, par exemple : `10.177.119.192/26`     |
|VLAN front end                     | Sélectionnez une valeur dans la liste déroulante, par exemple : `dal10.fcr01a.926`      |
|Sous-réseau                            | Sélectionnez une valeur dans la liste déroulante, par exemple : 169.46.15.96/27         |
|Scripts de provisionnement                 | Défini sur Aucun par défaut                                                     |
|Clés SSH                          | Ajoutez des clés SSH (si conservé tel quel, pas de clé SSH)                                   |
|User Metadata                     | Laissez cette zone vide                                                          |
|Hostname Server1                  | Par exemple, `e2e2690`                                               |
|Domain Server1                    | Par exemple, `saptest.com`                                           |
{: caption="Tableau 1. Valeurs pour configuration système avancée" caption-side="top"}

## Confirmation de vos sélections
{: #confirm_selections}

1. Confirmez vos sélections sur la page de paiement et cliquez sur **Conditions de services Cloud** et **Contrat de logiciel tiers** sur le côté droit de la page.
2. Cliquez sur **Soumettre commande**. Vous êtes redirigé vers un écran affichant votre numéro de commande. Vous pouvez l'imprimer puisqu'il s'agit aussi du reçu de votre commande.

Une fois votre commande soumise, le serveur peut être utilisé pendant une durée allant de 1 à 4 heures, suivant votre commande. Vous pouvez examiner l'écran Device Details sur la page principale du Portail client (**Devices** > **Device List**) pour déterminer le statut des étapes de provisionnement du serveur. Cliquez sur le **Nom de l'unité** correspondant à votre nom d'hôte donné et à votre domaine pour afficher son état.

## Etapes suivantes

  [2. Préparation de votre serveur pour votre installation SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-256GB.html)
  
  [3. Partitionnement et systèmes de fichiers](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-256GB.html)
  
  [4. Préparation de votre réseau](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-network.html#network)
