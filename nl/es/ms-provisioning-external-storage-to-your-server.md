---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, database server, deployment

subcollection: sap-netweaver-ms-qrg

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Adición de almacenamiento externo al servidor
{: #storage}

## Configuración de almacenamiento externo
{: #set_up_storage}

Puede añadir almacenamiento externo al servidor suministrado (o servidores) si desea utilizarlo como dispositivo de copia de seguridad o utilizar una instantánea para restaurar rápidamente la base de datos en un entorno de prueba. En el ejemplo, se utiliza almacenamiento en bloque para archivar los archivos de registro de la base de datos y copias de seguridad en línea y fuera de línea para la base de datos. Se ha seleccionado el almacenamiento en bloque más rápido (10 IOPS por GB) para garantizar el tiempo mínimo de copia de seguridad. Un almacenamiento en bloque más lento puede ser suficiente según sus necesidades. Para obtener más información sobre {{site.data.keyword.blockstoragefull}}, consulte [Iniciación a Almacenamiento en bloque](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted).

1. Inicie sesión en el [portal de clientes de la infraestructura de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){: new_window} con sus credenciales exclusivas.
2. Seleccione **Almacenamiento** > **Almacenamiento en bloque**.
3. Pulse **Realizar pedido de almacenamiento en bloque** en la esquina superior derecha de la página de almacenamiento en bloque.
4. Seleccione los detalles en función de sus necesidades de almacenamiento. La tabla 1 contiene los valores recomendados, incluyendo 10 IOPS/GB para una carga de trabajo de base de datos exigente.

|              Campo               |      Valor                                        |
| -------------------------------- | ------------------------------------------------- |
|Ubicación                          | DAL10                                             |
|Método de facturación                    | Mensual (predeterminado)                                 |
|Nuevo tamaño de almacenamiento                  | 1000 GB                                           |
|Opciones IOPS de almacenamiento              | Resistencia (IOPS por niveles) (predeterminado)                 |
|Resistencia IOPS por niveles             | 10 GB                                             |
|Tamaño de espacio para instantáneas               | 0 GB                                              |
|Tipo de SO                           | Windows 2008+                                     |
{: caption="Tabla 1. Valores recomendados para el almacenamiento en bloque" caption-side="top"}

5. Pulse los dos recuadros de selección y pulse **Realizar pedido**.

## Autorización de hosts
{: #authorize-host}

1. Pulse **Acciones** a la derecha del LUN y seleccione **Autorizar host** para acceder al almacenamiento suministrado.
2. Seleccione **Dispositivos**; el valor predeterminado para **Tipo de dispositivo** es Servidor nativo. Pulse **Hardware** y seleccione los nombres de host del servidor de base de datos.
3. Pulse **Enviar**.
4. Compruebe el estado del almacenamiento suministrado en el separador **Dispositivos** > (seleccione el dispositivo) > **Almacenamiento**.
5. Apunte la **Dirección de destino** y el Nombre calificado iSCSI (IQN) para su servidor (iniciador iSCSI) y el **nombre de usuario** y **contraseña** para la autorización con el servidor iSCSI. Esa información se utiliza para conectar el almacenamiento en bloque con el servidor de base de datos.

En el despliegue de ejemplo, los datos recuperados del separador Almacenamiento son:
   * IP de destino: `10.2.62.78`
   * IQN: `iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * Usuario: `SL01SU276540-H896345`
   * Contraseña: `EtJ79F4RA33dXm2q`

Siga los pasos descritos en [Conexión a los LUN iSCSI de MPIO en Microsoft Windows](/docs/infrastructure/BlockStorage?topic=BlockStorage-mountingWindows#mountingWindows) para conectar el almacenamiento en bloque con el servidor de base de datos utilizando los datos anteriores. Siga los pasos detenidamente; el resultado será un nuevo disco “fuera de línea” disponible para el servidor Windows.

Ahora puede conectar el disco e inicializarlo.
