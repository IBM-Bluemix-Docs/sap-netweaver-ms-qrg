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

# 4. Preparing your network for a three-tier setup
{: #network}

If you are planning to install a three-tier setup, you need to prepare the network setup accordingly. For the sample setup, a 256 GB database server (named `e2e2690`) and a 32 GB application server (`named e2e1270`) have been deployed. The database server also hosts the ABAP SAP Central Services (ASCS) instance. Adding the IPs on the private network to your hosts file helps with the upcoming steps and ensures that SAP internal network traffic goes through the right network.

![Figure 1. Sample of three-tier setup](/images/network-01.png "Sample of three-tier setup")

The network setup of the deployed servers outlined in Figure 1 is found under Network Connections in Microsoft Windows. In the sample setup, `10.17.139.35` is the private IP of the database server found under Network Connections - Private Network-Teamed, and is one of the IP ranges from RFC 1597. You can determine the IP of the appication server, too, and add both IPs to both servers' `host files` under `C:\Windows\System32\drivers\etc`.

## Next Steps

  * [Adding external storage to your {{site.data.keyword.baremetal_short}}](/docs/infrastructure/sap-netweaver-ms-qrg/ms-provisioning-external-storage-to-your-server.html)
  * [Installing your SAP applications and software](/docs/infrastructure/sap-netweaver-ms-qrg/ms-installing-your-SAP-landscape.html)
