---



copyright:
  years: 2017, 2018
lastupdated: "2018-08-13"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. Commande de serveurs 192 Go et 32 Go pour une configuration à trois niveaux
{: #install_three_tier}

Suivez les étapes de la section [Commande de votre serveur 32 Go](/docs/infrastructure/sap-netweaver-ms-qrg/ms-set-up-infrastructure-32GB.html#order_32GB) pour commander le serveur d'applications SAP NetWeaver. Les étapes qui suivent vous guident à travers la commande du serveur de base de données. Le stockage externe est provisionné lors d'une étape ultérieure comme espace de sauvegarde tant pour les fichiers journaux archivés que pour les sauvegardes en ligne intégrales.

## Commande de votre serveur de base de données
{: #order_db_servers}

1. Connectez-vous au [portail client de l'infrastructure {{site.data.keyword.cloud}}](https://control.softlayer.com) avec vos données d'identification uniques.
2. Cliquez sur **Compte** > **Passer une commande** dans la page Récapitulatif du compte.
3. Cliquez sur **Au mois** sous Serveurs Bare Metal sur la page Unités. La boîte de dialogue présentant la liste des serveurs s'ouvre.
4. Les serveurs certifiés SAP figurent en début de liste. Cliquez sur l'hyperlien sous **Prix de départ par mois** pour sélectionner le serveur **BI.S3.NW192 (OS Options)**.

## Configuration de votre serveur de base de données
{: #configure_server}

1. Laissez **1** dans la zone **Quantité**.
2. Sélectionnez **DAL10** pour **Centre de données**. La liste des centres de données dépend des produits disponibles dans un centre de données spécifique.
3. Par défaut, la zone **Serveur** affiche une valeur prédéfinie basée sur votre sélection de serveur qui ne peut pas être modifiée.
4. Cliquez sur **192 Go RAM** même si la sélection de **RAM** affiche par défaut une valeur prédéfinie basée sur votre sélection de serveur qui ne peut pas être modifiée.
5. Sélectionnez la version Microsoft Windows de votre choix pour **Système d'exploitation**. **Remarque** : si vous apportez votre propre licence pour votre système d'exploitation, sélectionnez **Autre** > **Sans système d'exploitation**. Pour plus d'informations, voir [Apport de votre propre licence](#byol).
6. Ajoutez une seconde unité SATA de 2 To en vérifiant que **Contrôleur de disques 1** a la valeur par défaut **SATA 2 To**. Cliquez sur **Ajouter un disque**.
7. Cliquez sur **Sélectionner tous les disques**, puis sur **Créer un groupe de stockage RAID**.
8. Cliquez sur **Type** et sélectionnez **RAID 1**. Entrez dans la zone **Taille** une valeur de taille qui couvre la quantité totale de stockage dont vous avez besoin.
9. Laissez **LVM** désélectionné et acceptez les valeurs par défaut des zones **Modèle de partition** et **Windows Basic**.
10. Cliquez sur **Terminé**.

##Sélection de vos options de serveur supplémentaires
{: #options_256GB}

1. Sélectionnez **500 Go** pour **Bande passante publique**.
2. Sélectionnez **Liaisons montantes redondantes de 1 Gbit/s sur réseau public et privé** pour **Vitesse de port de liaison montante**.
3. Conservez les valeurs par défaut pour toutes les autres zones. Pour une description détaillée des options, voir [génération d'un serveur Bare Metal personnalisé](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html#addl-server-options).
10. Cliquez sur **Ajouter à la commande** au bas de la page. Vous êtes redirigé vers la page Réservation une fois que votre commande a été vérifiée.

## Définition de configurations système avancées
{: #adv_config}

Utilisez les valeurs du tableau 1 dans les zones de Configuration système avancée. Vous trouverez des informations supplémentaires dans les directives fournies sous les [options de configuration système avancées](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html#adv-system-config).

|              Zone               |      Valeur                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|VLAN de back end                      | Sélectionnez une valeur dans la liste déroulante, par exemple : `dal10.bcr01a.981`      |
|Sous-réseau                            | Sélectionnez une valeur dans la liste déroulante, par exemple : `10.177.119.192/26`     |
|VLAN de front end                     | Sélectionnez une valeur dans la liste déroulante, par exemple : `dal10.fcr01a.926`      |
|Sous-réseau                            | Sélectionnez une valeur dans la liste déroulante, par exemple : 169.46.15.96/27         |
|Scripts de provisionnement                 | Laissez cette zone vide.                                                         |
|Clés SSH                          | Prend par défaut la valeur `Add`, c'est-à-dire pas de clé SSH                            |
|Métadonnées utilisateur           | Laissez cette zone vide                                                          |
|Nom d'hôte Serveur1               | Par exemple, `sdb192`                                                |
|Domaine Serveur1                  | Par exemple, `saptest.com`                                           |
{: caption="Tableau 1. Valeurs pour configuration système avancée" caption-side="top"}

## Confirmation de vos sélections
{: #confirm_selections}

1. Confirmez vos sélections sur la page de paiement et cliquez sur **Conditions de services Cloud** et **Contrat de logiciel tiers** sur le côté droit de la page.
2. Cliquez sur **Soumettre commande**. Vous êtes redirigé vers un écran affichant votre numéro de commande. Vous pouvez l'imprimer puisqu'il s'agit aussi du reçu de votre commande.

Une fois votre commande soumise, le serveur peut être utilisé pendant une durée allant de 1 à 4 heures, suivant votre commande. Vous pouvez examiner l'écran Détails de l'unité sur la page principale du Portail client (**Devices** > **Device List**) pour déterminer le statut des étapes de provisionnement du serveur. Cliquez sur le **Nom de l'unité** correspondant à votre nom d'hôte donné et à votre domaine pour afficher son état.

## Apport de votre propre licence
{: #byol}

Lorsque vous disposez de votre propre licence de système d'exploitation, installez-le sur votre serveur {{site.data.keyword.baremetal_short}} en suivant les instructions du fournisseur. Pour plus d'informations, voir l'option [Sans système d'exploitation](https://console.bluemix.net/docs/bare-metal/introduction-no-os.html#how-to-install-an-operating-system-on-a-no-os-server-).

## Etapes suivantes

  [2. Préparation de votre serveur pour votre installation SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-256GB.html)
  
  [3. Partitionnement et systèmes de fichiers](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-256GB.html)
  
  [4. Préparation de votre réseau](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-network.html#network)
