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

# Instalando a paisagem da SAP
{: #install_landscape}

## Fazendo download do software SAP
{: #download_software}

São necessários um ID de usuário do SAP S e uma Autorização de download para fazer download dos DVDs. Para obter mais informações sobre o ID de usuário do SAP S, veja [Como configurar um ID de usuário do S](https://www.sapappsdevelopmentpartnercenter.com/en/faq/program-faqs_2/how-to-receive-an-s-user-to-access-the-s_77).

1. Efetue login no [Portal de Suporte do SAP](https://support.sap.com/en/index.html), clique em **Fazer download do software** e faça download dos DVDs necessários para uma unidade de compartilhamento local. 
2 Transfira os arquivos para o servidor provisionado. 

Outra opção é fazer download do [SAP Software Download Manager](https://support.sap.com/en/my-support/software-downloads.html#section_995042677), instalá-lo no servidor de destino e fazer download das imagens de DVD diretamente no servidor. 

## Instalando o software SAP
{: #install_software}

Depois de fazer download da mídia de instalação, siga o procedimento de instalação padrão da SAP documentado no guia de instalação da SAP de sua versão e componentes da SAP, além das Notas SAP correspondentes. Para obter mais informações, veja [Guia de instalação da SAP](https://service.sap.com/instguides) e [Notas SAP](https://support.sap.com). Ambos requerem um ID de usuário do SAP S.

1. Abra a pasta raiz do DVD SWPM ou do DVD principal da instalação como Administrador e execute `sapinst`. A página Bem-vindo à instalação da SAP é exibida.
2. Selecione **SAP NetWeaver 7.5** > **IBM DB2 for Linux, Unix and Windows** > **Sistemas SAP** > **Servidor de Aplicativos ABAP**.
3. Abra **Sistema distribuído** e execute **Instância ASCS** e **Instância de banco de dados** no servidor de banco de dados.
4. Verifique se `sapinst` compartilhou com êxito as pastas `\\sapmnt` e `\\user\sap\trans` após a instalação da Instância ASCS para que a próxima etapa funcione.
5. Execute **Instância do servidor de aplicativos principal** no servidor de aplicativos. Certifique-se de usar os endereços privados para os nomes de host do ASCS e do banco de dados durante a instalação do servidor de aplicativos. Isso assegura que o tráfego de rede entre o servidor de aplicativos e o ASCS, ou o banco de dados, passe pela rede privada e não pela rede pública.

Agora é possível executar a instalação da SAP de acordo com as instruções de instalação da SAP.

