---

copyright:
  years: 2017, 2019
lastupdated: "2019-08-06"

keywords: SAP NetWeaver, ABAP, ASCS instance, ABAP SAP Central Services, application server, database server, three-tier

subcollection: sap-netweaver-ms-qrg

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:external: target="_blank" .external}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 4. Preparing your network for a three-tier setup
{: #network}

If you are planning to install a three-tier setup, you need to prepare the network setup accordingly. For the sample setup, a 192 GB database server (named `sdb192`) and a 32 GB application server (named `e2e1270`) have been deployed. The database server also hosts the ABAP SAP Central Services (ASCS) instance. Adding the IPs on the private network to your hosts file helps with the upcoming steps and ensures that SAP internal network traffic goes through the right network.

![Figure 1. Sample of three-tier setup](/images/network_07232019.png "Sample of three-tier setup")

Figure 1. Sample of three-tier setup

The network setup of the deployed servers outlined in Figure 1 is found under Network Connections in Microsoft Windows. In the sample setup, `10.17.139.35` is the private IP of the database server found under Network Connections - Private Network-Teamed, and is one of the IP ranges from RFC 1597. You can determine the IP of the appication server, too, and add both IPs to both servers' `host files` under `C:\Windows\System32\drivers\etc`.

In the {{site.data.keyword.cloud}} console, you can find the private IP of the database server under Menu icon ![Menu icon](../../icons/icon.hamburger.svg) > Resource List > Devices. Select the applicable device and the IP address displays in the respective column.

## Next Steps
{: #network-next-steps}

  * [Adding external storage to your {{site.data.keyword.baremetal_short}}](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-storage)

  * [Installing your SAP applications and software](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-install_landscape)
