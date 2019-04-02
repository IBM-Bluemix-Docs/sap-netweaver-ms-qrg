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

# Instalación del entorno SAP
{: #install_landscape}

## Descarga del software de SAP
{: #download_software}

Necesita un ID S-user de SAP y autorización de descarga para descargar los DVD. Para obtener más información sobre el ID S-user de SAP, consulte [Cómo configurar un ID S-user ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](https://www.youtube.com/watch?v=4wICiRTP8u0/){: new_window}.

1. Inicie sesión en [SAP Support Portal ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](https://support.sap.com/en/index.html){: new_window}, pulse **Descargar software**, y descargue los DVD necesarios en una unidad compartida local.
2. Transfiera los archivos a su servidor suministrado.

Otra opción es descargar [SAP Software Download Manager ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](https://support.sap.com/en/my-support/software-downloads.html#section_995042677){: new_window}, instalarlo en el servidor de destino y descargar directamente las imágenes de DVD en el servidor.

## Instalación del software de SAP
{: #install_software}

Después de descargar el soporte de instalación, siga el procedimiento de instalación de SAP estándar que se documenta en la guía de instalación de SAP para su versión y componentes de SAP, y las Notas de SAP correspondientes. Para obtener más información, consulte la [Guía de instalación de SAP ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](https://service.sap.com/instguides){: new_window} y las [Notas de SAP ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](https://support.sap.com){: new_window}. Ambas requieren un ID S-user de SAP.

1. Abra la carpeta raíz del SWPM-DVD o del DVD maestro de instalación como Administrador y ejecute `sapinst`. Se muestra la página de bienvenida a la instalación de SAP.
2. Seleccione **SAP NetWeaver 7.5** > **IBM DB2 for Linux, Unix, and Windows** > **SAP Systems** > **Application Server ABAP**.
3. Abra **Sistema distribuido** y ejecute **Instancia de ASCS** e **Instancia de base de datos** en el servidor de base de datos.
4. Compruebe que `sapinst` haya compartido las carpetas `\\sapmnt` y `\\user\sap\trans` después de que se haya instalado la Instancia de ASCS para que funcione el siguiente paso.
5. Ejecute la **instancia de servidor de aplicaciones primaria** en el servidor de aplicaciones. Asegúrese de utilizar las direcciones privadas para ASCS y los nombres de host de base de datos durante la instalación del servidor de aplicaciones. Esto garantiza que el tráfico de red entre el servidor de aplicaciones y ASCS, o la base de datos, pase a través de la red privada y no a través de la red pública.

Ahora ya puede ejecutar la instalación de SAP siguiendo las instrucciones de instalación de SAP.
