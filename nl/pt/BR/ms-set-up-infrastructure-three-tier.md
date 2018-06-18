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

# 1. Pedindo servidores de 256 GB e de 32 GB para uma configuração de três camadas
{: #install_three_tier}

Siga as etapas de [Pedindo seu servidor de 32 GB](/docs/infrastructure/sap-netweaver-ms-qrg/ms-set-up-infrastructure-32GB.html#order_32GB) para pedir o servidor de aplicativos SAP NetWeaver. As etapas a seguir fornecem orientação durante o pedido do servidor de banco de dados. O armazenamento externo será provisionado em uma etapa posterior como espaço de backup para o banco de dados para arquivos de log arquivados e backups completos on-line.

## Pedindo seus servidores
{: #order_servers}

1. Efetue login no [portal do cliente de infraestrutura do {{site.data.keyword.cloud}}](https://control.softlayer.com) com suas credenciais exclusivas.
2. Clique no ícone **Dispositivos** na página Resumo da conta.
3. Clique em **Mensal** nos **{{site.data.keyword.baremetal_long}}** na página Dispositivos. A caixa de diálogo Lista de servidores aparece.
4. Clique no hiperlink em **PREÇO INICIAL POR MÊS** para selecionar o servidor **BI.S1.NW256 (Opções do S.O.)**.

## Selecionando suas opções do servidor
{: #options_256GB}

1. Deixe **1** no campo **Quantidade**.
2. Selecione **DAL10** para **Data Center**.
3. O **servidor** é padronizado para um valor predefinido, com base em sua seleção de servidor, e não pode ser mudado.
4. Clique em **32 GB RAM**, embora a seleção de **RAM** seja padronizada para um valor predefinido com base em sua seleção de servidor e não possa ser mudada.
5. Selecione a versão do Microsoft Windows de sua escolha de acordo com o seu **Sistema operacional**.
6. Em **Unidades de disco rígido**, selecione um segundo disco do mesmo tipo que o primeiro, crie um grupo de armazenamentos RAID de RAID1 de ambos os discos que cubra a quantidade total de armazenamento e escolha **Windows Básico** como a **Amostra de partição**. Deixe **LVM** desmarcado.
7. Selecione **500 GB** para **Largura da banda pública**.
8. Selecione **Uplinks redundantes de rede pública e privada de 1 Gbps** e **Velocidade da porta de uplink**.
9. Para esta instalação de amostra, deixe os valores padrão para todos os outros campos. É possível consultar [Configurando os servidores bare metal](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers) para obter descrições detalhadas das opções.
10. Clique em **Incluir no pedido** na parte inferior da página. Você é redirecionado para a página de check-out após seu pedido ser verificado.

## Definindo configurações do sistema avançado
{: #adv_config}

1. Use os valores na Tabela 1 para os campos em Configuração do sistema avançado. Mais informações estão disponíveis nas diretrizes de [Configuração do sistema avançado](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration).

|              Campo               |      Valor                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|VLAN de backend                      | Selecione na lista suspensa, por exemplo, `dal10.bcr01a.981`      |
|Sub-rede                            | Selecione na lista suspensa, por exemplo, `10.177.119.192/26`     |
|VLAN de Frontend                     | Selecione na lista suspensa, por exemplo, `dal10.fcr01a.926`      |
|Sub-rede                            | Selecione na lista suspensa, por exemplo, 169.46.15.96/27         |
|Provisionar scripts                 | Padroniza para Nenhum                                                     |
|Chaves SSH                          | Incluir (deixar assim - significa: sem Chave SSH)                          |
|Metadados do usuário                     | Deixar em branco                                                     |
|Hostname Server1                  | Por exemplo, `e2e2690`                                               |
|Domain Server1                    | Por exemplo, `saptest.com`                                           |
{: caption="Tabela 1. Valores de configuração do sistema avançado" caption-side="top"}

## Confirmando suas seleções
{: #confirm_selections}

1. Confirme suas seleções na página de check-out e clique em **Termos do serviço de nuvem** e **Contrato de software de terceiros** no lado direito da página.
2. Clique em **Enviar pedido**. Você é redirecionado para uma tela com o seu número de pedido. É possível imprimir a tela, porque ela também é seu recibo do pedido.

Depois que o pedido for enviado, o servidor, dependendo do pedido, estará disponível para uso no prazo de uma a quatro horas. É possível verificar a tela Detalhes do dispositivo na página principal do Portal do Cliente (**Dispositivos** > **Lista de dispositivos**) para um status das etapas de fornecimento. Clique no **Nome do dispositivo** que corresponde ao seu Nome do host e Domínio para ver o status.

## Próximas etapas

  [2. Preparando o servidor para a instalação da SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-256GB.html)
  
  [3. Particionamento e sistemas de arquivos](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-256GB.html)
  
  [4. Preparando sua rede](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-network.html#network)
