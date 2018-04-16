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

# 1. 3계층 설정을 위한 256GB 및 32GB 서버 주문
{: #install_three_tier}

[32GB 서버 주문](/docs/infrastructure/sap-netweaver-ms-qrg/ms-set-up-infrastructure-32GB.html#order_32GB)의 단계에 따라 SAP NetWeaver 애플리케이션 서버를 주문하십시오. 다음 단계는 데이터베이스 서버를 주문하는 과정을 안내합니다. 외부 스토리지는 이후 단계에서 아카이브된 로그 파일 및 온라인 전체 백업 모두를 위한 데이터베이스의 백업 공간으로 프로비저닝됩니다.

## 서버 주문
{: #order_servers}

1. 고유 신임 정보로 [{{site.data.keyword.cloud}} 인프라 고객 포털](https://control.softlayer.com)에 로그인하십시오.
2. 계정 요약 페이지에서 **디바이스** 아이콘을 클릭하십시오.
3. 디바이스 페이지에서 **{{site.data.keyword.baremetal_long}}** 아래의 **월별**을 클릭하십시오. 서버 목록 대화 상자가 표시됩니다.
4. **월별 시작 가격** 아래의 하이퍼링크를 클릭하여 **BI.S1.NW256(OS 옵션)** 서버를 선택하십시오.

## 서버 옵션 선택
{: #options_256GB}

1. **수량** 필드를 **1**로 남겨 두십시오.
2. **데이터 센터**로 **DAL10**을 선택하십시오.
3. **서버**는 서버 선택사항에 따라 사전 정의된 값으로 기본값이 설정되며 이를 변경할 수 없습니다.
4. **32GB RAM**을 클릭하십시오. **RAM** 선택사항은 서버 선택사항에 따라 사전 정의된 값으로 기본값이 설정되며 이를 변경할 수 없습니다.
5. 선택한 Microsoft Windows 버전을 **운영 체제**로 선택하십시오.
6. **하드 드라이브** 아래에서 첫 번째 디스크와 동일한 유형의 두 번째 디스크를 선택하고 두 개의 디스크에서 총 스토리지 용량을 포괄하는 RAID1의 RAID 스토리지 그룹을 작성한 후 **Windows 기본**을 **파티션 템플리트**로 선택하십시오. **LVM**은 선택되지 않은 상태로 두십시오.
7. **공용 대역폭**을 **500GB**로 선택하십시오.
8. **업링크 포트 속도**와 **1Gbps 중복 공용 및 사설 네트워크 업링크**를 선택하십시오.
9. 이 샘플 설치의 경우 다른 모든 필드를 기본값으로 남겨 두십시오. 옵션에 대한 자세한 설명은 [베어메탈 서버 설정](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers)을 참조하십시오.
10. 페이지의 맨 아래에서 **주문에 추가**를 클릭하십시오. 주문이 확인된 후 체크아웃 페이지로 경로 재지정됩니다.

## 고급 시스템 구성 설정
{: #adv_config}

1. 고급 시스템 구성 아래의 필드에 표 1의 값을 사용하십시오. 자세한 정보는 [Advanced System Configuration](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration) 가이드라인에 있습니다.

|              필드                |      값                                                              |
| -------------------------------- | -------------------------------------------------------------------- |
|백엔드  VLAN                      | 드롭 다운 목록에서 선택(예: `dal10.bcr01a.981`)     |
|서브넷                            | 드롭 다운 목록에서 선택(예: `10.177.119.192/26`)    |
|프론트엔드 VLAN                   | 드롭 다운 목록에서 선택(예: `dal10.fcr01a.926`)     |
|서브넷                            | 드롭 다운 목록에서 선택(예: 169.46.15.96/27)                         |
|프로비저닝 스크립트               | 기본적으로 없음으로 설정됨                                           |
|SSH 키                            | 추가(그대로 유지 - SSH 키가 없음을 의미함)                           |
|사용자 메타데이터                 | 공백으로 두기                                                        |
|호스트 이름 Server1               | 예: `e2e2690`                                       |
|도메인 Server1                    | 예: `saptest.com`                                   |
{: caption="표 1. 고급 시스템 구성 값" caption-side="top"}

## 선택사항 확인
{: #confirm_selections}

1. 체크아웃 페이지에서 선택사항을 확인하고 페이지의 오른쪽에 있는 **클라우드 서비스 이용 약관** 및 **써드파티 소프트웨어 계약**을 클릭하십시오.
2. **주문 제출**을 클릭하십시오. 주문 번호가 표시된 화면으로 경로 재지정됩니다. 이 화면은 주문 영수증이기도 하므로 화면을 인쇄할 수 있습니다.

주문이 제출된 후 주문에 따라 1 - 4시간 이내에 서버가 사용 가능하게 됩니다. 기본 고객 포털 페이지의 디바이스 세부사항 화면(**디바이스** > **디바이스 목록**)에서 프로비저닝 단계의 상태를 확인할 수 있습니다. 지정된 호스트 이름 및 도메인과 일치하는 **디바이스 이름**을 클릭하여 해당 상태를 확인하십시오.

## 다음 단계

  [2. SAP 설치를 위해 서버 준비](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-256GB.html)
  
  [3. 파티셔닝 및 파일 시스템](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-256GB.html)
  
  [4. 네트워크 준비](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-network.html#network)
