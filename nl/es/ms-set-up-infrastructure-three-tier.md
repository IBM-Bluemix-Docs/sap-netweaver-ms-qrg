---



copyright:
  years: 2017, 2018
lastupdated: "2018-08-13"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. Realización del pedido de servidores de 192 GB y 32 GB para una configuración de tres capas
{: #install_three_tier}

Siga los pasos descritos en [Realización del pedido del servidor de 32 GB](/docs/infrastructure/sap-netweaver-ms-qrg/ms-set-up-infrastructure-32GB.html#order_32GB) para realizar el pedido de un servidor de aplicaciones SAP NetWeaver. Los siguientes pasos le guiarán para realizar el pedido del servidor de base de datos. El almacenamiento externo se suministra en un paso posterior como espacio de copia de seguridad para la base de datos de tanto los archivos de registro archivados como las copias de seguridad completas en línea.

## Realización del pedido del servidor de base de datos
{: #order_db_servers}

1. Inicie sesión en el [portal de clientes de la infraestructura de {{site.data.keyword.cloud}}](https://control.softlayer.com) con sus credenciales exclusivas.
2. Pulse **Cuenta** > **Realizar un pedido** a página Resumen de la cuenta.
3. Pulse **Mensual** en **{{site.data.keyword.baremetal_long}}** en la página Dispositivos. Se abre el recuadro de diálogo Lista de servidores.
4. Los servidores certificados por SAP están en la parte superior de la lista. Pulse el hiperenlace en **Precio inicial al mes** para seleccionar el servidor **BI.S3.NW192 (Opciones de sistema operativo)**.

## Configuración del servidor de base de datos
{: #configure_server}

1. Deje **1** en el campo **Cantidad**.
2. Seleccione **DAL10** para **Centro de datos**. La lista de los centros de datos depende de la disponibilidad del producto en un centro de datos determinado.
3. **Servidor** se establece de forma predeterminada en un valor predefinido sobre la base de la selección de servidor y no se puede cambiar.
4. Pulse **192 GB RAM** aunque **RAM** se establece de forma predeterminada en un valor predefinido sobre la base de la selección de servidor y no se puede cambiar.
5. Seleccione la versión de Microsoft Windows de su elección como **Sistema operativo**. **Nota**: Si va a traer su propia licencia (BYOL) para su sistema operativo, seleccione **Otros** > **Sin sistema operativo**. Para obtener más información, consulte [Traiga su propia licencia](#byol).
6. Añada una segunda unidad SATA de 2 TB verificando que **Controlador de disco 1** esté como predeterminado a **2 TB SATA**. Pulse **Añadir disco**.
7. Pulse **Seleccionar todos los discos** y pulse **Crear grupo de almacenamiento de RAID**.
8. Pulse **Tipo** y seleccione **RAID 1**. Especifique un **Tamaño** que cubra la cantidad total de almacenamiento que necesita.
9. Deje **LVM** desmarcado y acepte los valores predeterminados **Plantilla de partición**, **Windows Basic**.
10. Pulse **Hecho**.

##Selección de las opciones de servidor adicional
{: #options_256GB}

1. Seleccione **500 GB** para el **Ancho de banda público**.
2. Seleccione **1 Gbps de enlaces ascendentes de red pública y privada redundantes** para **Velocidad de puerto de enlace ascendente**.
3. Deje los valores predeterminados para todos los demás campos. Para obtener descripciones detalladas de las opciones, consulte [Creación de un servidor nativo personalizado](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html#addl-server-options).
10. Pulse **Añadir a pedido** en la parte inferior de la página. Se le redirigirá a la página de pago una vez verificado su pedido.

## Ajuste de las configuraciones avanzadas del sistema
{: #adv_config}

Utilice los valores de la Tabla 1 para los campos de la Configuración avanzada del sistema. Encontrará más información disponible en las directrices de [Opciones de configuración avanzadas del sistema](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html#adv-system-config).

|              Campo               |      Valor                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|VLAN de fondo                      | Seleccione de la lista desplegable, por ejemplo `dal10.bcr01a.981`      |
|Subred                            | Seleccione de la lista desplegable, por ejemplo `10.177.119.192/26`     |
|VLAN frontal                     | Seleccione de la lista desplegable, por ejemplo `dal10.fcr01a.926`      |
|Subred                            | Seleccione de la lista desplegable, por ejemplo 169.46.15.96/27         |
|Scripts de suministro                 | Dejar en blanco.                                                         |
|Claves SSH                          | Dejar predeterminado a `Añadir`, lo que significa que no hay clave SSH                            |
|Metadatos de usuario                     | Dejar en blanco                                                          |
|Nombre de host Servidor1                  | Por ejemplo, `sdb192`                                                |
|Dominio Servidor1                    | Por ejemplo, `saptest.com`                                           |
{: caption="Tabla 1. Valores de Configuración avanzada del sistema" caption-side="top"}

## Confirmación de las selecciones
{: #confirm_selections}

1. Confirme las selecciones en la página de pago, y pulse **Términos de los servicios en la nube** y **Acuerdo de software de terceros** en la parte derecha de la página.
2. Pulse **Enviar pedido**. Se le redirigirá a una página con el número de pedido. Puede imprimir la página, ya que también es su recibo del pedido.

Una vez enviado el pedido, el servidor estará disponible, dependiendo de su pedido, para su uso en un plazo de una a cuatro horas. Puede comprobar el estado de los distintos pasos del suministro en la pantalla Detalles del dispositivo en la página principal del portal de clientes (**Dispositivos** > **Lista de dispositivos**). Pulse el **Nombre de dispositivo** que coincida con el nombre de host y dominio para ver su estado.

## Traiga sus propias licencias
{: #byol}

Cuando tiene su propia licencia de sistema operativo, la instala en su {{site.data.keyword.baremetal_short}} basándose en las instrucciones del vendedor. Para obtener más información, consulte [La opción sin SO](https://console.bluemix.net/docs/bare-metal/introduction-no-os.html#how-to-install-an-operating-system-on-a-no-os-server-).

## Siguientes pasos

  [2. Preparación del servidor para la instalación de SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-256GB.html)
  
  [3. Particionamiento y sistemas de archivos](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-256GB.html)
  
  [4. Preparación de la red](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-network.html#network)
