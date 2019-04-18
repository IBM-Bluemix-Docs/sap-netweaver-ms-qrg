---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, bring your own license, BYOL, VLAN

subcollection: sap-netweaver-ms-qrg

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

1. Connectez-vous au [portail client de l'infrastructure {{site.data.keyword.cloud_notm}}![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com){: new_window} avec vos données d'identification uniques.
2. Cliquez sur **Compte** > **Passer une commande** dans la page Récapitulatif du compte.
3. Cliquez sur **Au mois** sous les serveurs Bare Metal dans la page Unités. La liste des serveurs s'affiche avec les serveurs certifiés SAP en début de liste.
4. Cliquez sur l'hyperlien sous **Prix de départ par mois** pour sélectionner le serveur **BI.S3.NW32 (OS Options)**.

Le serveur BI.S3.NW32 (OS Options) est également disponible pour la facturation **à l'heure**.
{: note}

## Configuration de votre serveur
{: #configure_server}

1. Laissez **1** dans la zone **Quantité**.
2. Sélectionnez **DAL10** pour **Centre de données**. La liste des centres de données dépend des produits disponibles dans un centre de données spécifique.
3. Par défaut, la zone **Serveur** affiche une valeur prédéfinie basée sur votre sélection de serveur qui ne peut pas être modifiée.
4. Cliquez sur **32 Go RAM** même si la sélection de **RAM** affiche par défaut une valeur prédéfinie basée sur votre sélection de serveur qui ne peut pas être modifiée.
5. Sélectionnez la version Microsoft Windows de votre choix pour **Système d'exploitation**. **Remarque** : si vous apportez votre propre licence pour votre système d'exploitation, sélectionnez **Autre** > **Sans système d'exploitation**. Pour plus d'informations, voir [Apport de votre propre licence](#byol).
6. Ajoutez une seconde unité SATA de 2 To en vérifiant que **Contrôleur de disques 1** a la valeur par défaut **SATA 2 To**. Cliquez sur **Ajouter un disque**.
7. Cliquez sur **Sélectionner tous les disques**, puis sur **Créer un groupe de stockage RAID**.
8. Cliquez sur **Type** et sélectionnez **RAID 1**. Entrez dans la zone **Taille** une valeur de taille qui couvre la quantité totale de stockage dont vous avez besoin.
9. Laissez **LVM** désélectionné et acceptez les valeurs par défaut des zones **Modèle de partition** et **Windows Basic**.
10. Cliquez sur **Terminé**.

## Sélection de vos options de serveur supplémentaires
{: #options_32GB}

1. Sélectionnez **500 Go** pour **Bande passante publique**.
2. Sélectionnez **Liaisons montantes redondantes de 1 Gbit/s sur réseau public et privé** pour **Vitesse de port de liaison montante**.
3. Conservez les valeurs par défaut pour toutes les autres zones. Pour une description détaillée des options, voir [génération d'un serveur Bare Metal personnalisé](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server).
10. Cliquez sur **Ajouter à la commande** au bas de la page. Vous êtes redirigé vers la page Réservation une fois que votre commande a été vérifiée.

## Définition de configurations système avancées
{: #adv_config}

Utilisez les valeurs du tableau 1 dans les zones de Configuration système avancée. Vous trouverez des informations supplémentaires dans les directives fournies sous les [options de configuration système avancées](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server).

1. Faites défiler la liste et entrez les valeurs dans le tableau 1 sous **Configuration système avancé**.

|              Zone               |      Valeur                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|VLAN de back end                      | Sélectionnez une valeur dans la liste déroulante, par exemple : `dal10.bcr01a.981`      |
|Sous-réseau                            | Sélectionnez une valeur dans la liste déroulante, par exemple : `10.177.119.192/26`     |
|VLAN de front end                     | Sélectionnez une valeur dans la liste déroulante, par exemple : `dal10.fcr01a.926`      |
|Sous-réseau                            | Sélectionnez une valeur dans la liste déroulante, par exemple, `169.46.15.96/27`       |
|Scripts de provisionnement                 | Laissez cette zone vide                                                          |
|Clés SSH                          | Prend par défaut la valeur `Add`, c'est-à-dire pas de clé SSH                            |
|Nom d'hôte                          | Par exemple, `e2e1270`                                               |
|Domaine                            | Par exemple, `saptest.com`                                           |
{: caption="Tableau 1. Valeurs de configuration avancée 32 Go" caption-side="top"}  

## Confirmation de vos sélections
{: #confirm_selections}

1. Confirmez vos sélections sur la page de paiement et cliquez sur **Conditions de services Cloud** et **Contrat de logiciel tiers** sur le côté droit de la page.
2. Cliquez sur **Soumettre commande** sur le côté droit du formulaire. Vous serez redirigé vers une page avec votre numéro de commande. Vous pouvez imprimer la page qui vous servira de reçu. Vous recevrez en outre un courrier électronique de confirmation avec pour objet *Votre commande IBM Cloud numéro ## a été approuvée*, où ## correspond à votre numéro de commande.

Une fois votre commande soumise, en fonction de votre commande, le serveur est disponible pour son utilisation d'ci une à quatre heures. Vous pouvez examiner l'écran Détails de l'unité sur la page principale du Portail client (**Devices** > **Device List**) pour déterminer le statut des étapes de provisionnement du serveur. Cliquez sur le **Nom de l'unité** correspondant à votre nom d'hôte donné et à votre domaine pour afficher son état.

## Apport de votre propre licence
{: #byol}

Lorsque vous disposez de votre propre licence de système d'exploitation, installez-le sur votre serveur {{site.data.keyword.baremetal_short}} en suivant les instructions du fournisseur. Pour plus d'informations, voir l'option [Sans système d'exploitation](/docs/bare-metal?topic=bare-metal-bm-no-os#bm-no-os).

## Etapes suivantes

  [2. Préparation de votre serveur pour votre installation SAP](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-2-preparing-your-server-for-your-sap-installation-32-gb-)

  [3. Partitionnement et systèmes de fichiers](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-partition_32GB)
