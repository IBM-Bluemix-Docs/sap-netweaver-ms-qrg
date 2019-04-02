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

# 1. Ordine del tuo server di 32 GB
{: #install_32GB}

## Ordine del tuo server
{: #order_32GB}

1. Accedi al [Portale del client dell'infrastruttura {{site.data.keyword.cloud_notm}} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com){: new_window} con le tue credenziali univoche. 
2. Fai clic su **Account** > **Place an Order** nella pagina Account Summary.
3. Fai clic su **Monthly** in {{site.data.keyword.baremetal_short}} nella pagina Devices. Viene visualizzato l'elenco dei server; i server certificati SAP sono all'inizio dell'elenco.
4. Fai clic sull'hyperlink in **STARTING PRICE PER MONTH** per selezionare il server **BI.S3.NW32 (OS Options)**.

Il server BI.S3.NW32 (OS Options) è disponibile anche per la fatturazione **Hourly**.
{: note}

## Configurazione del tuo server
{: #configure_server}

1. Lascia **1** nel campo **Quantity**.
2. Seleziona **DAL10** per **Data Center**. L'elenco dei data center dipende dalla disponibilità del prodotto in un data center particolare.
3. Imposta **Server** su un valore predefinito basato sulla tua selezione del server e non può essere modificato.
4. Fai clic su **32 GB RAM** anche se la selezione **RAM** è impostata su un valore predefinito basato sulla tua selezione server e non può essere modificato.
5. Seleziona la versione di Microsoft Windows di tua scelta come tuo **Operating System**. **Nota**: se stai utilizzando BYOL (Bring Your Own License) per il tuo sistema operativo, seleziona **Other** > **No Operating System**. Per ulteriori informazioni, vedi [BYOL (Bring Your Own License)](#byol).
6. Aggiungi una seconda unità SATA da 2 TB verificando che **Disk Controller 1** sia **2 TB SATA** per impostazione predefinita. Fai clic su **Add Disk**.
7. Fai clic su **Select All Disks** e su **Create RAID storage group**.
8. Fai clic su **Type** e seleziona **RAID 1**. Immetti una **Size** che include la quantità totale di archiviazione di cui hai bisogno.
9. Lascia **LVM** non selezionato e accetta il valore predefinito di **Partition Template**, **Windows Basic**.
10. Fai clic su **Done**.

## Selezione delle tue opzioni server aggiuntive
{: #options_32GB

1. Seleziona **500 GB** per **Public Bandwidth**.
2. Seleziona **1 Gbps Redundant Public and Private Network Uplinks** per **Uplink Port Speed**.
3. Lascia i valori predefiniti per tutti gli altri campi. Per delle descrizioni delle opzioni dettagliate, consulta [Creazione di un server bare metal personalizzato](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server).
10. Fai clic su **Add to Order** in fondo alla pagina. Vieni reindirizzato alla pagina Checkout dopo che il tuo ordine è stato verificato.

## Configurazione delle impostazioni di sistema avanzate
{: #adv_config}

Utilizza i valori nella tabella 1 per i campi in Advanced System Configuration. Sono disponibili ulteriori informazioni nelle linee guida [Opzioni di configurazione del server avanzate](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server).

1. Scorri in basso e immetti i valori nella tabella 1 in **Advanced System Configuration**.

|              Campo               |      Valore                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|VLAN di backend                      | Seleziona dall'elenco a discesa, ad esempio, `dal10.bcr01a.981`      |
|Sottorete                            | Seleziona dall'elenco a discesa, ad esempio, `10.177.119.192/26`     |
|VLAN di frontend                     | Seleziona dall'elenco a discesa, ad esempio, `dal10.fcr01a.926`      |
|Sottorete                            | Seleziona dall'elenco a discesa, ad esempio, `169.46.15.96/27`       |
|Script di provisioning                 | Lascia vuoto                                                          |
|Chiavi SSH                          | Il valore predefinito è `Add`, che significa nessuna chiave SSH                            |
|Nome host                          | Ad esempio, `e2e1270`                                               |
|Dominio                            | Ad esempio, `saptest.com`                                           |
{: caption="Tabella 1. Valori di configurazione avanzati 32 GB" caption-side="top"}  

## Conferma delle tue selezioni
{: #confirm_selections}

1. Conferma le tue selezioni nella pagina Checkout e fai clic su **Cloud Service terms** e **3rd Party Software Agreement** nel lato destro della pagina.
2. Fai clic su **Submit Order** nel lato destro del modulo. Vieni reindirizzato a una pagina con il tuo numero d'ordine. Puoi stampare la pagina, perché è anche la tua ricevuta dell'ordine. In aggiunta, ricevi una email di conferma con l'oggetto *Your IBM Cloud Order ## has been approved* con ## che rappresenta il tuo numero d'ordine.

Dopo aver inviato l'ordine, il server, a seconda del tuo ordine, è disponibile per l'utilizzo in un tempo compreso tra una e quattro ore. Puoi controllare la schermata Device Details nella pagina del portale del cliente principale (**Devices** > **Device List**) per uno stato della procedura di provisioning. Fai clic sul **Device Name** che corrisponde ai tuoi nome host e dominio forniti per visualizzare lo stato.

## BYOL (Bring Your Own License)
{: #byol}

Quando hai la tua licenza del sistema operativo, installala sul tuo {{site.data.keyword.baremetal_short}} in base alle istruzioni del fornitore. Per ulteriori informazioni, vedi [L'opzione no SO](/docs/bare-metal?topic=bare-metal-the-no-os-option).

## Passi successivi

  [2. Preparazione del tuo server per la tua installazione SAP](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-2-preparing-your-server-for-your-sap-installation-32-gb-)

  [3. Partizionamento e file system](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-partition_32GB)
