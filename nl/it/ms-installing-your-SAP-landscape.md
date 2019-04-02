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

# Installazione del tuo scenario SAP
{: #install_landscape}

## Scaricamento del tuo software SAP
{: #download_software}

Hai bisogno di un ID utente SAP S e dell'autorizzazione di scaricamento per scaricare i DVD. Per ulteriori informazioni sull'ID utente SAP S, consulta [How to set up an S-user ID ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](https://www.youtube.com/watch?v=4wICiRTP8u0/){: new_window}.

1. Accedi a [SAP Support Portal ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](https://support.sap.com/en/index.html){: new_window}, fai clic su **Download Software** e scarica i DVD necessari in un'unità condivisa locale.
2 Trasferisci i file al tuo server di cui è stato eseguito il provisioning.

Un'altra opzione è di scaricare [SAP Software Download Manager ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](https://support.sap.com/en/my-support/software-downloads.html#section_995042677){: new_window}, installarlo sul server di destinazione e scaricare direttamente le immagini DVD nel server.

## Installazione del software SAP
{: #install_software}

Dopo aver scaricato il supporto di installazione, segui la procedura di installazione SAP standard documentata nella guida di installazione SAP per i componenti e la versione SAP e le note SAP correlate. Per ulteriori informazioni, consulta [SAP Installation Guide ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](https://service.sap.com/instguides){: new_window} e [SAP Notes ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](https://support.sap.com){: new_window}. Entrambi richiedono un ID utente SAP S.

1. Apri la cartella root del tuo SWPM-DVD o del DVD principale di installazione come un amministratore ed esegui `sapinst`. Viene visualizzata la pagina di benvenuto dell'installazione SAP.
2. Seleziona **SAP NetWeaver 7.5** > **IBM DB2 for Linux, Unix, and Windows** > **SAP Systems** > **Application Server ABAP**.
3. Apri **Distributed System** ed esegui **ASCS Instance** e **Database Instance** sul server del database.
4. Verifica che `sapinst` condivida correttamente le cartelle `\\sapmnt` e `\\user\sap\trans` dopo l'installazione dell'istanza ASCS per il funzionamento del prossimo passo.
5. Esegui **Primary Application Server Instance** nel server dell'applicazione. Assicurati di utilizzare gli indirizzi privati per i nomi host del database e ASCS durante l'installazione del server dell'applicazione. Questo garantisce che il traffico di rete tra il server dell'applicazione e ASCS o il database, passi tramite la rete privata e non la pubblica.

Puoi ora eseguire la tua installazione SAP in base alle istruzioni di installazione SAP.
