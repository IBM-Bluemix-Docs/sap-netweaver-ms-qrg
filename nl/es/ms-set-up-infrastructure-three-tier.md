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

# 1. Realización del pedido de servidores de 256 GB y 32 GB para una configuración de tres capas
{: #install_three_tier}

Siga los pasos descritos en [Realización del pedido del servidor de 32 GB](/docs/infrastructure/sap-netweaver-ms-qrg/ms-set-up-infrastructure-32GB.html#order_32GB) para realizar el pedido de un servidor de aplicaciones SAP NetWeaver. Los siguientes pasos le guiarán para realizar el pedido del servidor de base de datos. El almacenamiento externo se suministra en un paso posterior como espacio de copia de seguridad para la base de datos de tanto los archivos de registro archivados como las copias de seguridad completas en línea.

## Realización del pedido de servidores
{: #order_servers}

1. Inicie sesión en el [portal del cliente de la infraestructura de {{site.data.keyword.cloud}}](https://control.softlayer.com) con sus credenciales exclusivas.
2. Pulse el icono **Dispositivos** en la página Resumen de la cuenta.
3. Pulse **Mensual** en **{{site.data.keyword.baremetal_long}}** en la página Dispositivos. Se abre el recuadro de diálogo Lista de servidores.
4. Pulse el hiperenlace en **Precio inicial al mes** para seleccionar el servidor **BI.S1.NW256 (Opciones de sistema operativo)**.

## Selección de las opciones de servidor
{: #options_256GB}

1. Deje **1** en el campo **Cantidad**.
2. Seleccione **DAL10** para **Centro de datos**.
3. **Servidor** se establece de forma predeterminada en un valor predefinido sobre la base de la selección de servidor y no se puede cambiar.
4. Pulse **32 GB RAM** aunque **RAM** se establece de forma predeterminada en un valor predefinido sobre la base de la selección de servidor y no se puede cambiar.
5. Seleccione la versión de Microsoft Windows de su elección como **Sistema operativo**.
6. En **Discos duros**, seleccione un segundo disco del mismo tipo que el primero, cree un grupo de almacenamiento RAID de RAID1 desde ambos discos que cubra la cantidad total de almacenamiento, y seleccione **Windows Basic** como **Plantilla de partición**. Deje **LVM** sin marcar.
7. Seleccione **500 GB** para el **Ancho de banda público**.
8. Seleccione **1 Gbps de enlaces ascendentes de red pública y privada redundantes** y **Velocidad de puerto de enlace ascendente**.
9. Para esta instalación de ejemplo, deje los valores predeterminados para todos los demás campos. Puede consultar [Configuración de los servidores nativos](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers) para obtener descripciones detalladas de las opciones.
10. Pulse **Añadir a pedido** en la parte inferior de la página. Se le redirigirá a la página de pago una vez verificado su pedido.

## Ajuste de las configuraciones avanzadas del sistema
{: #adv_config}

1. Utilice los valores de la Tabla 1 para los campos de la Configuración avanzada del sistema. Encontrará más información disponible en las directrices de [Configuración avanzada del sistema](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration).

|              Campo               |      Valor                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|VLAN de fondo                      | Seleccione de la lista desplegable, por ejemplo `dal10.bcr01a.981`      |
|Subred                            | Seleccione de la lista desplegable, por ejemplo `10.177.119.192/26`     |
|VLAN frontal                     | Seleccione de la lista desplegable, por ejemplo `dal10.fcr01a.926`      |
|Subred                            | Seleccione de la lista desplegable, por ejemplo 169.46.15.96/27         |
|Scripts de suministro                 | El valor predeterminado es Ninguno                                                     |
|Claves SSH                          | Añadir (si lo deja en blanco significa: ninguna clave SSH)                                   |
|Metadatos de usuario                     | Dejar en blanco                                                          |
|Nombre de host Servidor1                  | Por ejemplo, `e2e2690`                                               |
|Dominio Servidor1                    | Por ejemplo, `saptest.com`                                           |
{: caption="Tabla 1. Valores de Configuración avanzada del sistema" caption-side="top"}

## Confirmación de las selecciones
{: #confirm_selections}

1. Confirme las selecciones en la página de pago, y pulse **Términos de los servicios en la nube** y **Acuerdo de software de terceros** en la parte derecha de la página.
2. Pulse **Enviar pedido**. Se le redirigirá a una página con el número de pedido. Puede imprimir la página, ya que también es su recibo del pedido.

Una vez enviado el pedido, el servidor estará disponible, dependiendo de su pedido, para su uso en un plazo de una a cuatro horas. Puede comprobar el estado de los distintos pasos del suministro en la pantalla Detalles del dispositivo en la página principal del portal del cliente (**Dispositivos** > **Lista de dispositivos**). Pulse el **Nombre de dispositivo** que coincida con el nombre de host y dominio para ver su estado.

## Siguientes pasos

  [2. Preparación del servidor para la instalación de SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-256GB.html)
  
  [3. Particionamiento y sistemas de archivos](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-256GB.html)
  
  [4. Preparación de la red](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-network.html#network)
