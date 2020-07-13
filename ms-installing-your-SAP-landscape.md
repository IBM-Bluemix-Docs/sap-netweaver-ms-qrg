---

copyright:
  years: 2017, 2020
lastupdated: "2020-05-05"

keywords: SAP NetWeaver, ABAP, ASCS Instance, Database Instance, ABAP SAP Central Services, SWPM, application server, database server

subcollection: sap-netweaver-ms-qrg


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:external: target="_blank" .external}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:note: .note}

# Installing your SAP landscape
{: #install_landscape}

## Downloading your SAP software
{: #download_software}

You need an SAP S-user ID and Download Authorization to download the DVDs. For more information on the SAP S-user ID, see [How to set up an S-user ID](https://www.youtube.com/watch?v=4wICiRTP8u0/){: external}.

1. Log in to the [SAP Support Portal](https://support.sap.com/en/index.html){: external}, click **Download Software**, and download the required DVDs to a local share drive.
2. Transfer the files to your provisioned server.

Another option is to download the [SAP Software Download Manager](https://support.sap.com/en/my-support/software-downloads.html#section_995042677){: external}, install it on your target server, and directly download the DVD images to the server.

## Installing SAP software
{: #install_software}

The following is an example of downloading the applicable SAP NetWeaver software. You may or may not be using  SAP Netweaver 7.5.
{: note}

After downloading the installation media, follow the standard SAP installation procedure documented in the SAP installation guide for your SAP version and components, and the corresponding SAP Notes. Fore more information, see [SAP Installation Guide](https://help.sap.com/viewer/nwguidefinder?gf-task=Install%20a%20new%20system&gf-nwrelease=SAP%20NetWeaver%207.5){: external} (search for the guides based on the Windows OS) and [SAP Notes](https://support.sap.com/en/index.html){: external}. SAP Notes requires an SAP S-user ID.

1. Open the root folder of your SWPM-DVD or of your installation DVD as Administrator, and run `sapinst`. The Welcome to SAP Installation page displays.
2. Select **SAP NetWeaver 7.5** > **IBM DB2 for Linux, Unix, and Windows** > **SAP Systems** > **Application Server ABAP**.
3. Open **Distributed System** and run **ASCS Instance** and **Database Instance** on the database server.
4. Verify that `sapinst` successfully shared folders `\\usr\sap\trans` and `\\sapmnt` after the ASCS Instance is installed for the next step to work.
5. Run **Primary Application Server Instance** on the application server. Be sure to use the private addresses for the ASCS and the database hostnames during installation of the application server. This ensures that network traffic between the application server and ASCS, or database, path through the private network and not through the public network.

You can now run your SAP installation according to the SAP installation instructions.
