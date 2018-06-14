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

# Incluindo armazenamento externo no servidor
{: #storage}

## Configurando o armazenamento externo
{: #set_up_storage}

O armazenamento externo poderá ser incluído no servidor ou nos servidores provisionados se você desejar usá-los como um dispositivo de backup ou usar uma captura instantânea para restaurar rapidamente seu banco de dados em um ambiente de teste. No exemplo, o armazenamento de bloco é usado para arquivar arquivos de log do banco de dados e backups on-line e off-line do banco de dados. O armazenamento de bloco mais rápido (4 IOPS por GB) foi selecionado para ajudar a assegurar um tempo mínimo de backup. Um armazenamento de bloco mais lento pode ser suficiente para suas necessidades. Para obter mais informações sobre o {{site.data.keyword.blockstoragefull}}, veja [Introdução ao Armazenamento de bloco](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage).

1. Efetue login no [portal do cliente de infraestrutura do {{site.data.keyword.cloud_notm}}](https://control.softlayer.com/).
2. Selecione **Armazenamento** > **Armazenamento de bloco**.
3. Clique em **Pedir armazenamento de bloco** no canto superior direito da página Armazenamento de bloco.
4. Selecione as características para suas necessidades de armazenamento. A Tabela 1 contém os valores recomendados, incluindo 4 IOPS/GB para uma carga de trabalho de banco de dados típica.

|              Campo               |      Valor                                        |
| -------------------------------- | ------------------------------------------------- |
|Selecionar o tipo de armazenamento  | Resistência (padrão)                              |
|Localização                          | DAL10                                             |
|Método de faturamento             | Mensal (padrão)                                   |
|Selecionar o pacote de armazenamento| 4 IOPS/GB                                         |
|Selecionar o tamanho do armazenamento| 1.000 GB                                          |
|Especificar o tamanho do espaço de captura instantânea| 0 GB                          |
|Selecionar o tipo de S.O.           | Microsoft Windows                                 |
{: caption="Tabela 1. Valores recomendados para o armazenamento de bloco" caption-side="top"}

## Autorizando hosts
{: authorize-hosts}

1. Clique em **Continuar**.
2. Clique em **Eu li o Contrato de Prestação de Serviços Principal** e em **Fazer pedido**.
3. Clique em **Ações** à direita do LUN e selecione **Autorizar host** para acessar o armazenamento provisionado.
4. Selecione **Dispositivos**; o **Tipo de dispositivo** é padronizado para Servidor Bare Metal. Clique em **Hardware** e selecione os nomes de host de seu servidor de banco de dados.
5. Clique em **Enviar**.
6. Verifique o status de seu armazenamento provisionado em **Dispositivos** > (selecione seu dispositivo) > guia **Armazenamento**.
7. Observe o **Endereço de destino** e o nome qualificado de iSCSI (IQN) de seu servidor (inicializador iSCSI) e o **nome do usuário** e a **senha** para autorização com o servidor iSCSI. Essas informações são usadas para conectar seu armazenamento de bloco ao servidor de banco de dados.

Na implementação de amostra, os dados recuperados da guia Armazenamento eram
   * IP de destino: `10.2.62.78`
   * IQN: `iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * Usuário: `SL01SU276540-H896345`
   * Senha: `EtJ79F4RA33dXm2q`

Siga as etapas em [Conectando-se a LUNS do MPIO iSCSCI no Microsoft Windows](https://console.bluemix.net/docs/infrastructure/BlockStorage/accessing-block-storage-windows.html#connecting-to-mpio-iscsi-luns-on-microsoft-windows) para conectar seu armazenamento de bloco ao servidor de banco de dados usando os dados acima. Siga as etapas cuidadosamente; elas levam a um novo disco "off-line" disponível para seu servidor Windows.

Agora é possível fazer com que o disco fique on-line e inicializá-lo. 
