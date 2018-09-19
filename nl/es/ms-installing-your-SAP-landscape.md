---



copyright:
  years: 2017, 2018
lastupdated: "2018-07-09"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Instalación del entorno SAP
{: #install_landscape}

## Descarga del software de SAP
{: #download_software}

Necesita un ID S-user de SAP y autorización de descarga para descargar los DVD. Para obtener más información sobre el ID S-user de SAP, consulte [Cómo configurar un ID S-user](https://www.sapappsdevelopmentpartnercenter.com/en/faq/program-faqs_2/how-to-receive-an-s-user-to-access-the-s_77).

1. Inicie sesión en [SAP Support Portal](https://support.sap.com/en/index.html), pulse **Descargar software**, y descargue los DVD necesarios en una unidad compartida local. 
2 Transfiera los archivos a su servidor suministrado. 

Otra opción es descargar [SAP Software Download Manager](https://support.sap.com/en/my-support/software-downloads.html#section_995042677), instalarlo en el servidor de destino y descargar directamente las imágenes de DVD en el servidor. 

## Instalación del software de SAP
{: #install_software}

Después de descargar el soporte de instalación, siga el procedimiento de instalación de SAP estándar que se documenta en la guía de instalación de SAP para su versión y componentes de SAP, y las Notas de SAP correspondientes. Para obtener más información, consulte la [Guía de instalación de SAP](https://service.sap.com/instguides) y las [Notas de SAP](https://support.sap.com). Ambas requieren un ID S-user de SAP.

1. Abra la carpeta raíz del SWPM-DVD o del DVD maestro de instalación como Administrador y ejecute `sapinst`. Se muestra la página de bienvenida a la instalación de SAP.
2. Seleccione **SAP NetWeaver 7.5** > **IBM DB2 for Linux, Unix, and Windows** > **SAP Systems** > **Application Server ABAP**.
3. Abra **Sistema distribuido** y ejecute **Instancia de ASCS** e **Instancia de base de datos** en el servidor de base de datos.
4. Compruebe que `sapinst` haya compartido las carpetas `\\sapmnt` y `\\user\sap\trans` después de que se haya instalado la Instancia de ASCS para que funcione el siguiente paso.
5. Ejecute la **instancia de servidor de aplicaciones primaria** en el servidor de aplicaciones. Asegúrese de utilizar las direcciones privadas para ASCS y los nombres de host de base de datos durante la instalación del servidor de aplicaciones. Esto garantiza que el tráfico de red entre el servidor de aplicaciones y ASCS, o la base de datos, pase a través de la red privada y no a través de la red pública.

Ahora ya puede ejecutar la instalación de SAP siguiendo las instrucciones de instalación de SAP.

