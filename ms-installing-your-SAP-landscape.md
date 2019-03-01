---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, ABAP, ASCS Instance, Database Instance, ABAP SAP Central Services, SWPM, application server, database server

subcollection: sap-netweaver-ms-qrg


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Installing your SAP landscape
{: #install_landscape}

## Downloading your SAP software
{: #download_software}

You need an SAP S-user ID and Download Authorization to download the DVDs. For more information on the SAP S-user ID, see [How to set up an S-user ID ![External link icon](../icons/launch-glyph.svg "External link icon")](https://www.youtube.com/watch?v=4wICiRTP8u0/){: new_window}.

1. Log in to the [SAP Support Portal ![External link icon](../icons/launch-glyph.svg "External link icon")](https://support.sap.com/en/index.html){: new_window}, click **Download Software**, and download the required DVDs to a local share drive.
2 Transfer the files to your provisioned server.

Another option is to download the [SAP Software Download Manager ![External link icon](../icons/launch-glyph.svg "External link icon")](https://support.sap.com/en/my-support/software-downloads.html#section_995042677){: new_window}, install it on your target server, and directly download the DVD images to the server.

## Installing SAP software
{: #install_software}

After downloading the installation media, follow the standard SAP installation procedure documented in the SAP installation guide for your SAP version and components, and the corresponding SAP Notes. Fore more information, see [SAP Installation Guide ![External link icon](../icons/launch-glyph.svg "External link icon")](https://service.sap.com/instguides){: new_window} and [SAP Notes ![External link icon](../icons/launch-glyph.svg "External link icon")](https://support.sap.com){: new_window}. Both require an SAP S-user ID.

1. Open the root folder of your SWPM-DVD or of your installation master DVD as Administrator, and run `sapinst`. The Welcome to SAP Installation page displays.
2. Select **SAP NetWeaver 7.5** > **IBM DB2 for Linux, Unix, and Windows** > **SAP Systems** > **Application Server ABAP**.
3. Open **Distributed System** and run **ASCS Instance** and **Database Instance** on the database server.
4. Verify that `sapinst` successfully shared folders `\\sapmnt` and `\\user\sap\trans` after the ASCS Instance is installed for the next step to work.
5. Run **Primary Application Server Instance** on the application server. Be sure to use the private addresses for the ASCS and the database hostnames during installation of the application server. This ensures that network traffic between the application server and ASCS, or database, path through the private network and not through the public network.

You can now run your SAP installation according to the SAP installation instructions.
