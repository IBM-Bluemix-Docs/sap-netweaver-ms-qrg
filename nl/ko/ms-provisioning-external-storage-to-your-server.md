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

# 서버에 외부 스토리지 추가
{: #storage}

## 외부 스토리지 구성
{: #set_up_storage}

외부 스토리지를 백업 디바이스로 사용하거나 테스트 환경에서 스냅샷을 사용하여 데이터베이스를 빠르게 복원하려는 경우 프로비저닝된 서버에 외부 스토리지를 추가하십시오. 이 예에서는 데이터베이스의 로그 파일 아카이브와 데이터베이스의 온라인 및 오프라인 백업 모두에 블록 스토리지가 사용됩니다. 최소 백업 시간을 보장하기 위해 가장 빠른 블록 스토리지(GB당 4IOPS)가 선택되었습니다. 요구사항에 따라 더 느린 블록 스토리지로도 충분할 수 있습니다. {{site.data.keyword.blockstoragefull}}에 대한 자세한 정보는 [블록 스토리지 시작하기](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage)를 참조하십시오.

1. [{{site.data.keyword.cloud_notm}} 인프라 고객 포털](https://control.softlayer.com/)에 로그인하십시오.
2. **스토리지** > **블록 스토리지**를 선택하십시오.
3. 블록 스토리지 페이지의 오른쪽 상단 모서리에서 **블록 스토리지 주문**을 클릭하십시오.
4. 스토리지 요구사항에 대한 고유 정보를 선택하십시오. 표 1에는 4 IOPS/GB를 포함하여 일반 데이터베이스 워크로드에 대해 권장되는 값이 포함되어 있습니다.

|              필드                |      값                                           |
| -------------------------------- | ------------------------------------------------- |
|스토리지 유형 선택                | 내구성(기본값)                                    |
|위치                              | DAL10                                             |
|비용 청구 방법                    | 월별(기본값)                                      |
|스토리지 패키지 선택              | 4 IOPS/GB                                          |
|스토리지 크기 선택                | 1,000GB                                            |
|스냅샷 공간 크기 지정             | 0GB                                               |
|OS 유형 선택                      | Microsoft Windows                                 |
{: caption="표 1. 블록 스토리지에 대한 권장 값" caption-side="top"}

## 호스트 권한 부여
{: authorize-hosts}

1. **계속**을 클릭하십시오.
2. **마스터 서비스 계약을 읽었습니다.**를 클릭한 후 **주문하기**를 클릭하십시오.
3. LUN의 오른쪽에 있는 **조치**를 클릭하고 프로비저닝된 스토리지에 액세스할 수 있도록 **호스트 권한 부여**를 선택하십시오.
4. **디바이스**를 선택하십시오. **디바이스 유형**은 기본적으로 베어메탈 서버로 설정됩니다. **하드웨어**를 클릭하고 데이터베이스 서버의 호스트 이름을 선택하십시오.
5. **제출**을 클릭하십시오.
6. **디바이스** > (디바이스 선택) > **스토리지** 탭 아래에서 프로비저닝된 스토리지의 상태를 확인하십시오.
7. 서버(iSCSI 이니시에이터)의 **대상 주소** 및 iSCSI 규정된 이름(IQN)과 iSCSI 서버에 인증하기 위한 **사용자 이름** 및 **비밀번호**를 기록해 두십시오. 이 정보는 블록 스토리지를 데이터베이스 서버에 연결하는 데 사용됩니다.

샘플 배치의 경우 스토리지 탭에서 검색된 데이터는 다음과 같습니다.
   * 대상 IP: `10.2.62.78`
   * IQN: `iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * 사용자: `SL01SU276540-H896345`
   * 비밀번호: `EtJ79F4RA33dXm2q`

[Microsoft Windows에서 MPIO iSCSCI LUN에 연결](https://console.bluemix.net/docs/infrastructure/BlockStorage/accessing-block-storage-windows.html#connecting-to-mpio-iscsi-luns-on-microsoft-windows)의 단계에 따라 위의 데이터를 사용하여 블록 스토리지를 데이터베이스 서버에 연결하십시오. 단계를 주의 깊게 수행하십시오. 이러한 단계를 수행하면 Windows 서버에 사용 가능한 새로운 "오프라인" 디스크가 생성됩니다.

이제 디스크를 온라인 상태로 전환한 후 초기화할 수 있습니다. 
