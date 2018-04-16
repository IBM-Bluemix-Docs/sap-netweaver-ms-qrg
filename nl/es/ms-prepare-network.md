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

# 4. Preparación de la red para una configuración de tres capas
{: #network}

Si tiene previsto instalar una configuración de tres capas, debe preparar la configuración la red correctamente. En la configuración de ejemplo, se ha desplegado un servidor de base de datos de 256 GB (denominado `e2e2690`) y un servidor de aplicaciones de 32 GB (denominado `e2e1270`). El servidor de base de datos también aloja la instancia de ASCS (ABAP SAP Central Services). Añadir las direcciones IP de la red privada al archivo hosts ayuda en los pasos siguientes y garantiza que el tráfico de red interno de SAP pase a través de la red correcta.

![Figura 1. Ejemplo de configuración de tres capas](/images/network-01.png "Ejemplo de configuración de tres capas")

La configuración de red de los servidores desplegados mostrada en la Figura 1 se encuentra en Conexiones de red en Microsoft Windows. En la configuración de ejemplo, `10.17.139.35` es la IP privada del servidor de base de datos que se encuentra en Conexiones de red - Red privada-Con equipo y es uno de los rangos de IP desde RFC 1597. También puede determinar la dirección IP del servidor de aplicaciones y añadir ambas direcciones IP a los archivos `hosts` de ambos servidores en `C:\Windows\System32\drivers\etc`.

## Siguientes pasos

  * [Adición de almacenamiento externo a {{site.data.keyword.baremetal_short}}](/docs/infrastructure/sap-netweaver-ms-qrg/ms-provisioning-external-storage-to-your-server.html)
  * [Instalación de software y aplicaciones de SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-installing-your-SAP-landscape.html)
