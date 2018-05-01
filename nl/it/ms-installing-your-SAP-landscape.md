---



copyright:
  years: 2017, 2018
lastupdated: "2018-02-09"


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

Hai bisogno di un ID utente SAP S e dell'autorizzazione di scaricamento per scaricare i DVD. Per ulteriori informazioni sull'ID utente SAP S, consulta [How to set up an S-user ID](https://www.sapappsdevelopmentpartnercenter.com/en/faq/program-faqs_2/how-to-receive-an-s-user-to-access-the-s_77).

1. Accedi a [SAP Service Marketplace](https://websmp201.sap-ag.de/) e scarica i DVD necessari in un'unità condivisa locale.
2 Trasferisci i file al tuo server di cui è stato eseguito il provisioning. 

Un'altra opzione è di scaricare [SAP Software Download Manager](https://support.sap.com/en/my-support/software-downloads.html#section_995042677), installarlo sul server di destinazione e scaricare direttamente le immagini DVD nel server. 

## Installazione del software SAP 
{: #install_software}

Dopo aver scaricato il supporto di installazione, segui la procedura di installazione SAP standard documentata nella guida di installazione SAP per i componenti e la versione SAP e le note SAP correlate. Per ulteriori informazioni, consulta [SAP Installation Guide](https://service.sap.com/instguides) e [SAP Notes](https://support.sap.com). Entrambi richiedono un ID utente SAP S.

1. Apri la cartella root del tuo SWPM-DVD o del DVD principale di installazione come un amministratore ed esegui `sapinst`. Viene visualizzata la pagina di benvenuto dell'installazione SAP.
2. Seleziona **SAP NetWeaver 7.5** > **IBM DB2 for Linux, Unix, and Windows** > **SAP Systems** > **Application Server ABAP**.
3. Apri **Distributed System** ed esegui **ASCS Instance** e **Database Instance** sul server del database.
4. Verifica che `sapinst` condivida correttamente le cartelle `\\sapmnt` e `\\user\sap\trans` dopo l'installazione dell'istanza ASCS per il funzionamento del prossimo passo.
5. Esegui **Primary Application Server Instance** nel server dell'applicazione. Assicurati di utilizzare gli indirizzi privati per i nomi host del database e ASCS durante l'installazione del server dell'applicazione. Questo garantisce che il traffico di rete tra il server dell'applicazione e ASCS o il database, passi tramite la rete privata e non la pubblica.

Puoi ora eseguire la tua installazione SAP in base alle istruzioni di installazione SAP.

