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

# 1. Ordine del tuo server di 32 GB
{: #install_32GB}

## Ordine del tuo server 
{: #order_32GB}

1. Accedi al [portale del cliente dell'infrastruttura {{site.data.keyword.cloud_notm}}](https://control.softlayer.com) con le tue credenziali univoche.
2. Fai clic su **Devices** nella pagina Account Summary.
3. Fai clic su **Monthly** in Bare Metal Servers nella pagina Devices. Viene visualizzata la finestra di dialogo Server List.
4. Fai clic sull'hyperlink in **STARTING PRICE PER MONTH** per selezionare il server **BI.S1.NW32 (OS Options)**.

## Selezione delle tue opzioni server
{: #options_32GB}

1. Lascia **1** nel campo **Quantity**.
2. Seleziona **DAL10** per **Data Center**. L'elenco dei data center dipende dalla disponibilità del prodotto in un data center particolare.
3. Imposta **Server** su un valore predefinito basato sulla tua selezione del server e non può essere modificato.
4. Fai clic su **32 GB RAM** anche se la selezione **RAM** è impostata su un valore predefinito basato sulla tua selezione server e non può essere modificato.
5. Seleziona la versione di Microsoft Windows di tua scelta come tuo **Operating System**.
6. In **Hard Drives**, seleziona un secondo disco dello stesso tipo del primo, crea un gruppo di archiviazione RAID di RAID1 da entrambi i dischi che copre la quantità totale di memoria e scegli **Windows Basic** come **Partition Template**. Lascia **LVM** non selezionato.
7. Seleziona **500 GB** per **Public Bandwidth**.
8. Seleziona **1 Gbps Redundant Public and Private Network Uplinks** per **Uplink Port Speed**.
9. Per questo esempio di installazione, lascia i valori predefiniti per tutti gli altri campi. Per descrizioni sull'opzione dettagliate, consulta [Setting up your bare metal servers](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers).
10. Fai clic su **Add to Order** in fondo alla pagina. Vieni reindirizzato alla pagina Checkout dopo che il tuo ordine è stato verificato.

## Configurazione delle impostazioni di sistema avanzate
{: #adv_config}

Utilizza i valori nella tabella 1 per i campi in Advanced System Configuration. Sono disponibili ulteriori informazioni nelle linee guida [Advanced System Configuration](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration).

1. Scorri in basso e immetti i valori nella tabella 1 in **Advanced System Configuration**.

|              Campo               |      Valore                                        |
| -------------------------------- | -------------------------------------------------------------------- |
|VLAN di backend                      | Seleziona dall'elenco a discesa, ad esempio, `dal10.bcr01a.981`      |
|Sottorete                            | Seleziona dall'elenco a discesa, ad esempio, `10.177.119.192/26`     |
|VLAN di frontend                     | Seleziona dall'elenco a discesa, ad esempio, `dal10.fcr01a.926`      |
|Sottorete                            | Seleziona dall'elenco a discesa, ad esempio, `169.46.15.96/27`       |
|Script di provisioning                 | Predefiniti su None                                                     |
|Chiavi SSH                          | Aggiungi                                                                  |
|Nome host                          | Ad esempio, `e2e1270`                                               |
|Dominio                            | Ad esempio, `saptest.com`                                           |
{: caption="Tabella 1. Valori di configurazione avanzati 32 GB" caption-side="top"}  

## Conferma delle tue selezioni
{: #confirm_selections}

1. Conferma le tue selezioni nella pagina Checkout e fai clic su **Cloud Service terms** e **3rd Party Software Agreement** nel lato destro della pagina.
2. Fai clic su **Submit Order** nel lato destro del modulo. Vieni reindirizzato a una pagina con il tuo numero d'ordine. Puoi stampare la pagina, perché è anche la tua ricevuta dell'ordine. In aggiunta, ricevi una email di conferma con l'oggetto *Your IBM Cloud Order ## has been approved* con ## che rappresenta il tuo numero d'ordine.

Dopo aver inviato l'ordine, il server, a seconda del tuo ordine, è disponibile per l'utilizzo in un tempo compreso tra una e quattro ore. Puoi controllare la schermata Device Details nella pagina del portale del cliente principale (**Devices** > **Device List**) per uno stato della procedura di provisioning. Fai clic sul **Device Name** che corrisponde ai tuoi nome host e dominio forniti per visualizzare lo stato.

## Passi successivi

  [2. Preparazione del tuo server per la tua installazione SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-32GB.html)
  
  [3. Partizionamento e file system](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-32GB.html)
