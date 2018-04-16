---



copyright:
  years: 2017
lastupdated: "2018-02-26"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. Commande du serveur 32 Go
{: #install_32GB}

## Commande de votre serveur
{: #order_32GB}

1. Connectez-vous au portail [{{site.data.keyword.cloud_notm}} Infrastructure Customer Portal](https://control.softlayer.com) avec vos données d'identification uniques.
2. Cliquez sur **Unités** sur la page Récapitulatif du compte.
3. Cliquez sur **Au mois** sous Serveurs Bare Metal sur la page Unités. La boîte de dialogue présentant la liste des serveurs s'ouvre.
4. Cliquez sur l'hyperlien sous **STARTING PRICE PER MONTH** afin de sélectionner le serveur **BI.S1.NW32 (OS Options)**.

## Sélection de vos options de serveur
{: #options_32GB}

1. Laissez **1** dans la zone **Quantité**.
2. Sélectionnez **DAL10** pour **Centre de données**. La liste des centres de données dépend des produits disponibles dans un centre de données spécifique.
3. Par défaut, la zone **Serveur** affiche une valeur prédéfinie basée sur votre sélection de serveur qui ne peut pas être modifiée.
4. Cliquez sur **32 Go RAM** même si la sélection de **RAM** affiche par défaut une valeur prédéfinie basée sur votre sélection de serveur qui ne peut pas être modifiée.
5. Sélectionnez la version Microsoft Windows de votre choix pour **Operating System**.
6. Sous **Hard Drives**, sélectionnez un second disque du même type que le premier, créez un groupe de stockage RAID de niveau RAID1 à partir des deux disques et couvrant le volume total d'espace de stockage et sélectionnez **Windows Basic** pour **Partition Template**. Laissez l'option **LVM** non cochée.
7. Sélectionnez **500 GB** pour **Public Bandwidth**.
8. Sélectionnez **1 Gbps Redundant Public and Private Network Uplinks** pour **Uplink Port Speed**.
9. Pour cet exemple d'installation, conservez les valeurs par défaut pour toutes les autres zones. Pour obtenir une description détaillée des options, voir [Configuration de vos serveurs physiques](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers).
10. Cliquez sur **Ajouter à la commande** au bas de la page. Vous êtes redirigé vers la page Checkout une fois que votre commande a été vérifiée.

## Définition de configurations système avancées
{: #adv_config}

Utilisez les valeurs du tableau 1 dans les zones de Configuration système avancée. Vous trouverez des informations supplémentaires dans les directives fournies sous [Configuration système avancée](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration).

1. Faites défiler la liste et entrez les valeurs dans le tableau 1 sous **Advanced System Configuration**.

|              Zone               |      Valeur                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|VLAN back end                      | Sélectionnez une valeur dans la liste déroulante, par exemple : `dal10.bcr01a.981`      |
|Sous-réseau                            | Sélectionnez une valeur dans la liste déroulante, par exemple : `10.177.119.192/26`     |
|VLAN front end                     | Sélectionnez une valeur dans la liste déroulante, par exemple : `dal10.fcr01a.926`      |
|Sous-réseau                            | Sélectionnez une valeur dans la liste déroulante, par exemple, `169.46.15.96/27`       |
|Scripts de provisionnement                 | Défini sur Aucun par défaut                                                     |
|Clés SSH                          | Ajouter                                                                  |
|Nom d'hôte                          | Par exemple, `e2e1270`                                               |
|Domaine                            | Par exemple, `saptest.com`                                           |
{: caption="Tableau 1. Valeurs de configuration avancée 32 Go" caption-side="top"}  

## Confirmation de vos sélections
{: #confirm_selections}

1. Confirmez vos sélections sur la page de paiement et cliquez sur **Conditions de services Cloud** et **Contrat de logiciel tiers** sur le côté droit de la page.
2. Cliquez sur **Soumettre commande** sur le côté droit du formulaire. Vous serez redirigé vers une page avec votre numéro de commande. Vous pouvez imprimer la page qui vous servira de reçu. Vous recevrez en outre un courrier électronique de confirmation avec pour objet *Votre commande IBM Cloud numéro ## a été approuvée*, où ## correspond à votre numéro de commande.

Une fois votre commande soumise, en fonction de votre commande, le serveur est disponible pour son utilisation d'ci une à quatre heures. Vous pouvez examiner l'écran Device Details sur la page principale du Portail client (**Devices** > **Device List**) pour déterminer le statut des étapes de provisionnement du serveur. Cliquez sur le **Nom de l'unité** correspondant à votre nom d'hôte donné et à votre domaine pour afficher son état.

## Etapes suivantes

  [2. Préparation de votre serveur pour votre installation SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-32GB.html)
  
  [3. Partitionnement et systèmes de fichiers](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-32GB.html)
