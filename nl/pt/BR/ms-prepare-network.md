---



copyright:
  years: 2017, 2018
lastupdated: "2018-07-12"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 4. Preparando sua rede para uma configuração de três camadas
{: #network}

Se você estiver planejando instalar uma configuração de três camadas, será necessário preparar a configuração de rede adequadamente. Para a configuração de amostra, um servidor de banco de dados de 192 GB
(denominado `sdb192`) e um servidor de aplicativos de 32 GB (denominado
`e2e1270`) foram implementados. O servidor de banco de dados também hospeda a instância ABAP SAP Central Services (ASCS). Incluir os IPs na rede privada em seus arquivos host ajuda com as próximas etapas e assegura que o tráfego de rede interno da SAP passe pela rede certa.

A configuração de rede dos servidores implementados é localizada em Conexões de rede no Microsoft Windows. Na configuração de amostra, `10.17.139.35` é o IP privado do servidor de banco de dados localizado em Conexões de rede - Rede privada de equipe e é um dos intervalos de IP da RFC 1597. É possível determinar também o IP do servidor de aplicativos e incluir ambos os IPs em ambos os `host files` dos servidores em `C:\Windows\System32\drivers\etc`.

## Próximas etapas

  * [Incluindo armazenamento externo nos {{site.data.keyword.baremetal_short}}](/docs/infrastructure/sap-netweaver-ms-qrg/ms-provisioning-external-storage-to-your-server.html)
  * [Instalando seus aplicativos e softwares SAP](/docs/infrastructure/sap-netweaver-ms-qrg/ms-installing-your-SAP-landscape.html)
