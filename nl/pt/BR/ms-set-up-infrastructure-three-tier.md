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

# 1. Solicitando servidores de 192 GB e 32 GB para uma configuração com três camadas
{: #install_three_tier}

Siga as etapas de [Pedindo seu servidor de 32 GB](/docs/infrastructure/sap-netweaver-ms-qrg/ms-set-up-infrastructure-32GB.html#order_32GB) para pedir o servidor de aplicativos SAP NetWeaver. As etapas a seguir fornecem orientação durante o pedido do servidor de banco de dados. O armazenamento externo será provisionado em uma etapa posterior como espaço de backup para o banco de dados para arquivos de log arquivados e backups completos on-line.

## Pedindo seu servidor de banco de dados
{: #order_db_servers}

1. Efetue login no [portal do cliente de infraestrutura do {{site.data.keyword.cloud}}](https://control.softlayer.com) com suas credenciais exclusivas.
2. Clique em **Conta** > **Fazer um pedido** na página Resumo da conta.
3. Clique em **Mensal** nos **{{site.data.keyword.baremetal_long}}** na página Dispositivos. A caixa de diálogo Lista de servidores aparece.
4. Os Servidores Certificados SAP estão no topo da lista. Clique no hyperlink em **PREÇO INICIAL POR MÊS** para selecionar o servidor **BI.S3.NW192 (Opções de S.O.)**.

## Configurando seu servidor de banco de dados
{: #configure_server}

1. Deixe **1** no campo **Quantidade**.
2. Selecione **DAL10** para **Data Center**. A lista de data centers depende da disponibilidade do produto em um data center específico.
3. O **servidor** é padronizado para um valor predefinido, com base em sua seleção de servidor, e não pode ser mudado.
4. Clique em **192 GB de RAM**, mesmo que a seleção de **RAM** esteja padronizada como um valor predefinido com base em sua seleção do servidor e não puder ser mudada.
5. Selecione a versão do Microsoft Windows de sua escolha de acordo com o seu **Sistema operacional**. **Nota**: se você estiver trazendo sua própria licença (BYOL) para o sistema operacional, selecione **Outro** > **Nenhum sistema operacional**. Para obter mais informações, consulte [Traga sua própria licença](#byol).
6. Inclua uma segunda unidade SATA de 2 TB verificando se **Controlador de disco 1**
está padronizado como **SATA de 2 TB**. Clique em **Incluir disco**.
7. Clique em **Selecionar todos os discos** e em **Criar grupo de armazenamento RAID**.
8. Clique em **Tipo** e selecione **RAID 1**. Insira um **Tamanho** que cubra a quantia total de armazenamento necessário.
9. Deixe **LVM** desmarcado e aceite o **Modelo de partição** padrão, **Windows básico**.
10. Clique em **Pronto**.

##Selecionando suas opções de servidor adicionais
{: #options_256GB}

1. Selecione **500 GB** para **Largura da banda pública**.
2. Selecione **Uplinks redundantes de rede pública e privada de 1 Gbps** para **Velocidade da porta de uplink**.
3. Deixe os valores padrão para todos os outros campos. Para obter descrições detalhadas da opção, consulte [Construindo um servidor bare metal customizado](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html#addl-server-options).
10. Clique em **Incluir no pedido** na parte inferior da página. Você é redirecionado para a página de check-out após seu pedido ser verificado.

## Definindo configurações do sistema avançado
{: #adv_config}

Use os valores na Tabela 1 para os campos em Configuração do sistema avançado. Mais informações
estão disponíveis nas diretrizes [Opções
de configuração do servidor avançado](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html#adv-system-config).

|              Campo               |      Valor                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|VLAN de backend                      | Selecione na lista suspensa, por exemplo, `dal10.bcr01a.981`      |
|Sub-rede                            | Selecione na lista suspensa, por exemplo, `10.177.119.192/26`     |
|VLAN de Frontend                     | Selecione na lista suspensa, por exemplo, `dal10.fcr01a.926`      |
|Sub-rede                            | Selecione na lista suspensa, por exemplo, 169.46.15.96/27         |
|Provisionar scripts                 | Deixe em branco.                                                         |
|Chaves SSH                          | Padronizado como `Add`, o que significa nenhuma chave SSH                            |
|Metadados do usuário                     | Deixar em branco                                                          |
|Hostname Server1                  | Por exemplo, `sdb192`                                                |
|Domain Server1                    | Por exemplo, `saptest.com`                                           |
{: caption="Tabela 1. Valores de configuração do sistema avançado" caption-side="top"}

## Confirmando suas seleções
{: #confirm_selections}

1. Confirme suas seleções na página de check-out e clique em **Termos do serviço de nuvem** e **Contrato de software de terceiros** no lado direito da página.
2. Clique em **Enviar pedido**. Você é redirecionado para uma tela com o seu número de pedido. É possível imprimir a tela, porque ela também é seu recibo do pedido.

Depois que o pedido for enviado, o servidor, dependendo do pedido, estará disponível para uso no prazo de uma a quatro horas. É possível verificar a tela Detalhes do dispositivo na página principal do Portal do Cliente (**Dispositivos** > **Lista de dispositivos**) para um status das etapas de fornecimento. Clique no **Nome do dispositivo** que corresponde ao seu Nome do host e Domínio para ver o status.

## Traga sua própria licença
{: #byol}

Quando você tiver sua própria licença do sistema operacional, instale-a no {{site.data.keyword.baremetal_short}} com base nas instruções do fornecedor. Para obter mais informações, consulte [A opção Nenhum S.O.](https://console.bluemix.net/docs/bare-metal/introduction-no-os.html#how-to-install-an-operating-system-on-a-no-os-server-).

## Próximas etapas

  [2. Preparando o servidor para a instalação da SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-256GB.html)
  
  [3. Particionamento e sistemas de arquivos](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-256GB.html)
  
  [4. Preparando sua rede](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-network.html#network)
