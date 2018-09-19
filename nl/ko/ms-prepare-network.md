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

# 4. 3 티어 설정을 위한 네트워크 준비
{: #network}

3 티어 설정을 설치하려는 경우 네트워크 설정을 적절하게 준비해야 합니다. 샘플 설정의 경우, 192GB 데이터베이스 서버(이름이 `sdb192`임) 및 32GB 애플리케이션 서버(이름이 `e2e1270`임)가 배치되었습니다. 또한 데이터베이스 서버는 ASCS(ABAP SAP Central Services) 인스턴스를 호스팅합니다. 사설 네트워크의 IP를 호스트 파일에 추가하면 이후 단계를 수행하는 데 도움이 되며 SAP 내부 네트워크 트래픽이 올바른 네트워크를 통과하게 됩니다.

배치된 서버의 네트워크 설정은 Microsoft Windows의 네트워크 연결 아래에서 찾을 수 있습니다. 샘플 설정에서는 `10.17.139.35`가 네트워크 연결 - 사설 네트워크 - 팀 구성 아래에 있는 데이터베이스 서버의 사설 IP이며 RFC 1597의 IP 범위 중 하나입니다. 애플리케이션 서버의 IP도 판별하여 두 IP를 모두 `C:\Windows\System32\drivers\etc` 아래에 있는 두 서버의 `host files`에 추가할 수 있습니다.

## 다음 단계

  * [{{site.data.keyword.baremetal_short}}에 외부 스토리지 추가](/docs/infrastructure/sap-netweaver-ms-qrg/ms-provisioning-external-storage-to-your-server.html)
  * [SAP 애플리케이션 및 소프트웨어 설치](/docs/infrastructure/sap-netweaver-ms-qrg/ms-installing-your-SAP-landscape.html)
