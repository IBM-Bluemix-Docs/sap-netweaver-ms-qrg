---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, bring your own license, BYOL, VLAN

subcollection: sap-netweaver-ms-qrg

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. Pedindo seu servidor de 32 GB
{: #install_32GB}

## Pedindo seu servidor
{: #order_32GB}

1. Efetue login no portal do cliente da infraestrutura do [{{site.data.keyword.cloud_notm}} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com){: new_window} com suas credenciais exclusivas.
2. Clique em **Conta** > **Fazer um pedido** na página Resumo da conta.
3. Clique em **Mensal** nos {{site.data.keyword.baremetal_short}} na página Dispositivos. A Lista de servidores aparece; os Servidores certificados por SAP estão na parte superior da lista.
4. Clique no hyperlink em **PREÇO INICIAL POR MÊS** para selecionar o servidor
**BI.S3.NW32 (Opções do S.O.)**.

O servidor BI.S3.NW32 (Opções de S.O.) também está disponível para faturamento **Por hora**.
{: note}

## Configurando seu servidor
{: #configure_server}

1. Deixe **1** no campo **Quantidade**.
2. Selecione **DAL10** para **Data Center**. A lista de data centers depende da disponibilidade do produto em um data center específico.
3. O **servidor** é padronizado para um valor predefinido, com base em sua seleção de servidor, e não pode ser mudado.
4. Clique em **32 GB RAM**, embora a seleção de **RAM** seja padronizada para um valor predefinido com base em sua seleção de servidor e não possa ser mudada.
5. Selecione a versão do Microsoft Windows de sua escolha de acordo com o seu **Sistema operacional**. **Nota**: se você estiver trazendo sua própria licença (BYOL) para o sistema operacional, selecione **Outro** > **Nenhum sistema operacional**. Para obter mais informações, consulte [Traga sua própria licença](#byol).
6. Inclua uma segunda unidade SATA de 2 TB, verificando se **Controlador de disco 1**
está padronizado como **SATA de 2 TB**. Clique em **Incluir disco**.
7. Clique em **Selecionar todos os discos** e em **Criar grupo de armazenamento RAID**.
8. Clique em **Tipo** e selecione **RAID 1**. Insira um **Tamanho** que cubra a quantia total de armazenamento necessário.
9. Deixe **LVM** desmarcado e aceite o **Modelo de partição** padrão, **Windows básico**.
10. Clique em **Pronto**.

## Selecionando suas opções de servidor adicionais
{: #options_32GB

1. Selecione **500 GB** para **Largura da banda pública**.
2. Selecione **Uplinks redundantes de rede pública e privada de 1 Gbps** para **Velocidade da porta de uplink**.
3. Deixe os valores padrão para todos os outros campos. Para obter descrições detalhadas da opção, consulte [Construindo um servidor bare metal customizado](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server).
10. Clique em **Incluir no pedido** na parte inferior da página. Você é redirecionado para a página de check-out após seu pedido ser verificado.

## Definindo configurações do sistema avançado
{: #adv_config}

Use os valores na Tabela 1 para os campos em Configuração do sistema avançado. Mais informações
estão disponíveis nas diretrizes [Opções
de configuração do servidor avançado](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server).

1. Role para baixo e insira os valores na Tabela 1 em **Configuração do sistema avançado**.

|              Campo               |      Valor                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|VLAN de backend                      | Selecione na lista suspensa, por exemplo, `dal10.bcr01a.981`      |
|Sub-rede                            | Selecione na lista suspensa, por exemplo, `10.177.119.192/26`     |
|VLAN de Frontend                     | Selecione na lista suspensa, por exemplo, `dal10.fcr01a.926`      |
|Sub-rede                            | Selecione na lista suspensa, por exemplo, `169.46.15.96/27`       |
|Provisionar scripts                 | Deixar em branco                                                          |
|Chaves SSH                          | Padroniza como `Add`, o que significa nenhuma chave SSH |
|Nome do Host                          | Por exemplo, `e2e1270`                                               |
|Domínio                            | Por exemplo, `saptest.com`                                           |
{: caption="Tabela 1. Valores de configuração avançada de 32 GB" caption-side="top"}  

## Confirmando suas seleções
{: #confirm_selections}

1. Confirme suas seleções na página de check-out e clique em **Termos do serviço de nuvem** e **Contrato de software de terceiros** no lado direito da página.
2. Clique em **Enviar pedido** no lado direito do formulário. Você é redirecionado para uma página com seu número de pedido. É possível imprimir a página, porque ela também é seu recibo do pedido. Além disso, você receberá um e-mail de confirmação com o assunto *Seu pedido nº do IBM Cloud foi aprovado*, com nº sendo o número do pedido.

Depois que o pedido for enviado, o servidor, dependendo do pedido, estará disponível para uso no prazo de uma a quatro horas. É possível verificar a tela Detalhes do dispositivo na página principal do Portal do Cliente (**Dispositivos** > **Lista de dispositivos**) para um status das etapas de fornecimento. Clique no **Nome do dispositivo** que corresponde ao seu Nome do host e Domínio para ver o status.

## Traga sua própria licença
{: #byol}

Quando você tiver sua própria licença do sistema operacional, instale-a no {{site.data.keyword.baremetal_short}} com base nas instruções do fornecedor. Para obter mais informações, consulte [A opção Nenhum S.O.](/docs/bare-metal?topic=bare-metal-the-no-os-option).

## Próximas etapas

  [2. Preparando o servidor para a instalação da SAP](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-2-preparing-your-server-for-your-sap-installation-32-gb-)

  [3. Particionamento e sistemas de arquivos](/docs/infrastructure/sap-netweaver-ms-qrg?topic=sap-netweaver-ms-qrg-partition_32GB)
