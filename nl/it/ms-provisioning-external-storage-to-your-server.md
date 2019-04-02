---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, database server, deployment

subcollection: sap-netweaver-ms-qrg

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Aggiunta dell'archiviazione esterna al tuo server
{: #storage}

## Configurazione dell'archiviazione esterna
{: #set_up_storage}

L'archiviazione esterna può essere aggiunta ai tuoi server di cui è stato eseguito il provisioning se vuoi utilizzarla come dispositivo di backup o utilizzare un'istantanea per ripristinare velocemente il database nel tuo ambiente di test. Nell'esempio, viene utilizzata l'archiviazione a blocchi per l'archiviazione dei file di log e dei backup online e offline del database. È stata selezionata l'archiviazione a blocchi più veloce (10 IOPS per GB) per garantire un tempo di backup minimo. L'archiviazione a blocchi più lenta potrebbe non essere sufficiente per i tuoi bisogni. Per ulteriori informazioni su {{site.data.keyword.blockstoragefull}}, consulta [Getting started with Block Storage](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted).

1. Accedi al [Portale del cliente dell'infrastruttura {{site.data.keyword.cloud_notm}} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){: new_window} con le tue credenziali univoche. 
2. Seleziona **Storage** > **Block Storage**.
3. Fai clic su **Order Block Storage** nell'angolo in alto a destra della pagina Block Storage.
4. Seleziona le specifiche per i tuoi bisogni di archiviazione. La tabella 1 contiene i valori raccomandati, incluso 10 IOPS/GB per un carico di lavoro del database più impegnativo.

|              Campo               |      Valore                                        |
| -------------------------------- | ------------------------------------------------- |
|Ubicazione                          | DAL10                                             |
|Metodo di fatturazione                    | Mensile (predefinito)                                 |
|Nuova dimensione di archiviazione                  | 1000 GB                                           |
|Opzioni IOPS di archiviazione              | Durata (IOPS a livelli) (predefinita)                 |
|Durata IOPS a livelli             | 10 GB                                             |
|Dimensione spazio istantanea               | 0 GB                                              |
|Tipo SO                           | Windows 2008+                                     |
{: caption="Tabella 1. Valori raccomandati per l'archiviazione a blocchi" caption-side="top"}

5. Fai clic sulle due caselle di spunta e su **Place Order**.

## Autorizzazione degli host
{: #authorize-host}

1. Fai clic su **Actions** alla destra del tuo LUN e seleziona **Authorize Host** per accedere all'archiviazione selezionata.
2. Seleziona **Devices**; e imposta **Device Type** sul valore predefinito Bare Metal Server. Fai clic su **Hardware** e seleziona i nomi host del tuo server database.
3. Fai clic su **Submit**.
4. Controlla lo stato della tua archiviazione selezionata nella scheda **Devices** > (seleziona il tuo dispositivo) > **Storage**.
5. Prendi nota di **Target Address** e iSCSI Qualified name (IQN) del tuo server (iniziatore iSCSI) e **username** e **password** per l'autorizzazione con il server iSCSI. Queste informazioni vengono utilizzate per collegare la tua archiviazione a blocchi al tuo server database.

Nella distribuzione di esempio, i dati richiamati dalla scheda Storage erano
   * IP destinazione: `10.2.62.78`
   * IQN: `iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * Utente: `SL01SU276540-H896345`
   * Password: `EtJ79F4RA33dXm2q`

Segui la procedura in [Connecting to MPIO iSCSCI LUNS on Microsoft Windows](/docs/infrastructure/BlockStorage?topic=BlockStorage-mountingWindows#mountingWindows) per collegare la tua archiviazione a blocchi al tuo server database utilizzando i precedenti dati. Segui la procedura attentamente; ti porta a un nuovo disco “offline” disponibile per il tuo server Windows.

Puoi ora portare il disco online e inizializzarlo.
