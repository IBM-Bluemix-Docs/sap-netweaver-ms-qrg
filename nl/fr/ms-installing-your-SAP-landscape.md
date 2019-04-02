---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, ABAP, ASCS Instance, Database Instance, ABAP SAP Central Services, SWPM, application server, database server

subcollection: sap-netweaver-ms-qrg


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Installation de votre paysage SAP
{: #install_landscape}

## Téléchargement de votre logiciel SAP
{: #download_software}

Vous aurez besoin d'un ID SAP-S-user et d'une autorisation de téléchargement pour télécharger les DVD. Pour plus d'informations sur l'ID SAP S-user, voir [How to set up an S-user ID ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://www.youtube.com/watch?v=4wICiRTP8u0/){: new_window}.

1. Connectez-vous au [portail du support SAP![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://support.sap.com/en/index.html){: new_window}, cliquez sur **Download Software** et téléchargez les DVD requis sur une unité partagée locale.
2. Transférez les fichiers vers votre serveur provisionné.

Une autre option consiste à télécharger l'utilitaire [SAP Software Download Manager ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://support.sap.com/en/my-support/software-downloads.html#section_995042677){: new_window}, à l'installer sur votre serveur cible, puis à télécharger directement les images des DVD sur le serveur.

## Installation du logiciel SAP
{: #install_software}

Après avoir téléchargé le support d'installation, suivez la procédure d'installation SAP standard documentée dans le guide d'installation SAP correspondant à votre version et à vos composants SAP, ainsi que dans le document SAP Notes associé. Pour plus d'informations, reportez-vous aux documents [SAP Installation Guide ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://service.sap.com/instguides){: new_window} et [SAP Notes ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://support.sap.com){: new_window}. Tous deux nécessitent un ID SAP S-user.

1. Ouvrez le dossier racine de votre DVD SWPM ou du DVD principal pour votre installation en tant qu'administrateur et exécutez la commande `sapinst`. La page Welcome to SAP Installation s'affiche.
2. Sélectionnez **SAP NetWeaver 7.5** > **IBM DB2 pour Linux, Unix et Windows** > **SAP Systems** > **Application Server ABAP**.
3. Ouvrez **Distributed System** et exécutez **ASCS Instance** et **Database Instance** sur le serveur de base de données.
4. Vérifiez que la commande `sapinst` a correctement partagé les dossiers `\\sapmnt` et `\\user\sap\trans` après l'installation de l'instance ASCS pour que l'étape suivante fonctionne.
5. Exécutez **Primary Application Server Instance** sur le serveur d'application. Prenez soin d'utiliser les adresses privées pour l'instance ASCS et les noms d'hôte de base de données lors de l'installation du serveur d'application. Ceci garantit que le trafic réseau entre le serveur et l'instance ASCS, ou la base de données, transite via le réseau privé et non pas public.

Vous pouvez à présent procéder à votre installation SAP en suivant les instructions à cet effet.
