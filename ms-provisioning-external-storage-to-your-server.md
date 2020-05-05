---

copyright:
  years: 2017, 2020
lastupdated: "2020-05-05"

keywords: SAP NetWeaver, database server, deployment

subcollection: sap-netweaver-ms-qrg

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:external: target="_blank" .external}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:note: .note}
{:tip: .tip}

# Adding external storage to your server
{: #storage}

## Setting up external storage
{: #set_up_storage}

External storage can be added to your provisioned server, or servers, if you want to use it as a backup device, or use a snapshot to quickly restore your database in a test environment. In the example, block storage is used for both archiving log files of the database and online and offline backups for the database. The fastest block storage (10 IOPS per GB) was selected to help assure a minimum backup time. Slower block storage might be sufficient for your needs. For more information about {{site.data.keyword.blockstoragefull}}, see [Getting started with Block Storage](/docs/BlockStorage?topic=BlockStorage-getting-started#getting-started).
{: shortdesc}

{{site.data.keyword.cloud_notm}} storage LUNS can be provisioned with two options - Endurance and Performance. Endurance tiers feature pre-defined performance levels and other features, such as [snapshot](/docs/BlockStorage?topic=BlockStorage-snapshots) and replication. A custom Performance environment is built with allocated input/output operations per second (IOPS) between 100 and 1,000.

## Setting up external storage
{: #setting-up-external-storage}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://cloud.ibm.com/){: external} with your unique credentials.
2. Expand the Menu icon ![Menu icon](../../icons/icon.hamburger.svg) and select *Classic Infrastructure*.
3. Select *Storage* > *Block Storage* > *Order Block Storage*.
4. Select the specifics for your storage needs. Table 1 contains recommended values, including 10 IOPS/GB for a demanding database workload.

|              Field               |      Value                                        |
| -------------------------------- | ------------------------------------------------- |
|Location                          | US South, DAL10                                   |
|Billing Method                    | Monthly (default)                                 |
|Size                              | 1000 GB                                           |
|Endurance (IOPS tiers)            | 10 IOPS/GB                                        |
|Snapshot space                    | 0 GB                                              |
|OS Type                           | Windows 2008+                                     |
{: caption="Table 1. Recommended values for block storage" caption-side="top"}

5. Review the Order Summary.
6. Select **I have read and agree to the terms and conditions listed below**.

### Authorizing host
{: #authorizing-hosts-console}

1. Select **Storage** > **Block Storage**.
2. Highlight your LUN and expand the Action menu ![Action menu](../../icons/action-menu-icon.svg) and select **Authorize Host**.
3. Select a **Device Type** of **Bare Metal Server**.
4. Click **Hardware** to load available devices and select the hostname of your database server.
5. Click **Save**.

  Additional provisioning information can be found under [Ordering Block Storage through the Console](/docs/BlockStorage?topic=BlockStorage-orderingthroughConsole).
  {: tip}  

Follow the steps in [Connecting to MPIO iSCSCI LUNS on Microsoft Windows](/docs/BlockStorage?topic=BlockStorage-mountingWindows#mountingWindows) to connect your block storage to your database server using the data above. Follow the steps carefully; they lead to a new “offline” disk available for your Windows server.

You can now bring the disk online and initialize it.
