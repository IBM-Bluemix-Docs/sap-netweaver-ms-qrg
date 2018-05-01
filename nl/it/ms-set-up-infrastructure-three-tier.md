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

# 1. Ordine dei server di 256 GB e 3 2GB per una configurazione su tre livelli
{: #install_three_tier}

Segui la procedura in [Ordine del tuo server di 32 GB](/docs/infrastructure/sap-netweaver-ms-qrg/ms-set-up-infrastructure-32GB.html#order_32GB) per ordinare il server dell'applicazione SAP NetWeaver. La seguente procedura ti guida attraverso l'ordine del server database. L'archiviazione esterna viene fornita in un passo successivo come spazio di backup per il database per i file di log archiviati e i backup completi offline.

## Ordine dei tuoi server
{: #order_servers}

1. Accedi al [portale del cliente dell'infrastruttura {{site.data.keyword.cloud}}](https://control.softlayer.com) con le tue credenziali univoche.
2. Fai clic sull'icona **Devices** nella pagina Account Summary.
3. Fai clic su **Monthly** in **{{site.data.keyword.baremetal_long}}** nella pagina Devices. Viene visualizzata la finestra di dialogo Server List.
4. Fai clic sull'hyperlink in **STARTING PRICE PER MONTH** per selezionare il server **BI.S1.NW256 (OS Options)**.

## Selezione delle tue opzioni server
{: #options_256GB}

1. Lascia **1** nel campo **Quantity**.
2. Seleziona **DAL10** per **Data Center**.
3. Imposta **Server** su un valore predefinito basato sulla tua selezione del server e non può essere modificato.
4. Fai clic su **32 GB RAM** anche se la selezione **RAM** è impostata su un valore predefinito basato sulla tua selezione server e non può essere modificato.
5. Seleziona la versione di Microsoft Windows di tua scelta come tuo **Operating System**.
6. In **Hard Drives**, seleziona un secondo disco dello stesso tipo del primo, crea un gruppo di archiviazione RAID di RAID1 da entrambi i dischi che copre la quantità totale di memoria e scegli **Windows Basic** come **Partition Template**. Lascia **LVM** non selezionato.
7. Seleziona **500 GB** per **Public Bandwidth**.
8. Seleziona **1 Gbps Redundant Public and Private Network Uplinks** e **Uplink Port Speed**. 
9. Per questo esempio di installazione, lascia i valori predefiniti per tutti gli altri campi. Puoi consultare [Setting up your bare metal servers](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers) per le descrizioni dettagliate delle opzioni.
10. Fai clic su **Add to Order** in fondo alla pagina. Vieni reindirizzato alla pagina Checkout dopo che il tuo ordine è stato verificato.

## Configurazione delle impostazioni di sistema avanzate
{: #adv_config}

1. Utilizza i valori nella tabella 1 per i campi in Advanced System Configuration. Sono disponibili ulteriori informazioni nelle linee guida [Advanced System Configuration](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration).

|              Campo               |      Valore                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|VLAN di backend                      | Seleziona dall'elenco a discesa, ad esempio, `dal10.bcr01a.981`      |
|Sottorete                            | Seleziona dall'elenco a discesa, ad esempio, `10.177.119.192/26`     |
|VLAN di frontend                     | Seleziona dall'elenco a discesa, ad esempio, `dal10.fcr01a.926`      |
|Sottorete                            | Seleziona dall'elenco a discesa, ad esempio, 169.46.15.96/27         |
|Script di provisioning                 | Predefiniti su None                                                     |
|Chiavi SSH                          | Aggiungi (lasciarlo vuoto - significa: nessuna chiave SSH)                                   |
|Metadati utente                     | Lascia vuoto                                                          |
|Nome host Server1                  | Ad esempio, `e2e2690`                                               |
|Dominio Server1                    | Ad esempio, `saptest.com`                                           |
{: caption="Tabella 1. Valori configurazione sistema avanzata" caption-side="top"}

## Conferma delle tue selezioni
{: #confirm_selections}

1. Conferma le tue selezioni nella pagina Checkout e fai clic su **Cloud Service terms** e **3rd Party Software Agreement** nel lato destro della pagina.
2. Fai clic su **Submit Order**. Vieni reindirizzato a una schermata con il tuo numero d'ordine. Puoi stampare la schermata, perché è anche la tua ricevuta dell'ordine. 

Dopo aver inviato l'ordine, il server, a seconda del tuo ordine, è disponibile per l'utilizzo in un tempo compreso tra una e quattro ore. Puoi controllare la schermata Device Details nella pagina del portale del cliente principale (**Devices** > **Device List**) per uno stato della procedura di provisioning. Fai clic sul **Device Name** che corrisponde ai tuoi nome host e dominio forniti per visualizzare lo stato.

## Passi successivi

  [2. Preparazione del tuo server per la tua installazione SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-256GB.html)
  
  [3. Partizionamento e file system](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-256GB.html)
  
  [4. Preparazione della tua rete](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-network.html#network)
