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

# Adding external storage to your server
{: #storage}

## Setting up external storage
{: #set_up_storage}

External storage can be added to your provisioned server or servers if you want to use it as a backup device or use a snapshot to quickly restore your database in a test environment. In the example, block storage is used for both archiving log files of the database and online and offline backups for the database. The fastest block storage (4 IOPS per GB) was selected to help assure a minimum backup time. Slower block storage might be sufficient for your needs. For more information about {{site.data.keyword.blockstoragefull}}, see [Getting started with Block Storage](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage).

1. Log in to the [{{site.data.keyword.cloud_notm}} infrastructure customer portal](https://control.softlayer.com/).
2. Select **Storage** > **Block Storage**.
3. Click **Order Block Storage** on the Block Storage page.
4. Select the specifics for your storage needs. Table 1 contains recommended values, including 4 IOPS/GB for a typical database workload.

|              Field               |      Value                                        |
| -------------------------------- | ------------------------------------------------- |
|Select Storage Type               | Endurance (default)                               |
|Location                          | DAL10                                             |
|Billing Method                    | Monthly (default)                                 |
|Select Storage Package            | 4 IOPS/GB                                         |
|Select Storage Size               | 1000 GB                                           |
|Specify Snapshot Space Size       | 0 GB                                              |
|Select OS Type                    | Microsoft Windows                                 |
{: caption="Table 1. Recommended values for block storage" caption-side="top"}

5. Click **Continue**.
6. Click **I have read the Master Service Agreement** and **Place Order**.
7. Click **Actions** to the right of your LUN and select **Authorize Host** to access the provisioned storage.
8. Select **Devices**; the **Device Type** defaults to Bare Metal Server. Click **Hardware** and select the host names of your database server.
9. Click **Submit**.
10. Check the status of your provisioned storage under **Devices** > (select your device) > **Storage** tab.
11. Note the **Target Address** and iSCSI Qualified name (IQN) for your server (iSCSI initiator) and the **username** and **password** for authorization with the iSCSI server. That information is used to connect your block storage to your database server.

In the sample deployment, the data retrieved from the Storage tab was
   * Target IP: `10.2.62.78`
   * IQN: `iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * User: `SL01SU276540-H896345`
   * Password: `EtJ79F4RA33dXm2q`

Follow the steps in [Connecting to MPIO iSCSCI LUNS on Microsoft Windows](https://console.bluemix.net/docs/infrastructure/BlockStorage/accessing-block-storage-windows.html#connecting-to-mpio-iscsi-luns-on-microsoft-windows) to connect your block storage to your database server using the data above. Follow the steps carefully; they lead to a new, “offline” disk available for your Windows server.

You can now bring the disk online and initialize it. 
