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

# Incluindo armazenamento externo no servidor
{: #storage}

## Configurando o armazenamento externo
{: #set_up_storage}

Armazenamento externo poderá ser incluído em seu servidor ou servidores provisionados se
você desejar utilizá-lo como um dispositivo de backup ou usar uma captura instantânea para restaurar
rapidamente seu banco de dados em um ambiente de teste. No exemplo, o armazenamento de bloco é usado para arquivar arquivos de log do banco de dados e backups on-line e off-line do banco de dados. O armazenamento de bloco mais rápido (10 IOPS por GB) foi selecionado para ajudar a assegurar um tempo
mínimo de backup. Um armazenamento de bloco mais lento pode ser suficiente para suas necessidades. Para obter mais informações sobre o {{site.data.keyword.blockstoragefull}}, veja [Introdução ao Block Storage](/docs/infrastructure/BlockStorage?topic=BlockStorage-getting-started#getting-started).

1. Efetue login no portal do cliente da infraestrutura do [{{site.data.keyword.cloud_notm}} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){: new_window} com suas credenciais exclusivas.
2. Selecione **Armazenamento** > **Block Storage**.
3. Clique em **Pedir armazenamento de bloco** no canto superior direito da página Block Storage.
4. Selecione as características para suas necessidades de armazenamento. A Tabela 1 contém os
valores recomendados, incluindo 10 IOPS/GB para uma carga de trabalho de banco de dados exigente.

|              Campo               |      Valor                                        |
| -------------------------------- | ------------------------------------------------- |
|Localização                          | DAL10                                             |
|Método de faturamento                    | Mensal (padrão)                                 |
|Novo tamanho de armazenamento                  | 1.000 GB                                           |
|Opções de IOPS de armazenamento              | Endurance (IOPS em camada) (padrão)                 |
|IOPS em camada do Endurance             | 10 GB                                             |
|Tamanho do espaço de captura instantânea               | 0 GB                                              |
|Tipo de S.O.                           | Windows 2008 ou mais recente                                     |
{: caption="Tabela 1. Valores recomendados para o armazenamento de bloco" caption-side="top"}

5. Clique nas duas caixas de seleção e em **Fazer pedido**.

## Autorizando hosts
{: #authorize-host}

1. Clique em **Ações** à direita do LUN e selecione **Autorizar host** para acessar o armazenamento provisionado.
2. Selecione **Dispositivos**; o **Tipo de dispositivo** é padronizado para Bare Metal Server. Clique em **Hardware** e selecione os nomes de host de seu servidor de banco de dados.
3. Clique em **Enviar**.
4. Verifique o status de seu armazenamento provisionado em **Dispositivos** > (selecione seu dispositivo) > guia **Armazenamento**.
5. Observe o **Endereço de destino** e o nome qualificado de iSCSI (IQN) de seu servidor (inicializador iSCSI) e o **nome do usuário** e a **senha** para autorização com o servidor iSCSI. Essas informações são usadas para conectar seu armazenamento de bloco ao servidor de banco de dados.

Na implementação de amostra, os dados recuperados da guia Armazenamento eram
   * IP de destino: `10.2.62.78`
   * IQN: `iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * Usuário: `SL01SU276540-H896345`
   * Senha: `EtJ79F4RA33dXm2q`

Siga as etapas em [Conectando-se a LUNS do MPIO iSCSCI no Microsoft Windows](/docs/infrastructure/BlockStorage?topic=BlockStorage-mountingWindows#mountingWindows) para conectar seu armazenamento de bloco ao servidor de banco de dados usando os dados acima. Siga as etapas com cuidado; elas levam a um novo disco “offline” disponível
para o seu servidor Windows.

Agora é possível fazer com que o disco fique on-line e inicializá-lo.
