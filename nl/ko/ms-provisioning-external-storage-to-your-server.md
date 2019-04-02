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

# 서버에 외부 스토리지 추가
{: #storage}

## 외부 스토리지 설정
{: #set_up_storage}

외부 스토리지를 백업 디바이스로 사용하려면 하나 이상의 프로비저닝된 서버에 외부 스토리지를 추가할 수 있습니다. 또는 테스트 환경에서는 스냅샷을 사용하여 데이터베이스를 빠르게 복원할 수 있습니다. 이 예에서는 데이터베이스의 로그 파일 아카이브와 데이터베이스의 온라인 및 오프라인 백업 모두에 블록 스토리지가 사용됩니다. 최소 백업 시간을 보장하는 데 도움이 되도록 최고속 블록 스토리지(GB당 10 IOPS)가 선택되었습니다. 요구사항에 따라 더 느린 블록 스토리지로도 충분할 수 있습니다. {{site.data.keyword.blockstoragefull}}에 대한 자세한 정보는 [블록 스토리지 시작하기](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted)를 참조하십시오.

1. 고유 인증 정보를 사용하여 [{{site.data.keyword.cloud_notm}} 인프라 고객 포털![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){: new_window}에 로그인하십시오.
2. **스토리지** > **블록 스토리지**를 선택하십시오.
3. 블록 스토리지 페이지의 오른쪽 상단 모서리에서 **블록 스토리지 주문**을 클릭하십시오.
4. 스토리지 요구사항에 맞는 세부 정보를 선택하십시오. 표 1에는 수요가 많은 데이터베이스 워크로드용 10 IOPS/GB를 포함하여 권장 값이 포함되어 있습니다.

|필드               |값                                        |
| -------------------------------- | ------------------------------------------------- |
|위치                          |DAL10                                             |
|비용 청구 방법                    |월별(기본값)                                 |
|새 스토리지 크기                  |1,000GB                                           |
|스토리지 IOPS 옵션              |내구성(계층 IOPS)(기본값)                 |
|내구성 계층 IOPS             | 10GB                                             |
|스냅샷 공간 크기               |0GB                                              |
|OS 유형                           | Windows 2008+                                     |
{: caption="표 1. 블록 스토리지에 대한 권장 값" caption-side="top"}

5. 두 개의 선택란을 클릭하고 **주문하기**를 클릭하십시오.

## 호스트 권한 부여
{: #authorize-host}

1. LUN의 오른쪽에 있는 **조치**를 클릭하고 프로비저닝된 스토리지에 액세스할 수 있도록 **호스트 권한 부여**를 선택하십시오.
2. **디바이스**를 선택하십시오. **디바이스 유형**은 기본적으로 베어메탈 서버로 설정됩니다. **하드웨어**를 클릭하고 데이터베이스 서버의 호스트 이름을 선택하십시오.
3. **제출**을 클릭하십시오.
4. **디바이스** > (디바이스 선택) > **스토리지** 탭 아래에서 프로비저닝된 스토리지의 상태를 확인하십시오.
5. 서버(iSCSI 이니시에이터)의 **대상 주소** 및 iSCSI 규정된 이름(IQN)과 iSCSI 서버에 인증하기 위한 **사용자 이름** 및 **비밀번호**를 기록해 두십시오. 이 정보는 블록 스토리지를 데이터베이스 서버에 연결하는 데 사용됩니다.

샘플 배치의 경우 스토리지 탭에서 검색된 데이터는 다음과 같습니다.
   * 대상 IP: `10.2.62.78`
   * IQN: `iqn.2005-05.com.softlayer:SL01SU276540-H896345`
   * 사용자: `SL01SU276540-H896345`
   * 비밀번호: `EtJ79F4RA33dXm2q`

[Microsoft Windows에서 MPIO iSCSCI LUN에 연결](/docs/infrastructure/BlockStorage?topic=BlockStorage-mountingWindows#mountingWindows)의 단계에 따라 위의 데이터를 사용하여 블록 스토리지를 데이터베이스 서버에 연결하십시오. 해당 단계를 주의하여 따르십시오. 이를 수행하면 Windows 서버에 사용 가능한 새 "오프라인" 디스크가 생성됩니다.

이제 디스크를 온라인 상태로 전환한 후 초기화할 수 있습니다.
