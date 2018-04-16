---



copyright:
  years: 2017, 2018
lastupdated: "2018-02-09"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# SAP 랜드스케이프 설치
{: #install_landscape}

## SAP 소프트웨어 다운로드
{: #download_software}

DVD를 다운로드하려면 SAP S-사용자 ID 및 다운로드 권한이 필요합니다. SAP S-사용자 ID에 대한 자세한 정보는 [S-사용자 ID를 설정하는 방법](https://www.sapappsdevelopmentpartnercenter.com/en/faq/program-faqs_2/how-to-receive-an-s-user-to-access-the-s_77)을 참조하십시오.

1. [SAP Service Marketplace](https://websmp201.sap-ag.de/)에 로그인하여 필수 DVD를 로컬 공유 드라이브에 다운로드하십시오. 2. 파일을 프로비저닝된 서버로 전송하십시오. 

다른 옵션은 [SAP Software Download Manager](https://support.sap.com/en/my-support/software-downloads.html#section_995042677)를 다운로드하여 대상 서버에 설치한 후 DVD 이미지를 직접 서버에 다운로드하는 것입니다. 

## SAP 소프트웨어 설치
{: #install_software}

설치 매체를 다운로드한 후 사용 중인 SAP 버전 및 컴포넌트에 대한 SAP 설치 안내서와 해당 SAP 노트에 문서화된 표준 SAP 설치 프로시저에 따르십시오. 자세한 정보는 [SAP 설치 안내서](https://service.sap.com/instguides) 및 [SAP 노트](https://support.sap.com)를 참조하십시오. 둘 다 SAP S-사용자 ID가 필요합니다.

1. 관리자로 SWPM-DVD 또는 설치 마스터 DVD의 루트 폴더를 열고 `sapinst`를 실행하십시오. SAP 설치 시작 페이지가 표시됩니다.
2. **SAP NetWeaver 7.5** > **Linux, UNIX 및 Windows용 IBM DB2** > **SAP 시스템** > **애플리케이션 서버 ABAP**를 선택하십시오.
3. **분산 시스템**을 열고 데이터베이스 서버에서 **ASCS 인스턴스** 및 **데이터베이스 인스턴스**를 실행하십시오.
4. 다음 단계가 작동하려면 ASCS 인스턴스가 설치된 후 `sapinst`가 `\\sapmnt` 및 `\\user\sap\trans` 폴더를 공유했는지 확인하십시오.
5. 애플리케이션 서버에서 **기본 애플리케이션 서버 인스턴스**를 실행하십시오. 애플리케이션 서버 설치 중에 데이터베이스 호스트 이름 및 ASCS의 개인용 주소를 사용해야 합니다. 이렇게 하면 애플리케이션 서버와 ASCS 또는 데이터베이스 간의 네트워크 트래픽이 공용 네트워크가 아니라 사설 네트워크를 통해 이동합니다.

이제 SAP 설치 지시사항에 따라 SAP 설치를 실행할 수 있습니다.

