---



copyright:
  years: 2017
lastupdated: "2018-08-13"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. 32GB 서버 주문
{: #install_32GB}

## 서버 주문
{: #order_32GB}

1. 고유 신임 정보로 [{{site.data.keyword.cloud_notm}} 인프라 고객 포털](https://control.softlayer.com)에 로그인하십시오.
2. 계정 요약 페이지에서 **계정** > **주문하기**를 클릭하십시오. 
3. 디바이스 페이지에서 {{site.data.keyword.baremetal_short}} 아래의 **월별**을 클릭하십시오. 서버 목록이 나타납니다. SAP 인증 서버는 목록의 맨 위에 있습니다. 
4. **월별 시작 가격** 아래의 하이퍼링크를 클릭하여 서버 **BI.S3.NW32(OS 옵션)**를 선택하십시오. 

## 서버 구성
{: #configure_server}

1. **수량** 필드를 **1**로 남겨 두십시오.
2. **데이터 센터**로 **DAL10**을 선택하십시오. 데이터 센터 목록은 특정 데이터 센터 내의 제품 가용성에 따라 다릅니다.
3. **서버**는 서버 선택사항에 따라 사전 정의된 값으로 기본값이 설정되며 이를 변경할 수 없습니다.
4. **32GB RAM**을 클릭하십시오. **RAM** 선택사항은 서버 선택사항에 따라 사전 정의된 값으로 기본값이 설정되며 이를 변경할 수 없습니다.
5. 선택한 Microsoft Windows 버전을 **운영 체제**로 선택하십시오. **참고**: 운영 체제에 대해 BYOL(Bringing Your Own License)을 이용하는 경우에는 **기타** > **운영 체제 없음**을 선택하십시오. 자세한 정보는 [BYOL(Bring Your Own License)](#byol)을 참조하십시오. 
6. **디스크 제어기 1**의 기본값이 **2TB SATA**임을 확인하여 두 번째 2TB SATA 드라이브를 추가하십시오. **디스크 추가**를 클릭하십시오. 
7. **모든 디스크 선택**을 클릭하고 **RAID 스토리지 그룹 작성**을 클릭하십시오. 
8. **유형**을 클릭하고 **RAID 1**을 선택하십시오. 필요한 스토리지 양의 총계를 포함하는 **크기**를 선택하십시오. 
9. **LVM**을 선택 취소 상태로 유지하고 기본값 **파티션 템플리트**, **Windows Basic**을 승인하십시오. 
10. **완료**를 클릭하십시오.

## 추가적인 서버 옵션 선택
{: #options_32GB}

1. **공용 대역폭**을 **500GB**로 선택하십시오.
2. **업링크 포트 속도**로 **1Gbps 중복 공용 및 사설 네트워크 업링크**를 선택하십시오.
3. 이 샘플 설치의 경우 다른 모든 필드를 기본값으로 남겨 두십시오. 세부 옵션 설명을 보려면 [사용자 정의 베어메탈 서버 빌드](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html#addl-server-options)를 참조하십시오. 
10. 페이지의 맨 아래에서 **주문에 추가**를 클릭하십시오. 주문이 확인된 후 체크아웃 페이지로 경로 재지정됩니다.

## 고급 시스템 구성 설정
{: #adv_config}

고급 시스템 구성 아래의 필드에 표 1의 값을 사용하십시오. 자세한 정보는 [고급 서버 구성 옵션](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html#adv-system-config) 가이드라인을 참조할 수 있습니다. 

1. 아래로 스크롤하여 **고급 시스템 구성** 아래에 표 1의 값을 입력하십시오.

|필드               |값                                                           |
| -------------------------------- | -------------------------------------------------------------------- |
|백엔드  VLAN                      |드롭 다운 목록에서 선택(예: `dal10.bcr01a.981`)      |
|서브넷                            |드롭 다운 목록에서 선택(예: `10.177.119.192/26`)     |
|프론트엔드 VLAN                     |드롭 다운 목록에서 선택(예: `dal10.fcr01a.926`)      |
|서브넷                            |드롭 다운 목록에서 선택(예: `169.46.15.96/27`)       |
|프로비저닝 스크립트                 |공백으로 남겨 두십시오. |
|SSH 키                          |기본값은 `Add`이며, 이는 SSH 키가 없음을 의미합니다. |
|호스트 이름                          |예: `e2e1270`                                               |
|도메인                            |예: `saptest.com`                                           |
{: caption="표 1. 32GB 고급 구성 값" caption-side="top"}  

## 선택사항 확인
{: #confirm_selections}

1. 체크아웃 페이지에서 선택사항을 확인하고 페이지의 오른쪽에 있는 **클라우드 서비스 이용 약관** 및 **써드파티 소프트웨어 계약**을 클릭하십시오.
2. 양식의 오른쪽에 있는 **주문 제출**을 클릭하십시오. 주문 번호가 표시된 페이지로 경로 재지정됩니다. 이 페이지는 주문 영수증이기도 하므로 페이지를 인쇄할 수 있습니다. 또한 *IBM Cloud 주문 ##이(가) 승인됨*(##은 주문 번호)이라는 제목의 확인 이메일을 수신합니다.

주문이 제출된 후 주문에 따라 1 - 4시간 이내에 서버가 사용 가능하게 됩니다. 기본 고객 포털 페이지의 디바이스 세부사항 화면(**디바이스** > **디바이스 목록**)에서 프로비저닝 단계의 상태를 확인할 수 있습니다. 지정된 호스트 이름 및 도메인과 일치하는 **디바이스 이름**을 클릭하여 해당 상태를 확인하십시오.

## BYOL(Bring Your Own License)
{: #byol}

자체 소유의 운영 체제 라이센스가 있는 경우에는 공급업체의 지시사항에 따라 {{site.data.keyword.baremetal_short}}에 이를 설치하십시오. 자세한 정보는 [OS 옵션 없음](https://console.bluemix.net/docs/bare-metal/introduction-no-os.html#how-to-install-an-operating-system-on-a-no-os-server-)을 참조하십시오. 

## 다음 단계

  [2. SAP 설치를 위해 서버 준비](/docs/infrastructure/sap-netweaver-ms-qrg/ms-prepare-server-32GB.html)
  
  [3. 파티셔닝 및 파일 시스템](/docs/infrastructure/sap-netweaver-ms-qrg/ms-partition-32GB.html)
