---

copyright:
  years: 2015, 2018
lastupdated: "2018-8-17"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}   

# 도구 통합 구성
{: #integrations}

오픈 도구 체인을 작성하는 동안 사용자는 개발, 배치 및 운영 태스크를 지원하는 도구 통합을 구성할 수 있습니다. 또는 도구 통합을 추가하고 구성하여 기존 도구 체인을 사용자 정의할 수도 있습니다.  
{:shortdesc}

도구 체인에 대해 추가와 구성이 가능한 도구 통합은 사용자가 도구 체인을 {{site.data.keyword.Bluemix_notm}} 퍼블릭에서 사용 중인지 또는 {{site.data.keyword.Bluemix_notm}} 데디케이티드에서 사용 중인지 여부에 따라 다릅니다. {{site.data.keyword.Bluemix_notm}} 퍼블릭에서 도구 체인을 사용 중인 경우 사용 가능한 도구 통합은 도구 체인의 지역 및 해당 지역에서의 도구 통합의 가용성에 따라 달라집니다. {{site.data.keyword.Bluemix_notm}} 데디케이티드의 도구 체인을 사용 중인 경우 사용 가능한 도구 통합은 사용자의 특정 환경에 {{site.data.keyword.contdelivery_full}}가 설정되는 방법에 따라 달라집니다.

|도구 통합 |{{site.data.keyword.Bluemix_notm}} 퍼블릭에서 사용 가능	|{{site.data.keyword.Bluemix_notm}} 데디케이티드에서 사용 가능(환경에 따라 다름)|
|:----------|:------------------------------|:------------------|
|{{site.data.keyword.alertnotificationshort}}		|미국 남부		|아니오		|
|Artifactory		|미국 남부, 독일, 영국		|예		|
|Availability Monitoring		|미국 남부		|아니오		|
|Bitbucket		|미국 남부, 독일, 영국		|아니오		|
|Cloud Event Management		|미국 남부		|아니오		|
|{{site.data.keyword.deliverypipeline}} 		|미국 남부, 독일, 영국	   	|예  		|
|{{site.data.keyword.DRA_short}} 		|미국 남부		|아니오			|
|Eclipse Orion {{site.data.keyword.webide}}		|미국 남부, 독일, 영국		|예			|
|{{site.data.keyword.gitrepos}}	|미국 남부, 독일, 영국		|아니오		|
|GitHub		|미국 남부, 독일, 영국		|예		|
|Dedicated {{site.data.keyword.ghe_short}} and Issues			|아니오		|예		|
|GitLab		|미국 남부, 독일, 영국		|아니오		|
|Jenkins		|미국 남부, 독일, 영국		|예		|
|JIRA		|미국 남부, 독일, 영국		|예		|
|Nexus			|미국 남부, 독일, 영국		|예		|
|기타 도구			|미국 남부, 독일, 영국		|예		|
|PagerDuty			|미국 남부, 독일, 영국		|예		|
|Rational Team Concert			|미국 남부, 독일, 영국		|예		|
|Sauce Labs		|미국 남부, 독일, 영국		|아니오		|
|Slack			|미국 남부, 독일, 영국		|예		|
|SonarQube			|미국 남부, 독일, 영국		|예		|
{: caption="표 1. {{site.data.keyword.Bluemix_notm}} 퍼블릭 및 데디케이티드에서 도구 체인에 사용 가능한 도구 통합" caption-side="top"}

{{site.data.keyword.Bluemix_notm}} 퍼블릭에서 소스 코드로 개발을 시작하려는 경우, {{site.data.keyword.deliverypipeline}}을 구성하기 전에 GitHub 도구 통합 또는 {{site.data.keyword.gitrepos}} 도구 통합을 구성하십시오. {{site.data.keyword.Bluemix_notm}} 데디케이티드에서 코드로 개발을 시작하려는 경우, {{site.data.keyword.deliverypipeline}}을 구성하기 전에 {{site.data.keyword.ghe_short}} 도구 통합 또는 GitHub 도구 통합을 구성하십시오.
{: tip}


## Alert Notification 구성
{: #alertnotification}

{{site.data.keyword.alertnotificationfull}}는 알림 전략의 집중화 및 단순화에 사용할 수 있는 하이브리드 클라우드 기반 솔루션입니다. 이는 기타 클라우드 기반 및 온프레미스 애플리케이션에서 작동됩니다. 경보는 보안 RESTful API를 사용하여 {{site.data.keyword.alertnotificationshort}}에 전달됩니다.

DevOps 프로세스 중에 문제에 대한 알림을 수신하도록 {{site.data.keyword.alertnotificationshort}}을 구성하십시오.

### 전제조건

1. {{site.data.keyword.alertnotificationshort}} 계정이 없으면 하나를 등록하십시오.

 a. IBM Marketplace에서 [IBM {{site.data.keyword.alertnotificationshort}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/us-en/marketplace/alert-notification){: new_window} 페이지를 여십시오.

 b. 구독을 구입하거나 무료 90일 평가판을 등록하십시오.

1. {{site.data.keyword.alertnotificationshort}} 계정이 설정되면 [내 IBM 대시보드![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://myibm.ibm.com/dashboard/){: new_window}를 여십시오.
1. IBM {{site.data.keyword.alertnotificationshort}} 옆의 **실행**을 클릭하십시오.
1. **API 키 관리**를 클릭하고 **API 키 작성**을 클릭하십시오.
1. **API 키 작성** 필드에서 설명을 입력하십시오.
1. **생성**을 클릭하십시오. 이름과 비밀번호를 포함하여 새 API 키 정보가 표시됩니다. 도구 통합 구성에 해당 정보가 필요하므로 새 API 창을 계속 열어 두십시오. 보안을 목적으로 API 키 비밀번호를 나중에 검색할 수는 없습니다.

### Alert Notification 구성

1. 도구 체인을 작성하면서 이 도구 통합을 구성 중이면 구성 가능한 통합 섹션에서 **{{site.data.keyword.alertnotificationshort}}**을 클릭하십시오.
1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하십시오. 그런 다음 **개요**를 클릭하십시오.  

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **{{site.data.keyword.alertnotificationshort}}**을 클릭하십시오.

1. 사용할 {{site.data.keyword.alertnotificationshort}} API의 URL을 입력하십시오. {{site.data.keyword.alertnotificationshort}} 서비스의 API 키 관리 페이지에서 URL을 찾을 수 있습니다. 예: `https://ibmnotifybm.mybluemix.net/api/alerts/v1`.
1. {{site.data.keyword.alertnotificationshort}}에 대한 API 키의 이름을 입력하십시오. 새 API 키 창에서 API 키 이름을 찾을 수 있습니다.
1. API 키에 대해 {{site.data.keyword.alertnotificationshort}}에서 생성한 비밀번호를 입력하십시오. 새 API 키 창에서 API 키 비밀번호를 찾을 수 있습니다.
1. **통합 작성**을 클릭하십시오.
1. 도구 체인에서 **{{site.data.keyword.alertnotificationshort}}**을 클릭하십시오.

### Alert Notification에 대해 자세히 알아보기

{{site.data.keyword.alertnotificationshort}}에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [IBM {{site.data.keyword.alertnotificationshort}} 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/manage/tool_alert_notification/){: new_window}를 참조하거나 이 튜토리얼을 수행하십시오.

  * [Add a tool integration to a toolchain ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/add-a-tool-integration-to-a-toolchain){:new_window}

  * [Manage your {{site.data.keyword.Bluemix_notm}} application by using {{site.data.keyword.Bluemix_notm}} Availability Monitoring and Alert Notification ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/tutorial_gm_advocate_bam_and_an){:new_window}


## Artifactory 구성
{: #artifactory}

Artifactory 저장소(repo)에 빌드 아티팩트를 저장하도록 Artifactory 저장소 관리자를 구성합니다.

1. 도구 체인을 작성하면서 이 도구 통합을 구성 중이면 구성 가능한 통합 섹션에서 **Artifactory**를 클릭하십시오.
1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하십시오. 그런 다음 **개요**를 클릭하십시오.  

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **Artifactory**를 클릭하십시오.

1. Artifactory 카드를 클릭할 때 열릴 Artifactory 저장소의 URL을 입력하십시오.
1. 연결할 저장소 유형을 선택하십시오.
1. Artifactory npm 레지스트리를 사용 중이면 다음 단계를 따르십시오.

 a. 레지스트리와 연관된 이메일 주소를 입력하십시오.

 b. 레지스트리와 연관된 인증 토큰을 입력하십시오.

 c. Artifactory 서버의 개인용 레지스트리인 Artifactory 릴리스 저장소의 URL을 입력하십시오.

 d. 여러 공용 및 개인용 npm 레지스트리를 결합하는 데 사용되는 URL을 입력하십시오. 예를 들어, 이 URL은 개인용 레지스트리 및 npm 글로벌 레지스트리의 캐시 모두에 액세스할 수 있는 Artifactory 서버의 가상 레지스트리의 URL일 수 있습니다.

1. Artifactory Maven 저장소를 사용 중이면 다음 단계를 따르십시오.

 a. 저장소와 연관된 사용자 ID를 입력하십시오.

 b. 저장소와 연관된 비밀번호를 입력하십시오.

 c. Artifactory 서버의 개인용 릴리스 저장소인 Artifactory 릴리스 저장소의 URL을 입력하십시오.

 d. Artifactory 서버의 개인용 스냅샷 저장소인 Artifactory 스냅샷 저장소의 URL을 입력하십시오.

 e. 여러 공용 및 개인용 Maven 저장소를 결합하는 데 사용되는 미러 또는 공용 저장소의 URL을 입력하십시오. 예를 들어, 이 URL은 개인용 저장소 및 Maven 중앙 저장소의 캐시 모두에 액세스할 수 있는 Artifactory 서버의 가상 저장소의 URL일 수 있습니다.

1. **통합 작성**을 클릭하십시오.
1. 작업할 Artifactory 저장소의 카드를 클릭하십시오. 저장소의 컨텐츠를 볼 수 있는 Artifactory 웹 사이트가 열립니다.
1. 선택사항: {{site.data.keyword.Bluemix_notm}} 퍼블릭에서 도구 체인을 사용 중이며 npm에서 Artifactory를 사용하여 앱을 빌드하려면 npm 빌드 작업을 추가하도록 파이프라인을 구성하십시오. 빌드 작업 구성에 대한 지시사항은 [파이프라인에서 Artifactory npm 빌드 작업 구성](#config_artifactory_npm) 절을 참조하십시오.
1. 선택사항: {{site.data.keyword.Bluemix_notm}} 퍼블릭에서 도구 체인을 사용 중이며 Maven에서 Artifactory를 사용하여 앱을 빌드하려면 Maven 빌드 작업을 추가하도록 파이프라인을 구성하십시오. 빌드 작업 구성에 대한 지시사항은 [파이프라인에서 Artifactory Maven 빌드 작업 구성](#config_artifactory_maven) 절을 참조하십시오.

### 파이프라인에서 Artifactory npm 빌드 작업 구성
{: #config_artifactory_npm}

파이프라인에서 npm 빌드 작업을 구성하려면, 우선 입력으로서 빌드 SCM 저장소를 사용할 수 있는 작업 파이프라인이 있어야 하며 도구 체인의 Artifactory를 구성해야 합니다. Artifactory 구성에 대한 지시사항은 [Artifactory](#artifactory) 절을 참조하십시오.

npm 빌드 작업을 추가하도록 {{site.data.keyword.deliverypipeline}}을 구성하십시오.

1. 단계를 작성하고 적합한 SCM 저장소에 대한 입력을 설정하십시오.
1. 단계에서 빌드 작업을 추가하십시오.
1. 빌드 작업을 구성하십시오.
  ![npm 빌드 작업](images/artifactory_npm_job.png)

  a. 빌더 유형에 대해 **NPM 빌드**를 선택하십시오.

  b. Artifactory 도구 통합의 여러 인스턴스를 구성한 경우에는 npm 빌드 작업이 구성될 Artifactory 도구 통합의 이름을 입력하십시오.

  c. 도구 통합 유형에 대해 **Artifactory**를 선택하십시오.

  d. 빌드 명령에 대해 npm 모듈을 빌드하거나 이를 레지스트리에 공개하는 명령을 입력하십시오. 다음 예제는 모듈을 빌드하거나 이를 공개하는 명령을 보여줍니다.
     ```
     npm install
     # or
     npm publish --registry "${NPM_RELEASE_URL}"
     ```
  Artifactory 도구 통합을 위한 구성 설정의 레지스트리에 연결하는 데 사용된 URL 및 사용자 신임 정보를 찾을 수 있습니다.
  {: tip}

  e. 빌드 작업이 Artifactory 레지스트리에 공개되며 노드 모듈 버전의 형식이 `x.y.z-SNAPSHOT.w`인 경우에는 **스냅샷 모듈 버전 올리기** 선택란을 선택하십시오. 빌드 작업은 해당 작업이 Artifactory 레지스트리에 공개되기 전에 모듈 버전을 자동으로 업데이트합니다. 작업은 로컬 `package.json` 파일 및 npm 레지스트리에서 모듈의 최상위 버전을 선택하며 semver을 사용하여 모듈 버전을 올립니다. 빌드 작업은 변경사항을 SCM 저장소에 전달하지 않습니다.

1. **저장**을 클릭하십시오. 파이프라인이 실행될 때마다 이 빌드 작업은 Artifactory 도구 통합의 구성 정보를 사용하여 npm 레지스트리에 연결합니다.

### 파이프라인에서 Artifactory Maven 빌드 작업 구성
{: #config_artifactory_maven}

파이프라인에서 Maven 빌드 작업을 구성하려면, 우선 입력으로서 빌드 SCM 저장소를 사용할 수 있는 작업 파이프라인이 있어야 하며 도구 체인의 Artifactory를 구성해야 합니다. Artifactory 구성에 대한 지시사항은 [Artifactory](#artifactory) 절을 참조하십시오.

Maven 빌드 작업을 추가하도록 {{site.data.keyword.deliverypipeline}}을 구성하십시오.

1. 단계를 작성하고 적합한 SCM 저장소에 대한 입력을 설정하십시오.
1. 단계에서 빌드 작업을 추가하십시오.
1. 빌드 작업을 구성하십시오.
  ![Maven 빌드 작업](images/artifactory_maven_job.png)

  a. 빌더 유형에 대해 **Maven 빌드**를 선택하십시오.

  b. Artifactory 도구 통합의 여러 인스턴스를 구성한 경우에는 Maven 빌드 작업이 구성될 Artifactory 도구 통합의 이름을 입력하십시오.

  c. 도구 통합 유형에 대해 **Artifactory**를 선택하십시오.

  d. 빌드 명령에 대해 Maven 모듈을 빌드하거나 이를 스냅샷 레지스트리에 공개하는 명령을 입력하십시오. 다음 예제는 모듈을 빌드하거나 이를 스냅샷 레지스트리에 공개하는 명령을 보여줍니다.
     ```
     mvn -B clean package
     # or
     mvn -DaltDeploymentRepository="snapshots::default::${MAVEN_SNAPSHOT_URL}" deploy
     ```
  Artifactory 도구 통합을 위한 구성 설정의 레지스트리에 연결하는 데 사용된 URL 및 사용자 신임 정보를 찾을 수 있습니다.
  {: tip}

1. **저장**을 클릭하십시오. 파이프라인이 실행될 때마다 이 빌드 작업은 Artifactory 도구 통합의 구성 정보를 사용하여 Maven 저장소에 연결합니다.

### Artifactory에 대해 자세히 알아보기

Artifactory에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [Artifactory 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/deliver/tool_artifactory/){: new_window}를 참조하십시오.


## Availability Monitoring 추가
{: #availabilitymonitoring}

{{site.data.keyword.prf_hublong}}은 사용자에게 영향을 주기 전에 문제점을 분리하고 패턴을 식별하며 성능을 개선합니다. 사용자는 전세계의 위치에서 앱을 테스트하고 딜리버리 파이프라인과 통합하며 지속적인 코드 최적화 방법에 대한 통찰을 얻을 수 있습니다.

이 도구 통합은 사전 구성되어 있으며 구성 매개변수를 필요로 하지 않습니다. 이 도구 통합은 재구성할 수 없습니다.
{: tip}

빌드하면서 앱 상태를 테스트, 모니터하고 개선하려면 {{site.data.keyword.prf_hubshort}} 도구 통합을 추가하십시오.

1. DevOps 대시보드의 도구 체인 페이지에서 {{site.data.keyword.prf_hubshort}}가 추가될 도구 체인을 클릭하십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **{{site.data.keyword.prf_hubshort}}**을 클릭하십시오.

1. **통합 작성**을 클릭하십시오.
1. **{{site.data.keyword.prf_hubshort}}**을 클릭하여 {{site.data.keyword.prf_hubshort}} 대시보드를 열고 앱을 선택한 후에 앱에 대한 모니터링을 구성하십시오.

### Availability Monitoring에 대해 자세히 알아보기

{{site.data.keyword.prf_hubshort}}에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [{{site.data.keyword.prf_hublong}} 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/manage/tool_bluemix_availability_monitoring/){: new_window}를 참조하거나 이 튜토리얼을 수행하십시오.

  * [Manage your {{site.data.keyword.Bluemix_notm}} application by using {{site.data.keyword.Bluemix_notm}} Availability Monitoring and Alert Notification ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/tutorial_gm_advocate_bam_and_an){:new_window}


## Bitbucket 구성
{: #bitbucket}

bitbucket.org의 기존 또는 새 저장소에 소스 코드를 저장하고 위키, 문제 추적 및 가져오기 요청을 통해 소셜 코딩에 참여합니다.

팀과 코드에 대해 협업하도록 Bitbucket 구성:

1. DevOps 대시보드에서 **도구 체인**을 클릭하십시오. Bitbucket을 추가하려는 도구 체인을 클릭하십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **Bitbucket**을 클릭하십시오.

   {{site.data.keyword.Bluemix_notm}} 퍼블릭에 이 도구 통합을 구성 중이고 Bitbucket에 액세스하는 권한을 {{site.data.keyword.Bluemix_notm}}에 부여하지 않은 경우 **권한 부여**를 클릭하여 Bitbucket 웹 사이트로 이동하십시오. 활성 상태의 Bitbucket 세션이 없는 경우 로그인하도록 프롬프트가 표시됩니다. **액세스 부여**를 클릭하여 {{site.data.keyword.Bluemix_notm}} 도구 체인이 Bitbucket 계정의 다음 파트에 액세스하도록 하십시오.
   
   * **계정 정보 읽기**. 기본 사용자 정보를 가져와 사용자 인터페이스를 채웁니다.
   
   * **저장소 문제 읽기 및 수정**. {{site.data.keyword.contdelivery_short}}가 파이프라인이 문제에 연결된 커미트를 배치할 때 표시하기 위해 문제를 업데이트할 수 있게 합니다. 
   
   * **팀의 프로젝트 설정 읽기 및 팀 프로젝트 내에 포함된 저장소 읽기**. {{site.data.keyword.contdelivery_short}}가 팀이 소유한 저장소와 통합할 수 있게 합니다.
   
   * **저장소 및 가져오기 요청 읽기 및 수정**. 사용자가 코드를 요청할 때 {{site.data.keyword.contdelivery_short}}가 샘플 코드를 저장소에 푸시할 수 있게 합니다.
   
   * **저장소 관리**. 사용자 요쳥 시 {{site.data.keyword.contdelivery_short}}가 새 저장소를 작성할 수 있게 합니다.
   
   * **팀 멤버십 정보 읽기**. {{site.data.keyword.contdelivery_short}}가 새 저장소 작성 시 표시되는 **소유자** 메뉴에 팀 목록을 표시할 수 있게 합니다.
   
   * **저장소의 웹훅 읽기 및 수정**. 커미트가 저장소에 푸시될 때 파이프라인이 빌드를 트리거할 수 있게 합니다.
   {: tip}
   
   활성 Bitbucket 세션이 있지만 최근에 비밀번호를 입력하지 않은 경우, 확인을 위해 Bitbucket 비밀번호를 입력하도록 프롬프트가 표시될 수 있습니다.

1. 사용하려는 Bitbucket 서버를 클릭하십시오.
1. 사용하려는 Bitbucket 저장소가 있는 경우 해당 저장소의 URL을 입력하십시오. 저장소 유형으로 **기존**을 클릭하십시오.
1. 새 Bitbucket 저장소를 사용하려는 경우, 해당 저장소의 이름을 입력하고 복제 또는 분기 중인 저장소의 URL을 입력한 후 저장소 유형을 선택하십시오.

 a. 빈 저장소를 작성하려면 **새로 작성**을 클릭하십시오.

 b. 저장소의 사본을 작성하려면 **복제**를 클릭하십시오.

 c. 가져오기 요청을 통해 변경사항을 제공할 수 있도록 저장소를 분기하려면 **분기**를 클릭하십시오.

1. 서버에 개인용 저장소를 작성하려면 **이 저장소를 개인용으로 설정** 선택란을 선택하십시오.
1. Bitbucket Issues를 문제 추적에 대해 사용하려면 **Bitbucket Issues 사용** 선택란을 선택하십시오.
1. 커미트에 태그 및 주석을 작성하고 커미트에서 참조하는 이슈에 대한 레이블과 주석을 작성하여 코드 변경사항의 배치를 추적하려면, **코드 변경사항의 배치 추적** 선택란을 선택하십시오. 자세한 정보는 [Track where your code is deployed with toolchains![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}를 참조하십시오.
1. **통합 작성**을 클릭하십시오.
1. 도구 체인에서 작업하려는 Bitbucket 저장소에 대한 카드를 클릭하십시오. Bitbucket 웹 사이트가 열리며 저장소의 컨텐츠를 볼 수 있습니다.
1. Bitbucket Issues가 사용으로 설정된 경우 **Bitbucket Issues**를 클릭하여 여십시오. 도구 체인에 여러 Bitbucket 저장소가 포함되어 있는 경우에도 전체 도구 체인에 대해 Bitbucket Issues의 이 인스턴스를 사용할 수 있습니다.    

링크 중인 저장소에 대해 소유자 또는 마스터 권한이 없으면 웹훅을 사용할 수 없으므로 통합이 제한됩니다. 웹훅은 커미트가 저장소에 푸시될 때 파이프라인을 자동으로 실행하는 데 필요합니다. 웹훅이 없으면 파이프라인을 수동으로 시작해야 합니다.
{: tip}

### Bitbucket에 대해 자세히 알아보기

Bitbucket에 대해 자세히 알아보려면 IBM Cloud Garage Method의 [Bitbucket 기사 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/code/tool_bitbucket/){: new_window}를 참조하십시오.


## Cloud Event Management 추가
{: #cloudeventmanagement}

{{site.data.keyword.evtmgt_full}}는 서비스, 애플리케이션 및 인프라에서 발생하는 문제점의 통합 보기를 제공합니다. 보다 효율적으로 문제점을 해결할 수 있도록 실시간 사건 관리를 설정할 수 있습니다.

이 도구 통합은 사전 구성되어 있으며 구성 매개변수를 필요로 하지 않습니다. 이는 재구성할 수 없습니다.
{: tip}

DevOps 팀이 안정적 운영 상태, 서비스 품질 및 지속적 개선 목표를 달성하도록 도움을 주려면 도구 체인에 Cloud Event Management를 추가하십시오.

1. DevOps 대시보드에서 **도구 체인**을 클릭하십시오. Cloud Event Management를 추가할 도구 체인을 클릭하십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **Cloud Event Management**를 클릭하십시오.

1. **통합 작성**을 클릭하십시오.
1. 도구 체인에서 다음 도구 카드 중 하나를 클릭하십시오.

 * **Cloud Event Management** - Cloud Event Management를 시작하는 경우.

 * **{{site.data.keyword.alertnotificationshort}}** - 사용자가 사건 알림을 받는 시점을 판별하는 정책을 작성하는 경우.

 * **Runbook Automation** - Cloud Event Management에서 런북의 카탈로그를 관리하는 경우.

### Cloud Event Management에 대해 자세히 알아보기

Cloud Event Management에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [Cloud Event Management 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/manage/tool_cloud_event_mgt/){: new_window}를 참조하십시오.


## Delivery Pipeline 구성
{: #deliverypipeline}

{{site.data.keyword.deliverypipeline}}은 입력을 검색하고 작업(예: 빌드, 테스트 및 배치)을 실행하는 일련의 단계를 통해 프로젝트의 지속적 배치를 자동화합니다.

앱의 지속적 빌드, 테스트 및 배치를 자동화하도록 {{site.data.keyword.deliverypipeline}}을 구성하십시오.

1. 도구 체인을 작성하면서 이 도구 통합을 구성 중이면 구성 가능한 통합 섹션에서 **{{site.data.keyword.deliverypipeline}}**을 클릭하십시오. 사용하는 템플리트에 따라 사용 가능한 필드가 다를 수 있습니다. 기본 필드 값을 검토하고 필요한 경우 해당 설정을 변경하십시오.
1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **{{site.data.keyword.deliverypipeline}}**을 클릭하십시오.

1. 새 파이프라인의 이름을 지정하십시오.
1. 파이프라인을 사용하여 사용자 인터페이스를 배치하려는 경우 **앱 보기 메뉴에 앱 표시** 선택란을 선택하십시오. 파이프라인에서 작성하는 모든 앱이 도구 체인의 개요 페이지에 있는 **앱 보기** 목록에 표시됩니다.
1. **통합 작성**을 클릭하여 도구 체인에 {{site.data.keyword.deliverypipeline}}을 추가하십시오.
1. **{{site.data.keyword.deliverypipeline}}**을 클릭하여 파이프라인을 보고 이를 구성하십시오. 파이프라인 구성의 기본사항을 알아보려면 [파이프라인 빌드 및 배치](/docs/services/ContinuousDelivery/pipeline_build_deploy.html){: new_window}의 내용을 참조하십시오.

  커미트를 GitHub, {{site.data.keyword.ghe_short}} 또는 Git 저장소에 푸시할 때 파이프라인을 자동으로 실행하려면 다음 단계를 따르십시오.

   a. 파이프라인의 스테이지를 정의하기 전에 도구 체인에 대해 GitHub, {{site.data.keyword.ghe_short}} 또는 {{site.data.keyword.gitrepos}}를 구성하십시오. 파이프라인 단계에는 사용하는 저장소의 Git URL이 필요합니다. 각 파이프라인 단계는 도구 체인과 연관된 GitHub, {{site.data.keyword.ghe_short}} 또는 Git 저장소 중 하나만 참조할 수 있습니다. GitHub 구성에 대한 지시사항은 [GitHub](#github) 섹션을 참조하십시오. 데디케이티드 {{site.data.keyword.ghe_short}} 구성에 대한 지시사항은 [{{site.data.keyword.ghe_long}} 시작하기](/docs/services/ghededicated/index.html){: new_window}를 참조하십시오. {{site.data.keyword.gitrepos}} 구성에 대한 지시사항은 [{{site.data.keyword.gitrepos}}](#gitbluemix) 섹션을 참조하십시오.

   b. 웹훅을 사용하십시오. 웹훅이 없으면 파이프라인을 수동으로만 실행할 수 있습니다. GitHub 또는 {{site.data.keyword.ghe_short}} 저장소에 연결할 때 웹훅을 사용하려면, 관리 권한이 필요합니다. {{site.data.keyword.gitrepos}} 저장소에 연결하려면 마스터 또는 소유자 권한이 있어야 합니다.

1. 선택사항: {{site.data.keyword.Bluemix_notm}} 퍼블릭에서 도구 체인을 사용 중이고 Sauce Labs에서 앱에 대한 테스트를 실행하도록 하려면 Sauce Labs 테스트 작업을 추가하도록 {{site.data.keyword.deliverypipeline}}을 구성하십시오. 테스트 작업을 구성하는 데 관한 지시사항은 [파이프라인에서 Sauce Labs 테스트 작업 구성](#config_saucelabs) 절을 참조하십시오.

### 파이프라인에서 Sauce Labs 테스트 작업 구성
{: #config_saucelabs}

파이프라인에서 Sauce Labs 테스트 작업을 구성하기 전, 앱을 빌드하고 배치하는 단계가 포함된 정상으로 작동하는 파이프라인이 필요하며 사용하는 도구 체인에 적합하게 Sauce Labs를 구성해야 합니다. Sauce Labs를 구성하는 데 관한 지시사항은 [Sauce Labs](#saucelabs) 절을 참조하십시오.

Sauce Labs 테스트 작업을 추가하도록 {{site.data.keyword.deliverypipeline}}을 구성하십시오.

1. 앱의 테스트 버전을 배치하는 단계가 없으면 하나를 작성하십시오.
1. 단계에서 배치 작업 뒤에 테스트 작업을 추가하십시오. 동일한 단계에 이러한 작업을 배치하면 해당 작업이 동일한 환경 특성 세트에 액세스할 수 있습니다.   
  ![테스트 작업](images/toolchain_test_job.png)

1. 단계를 구성하십시오. **ENVIRONMENT PROPERTIES** 탭에서 CF_APP_NAME 특성을 작성하십시오.

  SAUCE_USERNAME 및 SAUCE_ACCESS_KEY 환경 변수로 테스트 작업 스크립트에서 Sauce Labs 사용자 이름 및 액세스 키를 사용할 수 있습니다. 테스트를 작성하는 경우 Sauce Labs로 인증하는 데 환경 변수를 사용해야 합니다.
  {: tip}

1. 배치 작업을 구성하십시오. **배치 스크립트** 필드에 다음 명령을 포함시키십시오. `export CF_APP_NAME="$CF_APP"`. 이 명령은 앱 이름을 환경 특성으로서 내보냅니다.
1. 테스트 작업을 구성하십시오. 다음 이미지의 값은 예입니다. **서비스 인스턴스**, **대상**, **조직** 및 **영역** 필드는 사용 중인 Sauce Labs 사용자 이름, 지역, 조직 및 영역으로 채워집니다.  
![작업 구성](images/toolchain_configure_job.png)

  a. 테스터 유형으로 **Sauce Labs**를 선택하십시오.

  b. 서비스 인스턴스에 대해, 도구 체인에 Sauce Labs를 구성할 때 사용한 Sauce Labs 사용자 이름을 선택하십시오.

   도구 체인에 Sauce Labs를 구성할 때 사용한 사용자 이름 및 액세스 키를 보려면 **구성**을 클릭하십시오.
   {: tip}

  c. **테스트 실행 명령** 필드에 테스트에 필요한 종속 항목을 설치하는 명령을 입력한 후 테스트를 실행하십시오. 예를 들어, Node.js 앱의 경우 다음 명령을 입력할 수 있습니다.
     ```
     npm install
     node_modules/grunt-cli/bin/grunt test:sauce:parallel
     ```

    d. 테스트 작업 로그에서 테스트 보고서를 보려는 경우, **테스트 보고서 사용** 선택란을 선택하고 테스트 결과 파일 패턴을 `test/*.xml`로 설정하십시오.

1. **저장**을 클릭하십시오. 파이프라인을 실행할 때마다 Sauce Labs 테스트가 실행됩니다.

### Delivery Pipeline에 대해 자세히 알아보기

{{site.data.keyword.deliverypipeline}}에 대해 자세히 알아보려면 [파이프라인에 대한 작업](/docs/services/ContinuousDelivery/pipeline_working.html){: new_window} 및 IBM Cloud Garage Method의 [Delivery Pipeline 기사 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/deliver/tool_delivery_pipeline/){: new_window}를 참조하거나 다음 튜토리얼을 활용하십시오.

  * [파이프라인 작성 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/create-a-pipeline){:new_window}

  * ["Cloud Foundry 앱 개발" 도구 체인을 사용하여 첫 번째 도구 체인 작성 및 사용 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/introduce-develop-cloud-foundry-app-toolchain){:new_window}


## DevOps Insights 추가(베타)
{: #dra}

{{site.data.keyword.DRA_full}}는 단위 테스트, 기능 테스트 및 코드 검사 도구로부터의 결과를 수집하고 분석하여 코드가 배치 프로세스의 지정된 게이트에서 사전 정의된 기준을 충족하는지 여부를 판별합니다. 코드가 기준을 충족하지 않거나 기준을 초과하면 위험이 표출되지 않도록 배치가 중지됩니다. {{site.data.keyword.DRA_short}}를 Continuous Delivery 환경의 안전망으로서 또는 품질 표준을 구현하고 향상시키는 방법으로서 사용할 수 있습니다.

 이 도구 통합은 {{site.data.keyword.Bluemix_notm}} 퍼블릭에서만 사용 가능합니다. 이는 사전 구성되어 있으며 구성 매개변수를 필요로 하지 않습니다. 이 도구 통합은 재구성할 수 없습니다.
 {: tip}

{{site.data.keyword.DRA_short}}를 추가하여 배치를 모니터하고 위험이 표출되기 전에 위험을 식별함으로써 {{site.data.keyword.Bluemix_notm}}의 코드 품질을 유지하고 향상시킬 수 있습니다.

1. 도구 체인을 작성하면서 이 도구 통합을 구성 중이면 구성 가능한 통합 섹션에서 **{{site.data.keyword.DRA_short}}**을 클릭하십시오.
1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **{{site.data.keyword.DRA_short}}**을 클릭하십시오.

1. **통합 작성**을 클릭하십시오.
1. **{{site.data.keyword.DRA_short}}**를 클릭한 후에 시작하기 단계를 완료하십시오. 기준을 작성하고 파이프라인에 기준을 연결한 후에 파이프라인을 실행하십시오.

### DevOps Insights에 대해 자세히 알아보기

{{site.data.keyword.DRA_short}}에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [{{site.data.keyword.DRA_short}} 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/learn/tool_devops_insights/){: new_window}를 참조하거나 이 튜토리얼을 수행하십시오.

  * ["Cloud Foundry 앱 개발 및 테스트" 도구 체인 사용 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-cloud-foundry-app-toolchain){:new_window}

  * ["Cloud Foundry에서 마이크로서비스 개발 및 테스트" 도구 체인 사용 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}

  * ["GitHub 및 Jenkins를 사용하는 Deployment Risk Analytics" 도구 체인을 사용하여 품질 배치 보장 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/ensure-quality-deployment-risk-analytics-with-github-and-jenkins-toolchain){:new_window}


## Eclipse Orion Web IDE 추가
{: #webide}

Eclipse Orion {{site.data.keyword.webide}}는 소스 제어 태스크를 작성, 편집, 실행, 디버그 및 완료할 수 있는 통합된 웹 기반 환경입니다. 편집에서 실행, 제출 및 배치까지 원활하게 이동할 수 있습니다.

 이 도구 통합은 사전 구성됩니다. 구성 매개변수가 필요 없으며 재구성할 수 없습니다.
 {: tip}

소스 제어 태스크를 완료하려면 Eclipse Orion {{site.data.keyword.webide}} 도구 통합을 추가하십시오.

1. 도구 체인을 작성할 때 이 도구 통합을 구성하는 경우, 구성 가능한 통합 섹션에서 **Eclipse Orion {{site.data.keyword.webide}}**를 클릭하십시오.
1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **Eclipse Orion {{site.data.keyword.webide}}**를 클릭하십시오.

1. **통합 작성**을 클릭하십시오.
1. **Eclipse Orion {{site.data.keyword.webide}}**를 클릭하십시오. 작업공간이 GitHub 또는 {{site.data.keyword.ghe_short}} 저장소로 미리 채워집니다. 현재 도구 체인과 연관된 저장소가 강조표시됩니다.

### Eclipse Orion Web IDE에 대해 자세히 알아보기

Eclipse Orion {{site.data.keyword.webide}}에 대해 자세히 알아보려면, [Eclipse Orion {{site.data.keyword.webide}}로 코드 편집](/docs/services/ContinuousDelivery/web_ide.html){: new_window} 및 IBM Cloud Garage Method에서 [Eclipse Orion {{site.data.keyword.webide}} 기사 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/code/tool_eclipse_orion_web_ide/){: new_window}를 참조하거나 다음 튜토리얼을 활용하십시오.

  * ["Cloud Foundry 앱 개발" 도구 체인을 사용하여 첫 번째 도구 체인 작성 및 사용 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/introduce-develop-cloud-foundry-app-toolchain){:new_window}

  * ["Cloud Foundry에서 마이크로서비스 개발 및 테스트" 도구 체인 사용 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}


## Git Repos and Issue Tracking 구성
{: #gitbluemix}

{{site.data.keyword.gitrepos}} 도구 통합은 Git 저장소의 웹 기반 호스팅 서비스인 GitLab Community Edition을 기반으로 합니다. 사용자는 저장소의 로컬 및 원격 사본 모두를 보유할 수 있습니다. 자세히 알아보려면 [{{site.data.keyword.gitrepos}}![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://git.ng.bluemix.net/help){:new_window}을 참조하십시오.

도구 체인을 작성할 때 {{site.data.keyword.gitrepos}}을 구성하는 경우 다음 단계를 따르십시오.    

1. 구성 가능한 통합 섹션에서 **Git Repos and Issue Tracking**을 클릭하십시오.
1. Git 저장소의 기본 대상 위치를 검토하십시오. 해당 저장소는 샘플 저장소에서 복제됩니다. 필요한 경우 대상 저장소의 이름을 변경하십시오.

도구 체인이 있으며 도구 체인의 Git 저장소를 {{site.data.keyword.gitrepos}}에 마이그레이션하려면 다음 단계를 따르십시오.

이 지시사항은 {{site.data.keyword.gitrepos}}에 마이그레이션할 Git 저장소에 이미 포함된 도구 체인에 적용됩니다. 도구 체인에 다른 유형의 Git 저장소 추가에 대한 자세한 정보는 [GitHub 구성](#github), [{{site.data.keyword.Bluemix_notm}} 데디케이티드에서 GitHub Enterprise 및 Issues 구성](#configghe) 및 [GitLab 구성](#gitlab) 섹션을 참조하십시오.
{: tip}

1. DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.
1. **도구 추가**를 클릭하십시오.
1. 도구 통합 섹션에서 **Git Repos and Issue Tracking**을 클릭하십시오.
1. Git 저장소의 사본을 작성하려면 저장소 유형에 대해 **복제**를 클릭하십시오. 새 저장소 이름 및 소스 저장소의 URL을 입력하십시오.
1. 문제 추적을 위해 Issues를 사용하려면 **Issues 사용** 선택란을 선택하십시오.
1. 커미트의 태그와 주석 및 커미트에서 참조하는 문제의 레이블과 주석을 작성하여 코드 변경사항의 배치를 추적하려면 **코드 변경사항의 배치 추적** 선택란을 선택하십시오. 자세한 정보는 [Track where your code is deployed with toolchains![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}를 참조하십시오.
1. **통합 작성**을 클릭하십시오.

Git 저장소를 복제한 후 도구 체인에서 이를 제거할 수 있습니다.
{: tip}

도구 체인이 있고 여기에 {{site.data.keyword.gitrepos}}을 추가하는 경우 다음 단계를 따르십시오.    

1. DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.
1. **도구 추가**를 클릭하십시오.
1. 도구 통합 섹션에서 **Git Repos and Issue Tracking**을 클릭하십시오.
1. 저장소 유형을 선택하십시오.     

  a. 비어 있는 저장소를 작성하려면 저장소 유형에 대해 **새로 작성**을 클릭하고 저장소 이름을 입력하십시오.    
  b. 병합 요청을 통해 변경사항을 제공할 수 있도록 Git 저장소를 분기하려면 저장소 유형에 대해 **분기**를 클릭하십시오. 소스 저장소의 URL을 입력하십시오.    
  c. Git 저장소의 사본을 작성하려면 저장소 유형에 대해 **복제**를 클릭하십시오. 새 저장소 이름 및 소스 저장소의 URL을 입력하십시오.     
  d. Git 저장소가 있으며 이를 사용하려면 저장소 유형에 대해 **기존**을 클릭하십시오. URL을 입력하십시오.    

1. 문제 추적을 위해 Issues를 사용하려면 **Issues 사용** 선택란을 선택하십시오.
1. 커미트의 태그와 주석 및 커미트에서 참조하는 문제의 레이블과 주석을 작성하여 코드 변경사항의 배치를 추적하려면 **코드 변경사항의 배치 추적** 선택란을 선택하십시오. 자세한 정보는 [Track where your code is deployed with toolchains![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}를 참조하십시오.
1. **통합 작성**을 클릭하십시오.
1. 작업할 Git 저장소의 카드를 클릭하십시오. 프로젝트 개요 페이지가 열립니다.    

링크 중인 저장소에 대해 소유자 또는 마스터 권한이 없으면 웹훅을 사용할 수 없으므로 통합이 제한됩니다. 웹훅은 커미트가 저장소에 푸시될 때 파이프라인을 자동으로 실행하는 데 필요합니다. 웹훅이 없으면 파이프라인을 수동으로 시작해야 합니다.
{: tip}

### Git Repos and Issue Tracking에 대해 자세히 알아보기

{{site.data.keyword.gitrepos}}에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [{{site.data.keyword.gitrepos}}: Social coding hosted by IBM 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/code/tool_git_repos_and_issue_tracking/){: new_window}를 참조하거나 이 튜토리얼을 수행하십시오.

  * ["Cloud Foundry 앱 개발" 도구 체인을 사용하여 첫 번째 도구 체인 작성 및 사용 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/introduce-develop-cloud-foundry-app-toolchain){:new_window}


## GitHub 구성
{: #github}

GitHub는 Git 저장소의 웹 기반 호스팅 서비스입니다. 쉽게 협업할 수 있도록 저장소의 로컬 및 원격 사본을 모두 보유할 수 있습니다.

{{site.data.keyword.ghe_short}}는 Git 저장소를 위한 온프레미스 웹 기반 호스팅 서비스입니다.

GitHub Issues는 작업과 플랜을 모두 한 위치에 보관하는 추적 도구입니다. 개발 저장소에 통합되므로 중요한 태스크에 집중할 수 있습니다.

GitHub.com의 새 저장소 또는 기존 저장소에서 소스 코드를 관리하거나 회사의 {{site.data.keyword.ghe_short}} 인스턴스에서 소스 코드를 관리할 수 있도록 GitHub를 도구 체인의 도구 통합으로 구성할 수 있습니다. 위키, 문제 추적 및 가져오기 요청을 통해 소셜 코딩에 참여하십시오.

도구 체인을 작성할 때 이 도구 통합을 구성하는 경우 다음 단계를 따르십시오.

1. GitHub 저장소에 소스 코드를 저장 중인 경우 구성 가능한 통합 섹션에서 **GitHub**를 클릭하십시오. {{site.data.keyword.Bluemix_notm}} 퍼블릭에 이 도구 통합을 구성 중이고 GitHub에 액세스하는 권한을 {{site.data.keyword.Bluemix_notm}}에 부여하지 않은 경우 **권한 부여**를 클릭하여 GitHub 웹 사이트로 이동하십시오. 활성 GitHub 세션이 없으면 로그인을 요구하는 프롬프트가 표시됩니다. **애플리케이션에 권한 부여**를 클릭하여 {{site.data.keyword.Bluemix_notm}}에서 사용자의 GitHub 계정에 액세스할 수 있도록 허용하십시오. 활성 GitHub 세션이 있지만 최근에 비밀번호를 입력하지 않은 경우 확인을 위해 GitHub 비밀번호 입력을 요구하는 프롬프트가 표시될 수 있습니다.
1. 자체 {{site.data.keyword.ghe_short}} 서버의 저장소를 사용 중인 경우 구성 가능한 통합 섹션에서 **사용자 정의 서버 추가**를 클릭하십시오.

 {{site.data.keyword.Bluemix_notm}} 데디케이티드 환경에서 대상 Git 서버로 네트워크 액세스가 설정되어 있어야 합니다. 공용 인터넷에서 GitHub 서버를 사용할 수 없거나 호스트 이름을 공용 DNS(Domain Name Server)에서 해석할 수 없는 경우 [지원 티켓을 개설하십시오](/docs/services/ContinuousDelivery/cd_support.html#support-ticket){: new_window}. 지원 티켓을 사용하여 네트워크 라우트를 열거나 DNS 설정을 업데이트하도록 요청을 제출할 수 있습니다.
 {: tip}

 사용자 정의 GitHub 서버의 제목을 입력하고 서버의 루트 URL을 지정하십시오. 개인 액세스 토큰을 입력한 후 **사용자 정의 통합 저장**을 클릭하십시오.

  개인 액세스 토큰이 없으면 작성할 수 있습니다.

     a. GitHub 페이지에서 프로파일 아이콘을 클릭한 후 **설정**을 클릭하십시오.

     b. 사이드바에서 **개인 액세스 토큰**을 클릭하십시오.

     c. **새 토큰 생성**을 클릭하십시오.

     d. 토큰에 대한 설명을 추가하십시오.

     e. 개인 토큰에 대한 액세스 권한을 정의하려면 **저장소** 및 **사용자** 선택란을 선택하십시오.

     f. **토큰 생성**을 클릭하십시오.

     g. 토큰을 보안이 유지되는 위치 또는 비밀번호 관리 앱에 복사하십시오. 보안상의 이유로, 이 페이지를 나가면 더 이상 토큰을 볼 수 없습니다.

1. GitHub 저장소의 기본 대상 저장소 위치를 검토하십시오. 해당 저장소는 샘플 저장소에서 복제됩니다. 필요한 경우 대상 저장소의 이름을 변경하십시오.
 ![기본 대상 저장소 위치](images/toolchain_github_config.png)

도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 다음 단계를 따르십시오.

1. DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.
1. **도구 추가**를 클릭하십시오.
1. 도구 통합 섹션에서 **GitHub**를 클릭하십시오.
1. 사용할 GitHub 서버를 클릭하십시오.
1. GitHub 또는 {{site.data.keyword.ghe_short}} 저장소가 있으며 이를 사용하려면 저장소 유형에 대해 **기존**을 클릭하고 URL을 입력하십시오.
1. 새 GitHub 또는 {{site.data.keyword.ghe_short}} 저장소를 사용하려는 경우, 해당 저장소의 이름을 입력하고 복제하거나 분기시킬 저장소의 URL을 입력하며 저장소 유형을 선택하십시오.

 a. 빈 저장소를 작성하려면 **새로 작성**을 클릭하십시오.

 b. GitHub 또는 {{site.data.keyword.ghe_short}} 저장소의 사본을 작성하려면 **복제**를 클릭하십시오.

 c. 가져오기 요청을 통해 변경사항을 제공할 수 있도록 GitHub 또는 {{site.data.keyword.ghe_short}} 저장소를 분기하려면 **분기**를 클릭하십시오.

1. 업그레이드된 계정이 사용된 GitHub.com 사용자이거나, {{site.data.keyword.ghe_short}} 서버를 선택하고 서버에 새 개인용 저장소를 생성하려는 경우 **이 저장소를 개인용으로 설정** 선택란을 선택하십시오.
1. 문제 추적에 GitHub Issues를 사용하려면 **GitHub Issues 사용** 선택란을 선택하십시오.
1. 커미트의 태그와 주석 및 커미트에서 참조하는 문제의 레이블과 주석을 작성하여 코드 변경사항의 배치를 추적하려면 **코드 변경사항의 배치 추적** 선택란을 선택하십시오. 자세한 정보는 [Track where your code is deployed with toolchains![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}를 참조하십시오.
1. **통합 작성**을 클릭하십시오.
1. 작업할 GitHub 또는 {{site.data.keyword.ghe_short}} 저장소의 카드를 클릭하십시오. 선택한 저장소에 따라 저장소의 컨텐츠를 볼 수 있는 GitHub 웹 사이트 또는 회사의 {{site.data.keyword.ghe_short}} 저장소가 열립니다.

  Eclipse Orion {{site.data.keyword.webide}}의 통합된 소스 코드 관리 도구를 사용하여 GitHub 저장소를 편집하고 작업공간에서 앱을 배치할 수 있습니다.
  {: tip}

1. GitHub Issues를 사용한 경우에는 **GitHub Issues**를 클릭하여 이를 여십시오. 도구 체인에 여러 개의 GitHub 또는 {{site.data.keyword.ghe_short}} 저장소가 포함되어 있어도 전체 도구 체인에 대해 GitHub Issues의 이 인스턴스를 사용할 수 있습니다.    

링크 중인 저장소에 대해 관리자 권한이 없으면 웹훅을 사용할 수 없으므로 통합이 제한됩니다. 웹훅은 커미트가 저장소에 푸시될 때 파이프라인을 자동으로 실행하는 데 필요합니다. 웹훅이 없으면 파이프라인을 수동으로 시작해야 합니다.
{: tip}

### GitHub에 대해 자세히 알아보기

GitHub에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [GitHub 기사 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/code/tool_github/){: new_window} 및 [GitHub Issues 기사 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/think/tool_github_issues/){: new_window}를 참조하거나 다음 튜토리얼을 활용하십시오.

 * ["Cloud Foundry 앱 개발 및 테스트" 도구 체인 사용 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-cloud-foundry-app-toolchain){:new_window}

  * ["GitHub 및 Jenkins를 사용하는 Deployment Risk Analytics" 도구 체인을 사용하여 품질 배치 보장 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/ensure-quality-deployment-risk-analytics-with-github-and-jenkins-toolchain){:new_window}

  * [Create a custom toolchain ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/create-a-custom-toolchain){:new_window}


## {{site.data.keyword.Bluemix_notm}} 데디케이티드에서 GitHub Enterprise 및 Issues 구성
{: #configghe}

 다음 지시사항은 {{site.data.keyword.ghe_short}}용 {{site.data.keyword.Bluemix_notm}} 데디케이티드에 적용됩니다. {{site.data.keyword.ghe_short}}의 자체 관리 버전을 사용 중이면 일부 단계가 내부 프로시저에 따라 다를 수 있습니다.
 {: tip}

{{site.data.keyword.ghe_long}}는 Git 저장소를 위한 온프레미스 웹 기반 호스팅 서비스입니다. 데디케이티드 {{site.data.keyword.ghe_short}}는 {{site.data.keyword.Bluemix_notm}} 데디케이티드 고객 전용입니다. GitHub Issues는 작업과 플랜을 한 위치에 보관하는 추적 도구입니다. 개발 저장소에 통합되므로 중요한 태스크에 집중할 수 있습니다. 전용 {{site.data.keyword.ghe_short}} 및 GitHub Issues에 대한 자세한 정보는 [{{site.data.keyword.ghe_long}} 시작하기](/docs/services/ghededicated/index.html){: new_window} 및 IBM Cloud Garage Method에서 [GitHub Issues 기사 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/think/tool_github_issues/){: new_window}를 참조하십시오.

회사의 [{{site.data.keyword.Bluemix_notm}} 데디케이티드](/docs/dedicated/index.html#dedicated){: new_window} 인스턴스에서 소스 코드를 관리할 수 있도록 {{site.data.keyword.ghe_short}}를 도구 체인의 도구 통합으로 구성할 수 있습니다.

1. 도구 체인을 작성할 때 이 도구 통합을 구성하는 경우 다음 단계를 따르십시오.

 a. 데디케이티드 {{site.data.keyword.ghe_short}}에 처음으로 로그인하기 전에, LDAP을 사용하여 회사 사용자 레지스트리의 {{site.data.keyword.Bluemix_notm}} 데디케이티드 인스턴스에 사용자 ID를 추가하도록 회사의 지역 관리자에게 요청하십시오. {{site.data.keyword.ghe_short}} 계정 설정에 대한 정보는 [{{site.data.keyword.ghe_long}} 시작하기](/docs/services/ghededicated/index.html){: new_window}의 내용을 참조하십시오.

 b. 구성 가능한 통합 섹션에서 **{{site.data.keyword.ghe_short}}**을 클릭하십시오.    

 c. 새 {{site.data.keyword.ghe_short}} 저장소의 기본 이름을 검토하십시오. 필요한 경우 새 저장소의 이름을 변경하십시오. 다음 이미지는 샘플 저장소에서 복제된 저장소의 예를 보여줍니다. 기존 저장소 또는 새 저장소를 사용할 수 있습니다. 새 저장소를 사용하려면 비어 있는 저장소를 작성하거나 저장소를 복제하거나 또는 저장소를 분기시킬 수 있습니다.
 ![기본 저장소 위치](images/toolchain_ghe_config.png)

1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **{{site.data.keyword.ghe_short}}**를 클릭하십시오.

1. 사용할 {{site.data.keyword.ghe_short}} 저장소가 있는 경우 해당 저장소의 URL을 입력하십시오. 저장소 유형으로 **기존**을 클릭하십시오.
1. 새 {{site.data.keyword.ghe_short}} 저장소를 사용하려는 경우, 해당 저장소의 이름을 입력하고 복제하거나 분기시킬 저장소의 URL을 입력하며 저장소 유형을 선택하십시오.

 a. 빈 저장소를 작성하려면 **새로 작성**을 클릭하십시오.

 b. 저장소의 사본을 작성하려면 **복제**를 클릭하십시오.

 c. 가져오기 요청을 통해 변경사항을 제공할 수 있도록 저장소를 분기하려면 **분기**를 클릭하십시오.

1. 문제 추적에 GitHub Issues를 사용하려면 **GitHub Issues 사용** 선택란을 선택하십시오.
1. **통합 작성**을 클릭하십시오.
1. 작업할 {{site.data.keyword.ghe_short}} 저장소의 카드를 클릭하십시오. 회사의 {{site.data.keyword.ghe_short}} 저장소가 열립니다.

  Eclipse Orion {{site.data.keyword.webide}}의 통합된 소스 코드 관리 도구를 사용하여 {{site.data.keyword.ghe_short}} 저장소를 편집하고 작업공간에서 앱을 배치할 수 있습니다.
  {: tip}

1. GitHub Issues를 사용한 경우에는 **GitHub Issues**를 클릭하십시오. 도구 체인에 여러 개의 GitHub 저장소가 포함되어 있어도 전체 도구 체인에 대해 GitHub Issues의 이 인스턴스를 사용할 수 있습니다.    

링크 중인 저장소에 대해 관리자 권한이 없으면 웹훅을 사용할 수 없으므로 통합이 제한됩니다. 웹훅은 커미트가 저장소에 푸시될 때 파이프라인을 자동으로 실행하는 데 필요합니다. 웹훅이 없으면 파이프라인을 수동으로 시작해야 합니다.
{: tip}


## GitLab 구성
{: #gitlab}

GitLab은 Git 저장소의 웹 기반 호스팅 서비스입니다. 쉽게 협업할 수 있도록 저장소의 로컬 및 원격 사본을 모두 보유할 수 있습니다.

GitLab.com의 새 저장소 또는 기존 저장소에서 소스 코드를 관리하거나 회사의 GitLab 인스턴스에서 소스 코드를 관리할 수 있도록 GitLab을 도구 체인의 도구 통합으로 구성할 수 있습니다. 위키, 문제 추적 및 병합 요청을 통해 소셜 코딩에 참여하십시오.

도구 체인을 작성할 때 이 도구 통합을 구성하는 경우 다음 단계를 따르십시오.

1. GitLab 저장소에 소스 코드를 저장 중인 경우 구성 가능한 통합 섹션에서 **GitLab**을 클릭하십시오. {{site.data.keyword.Bluemix_notm}} 퍼블릭에 이 도구 통합을 구성 중이고 GitLab에 액세스하는 권한을 {{site.data.keyword.Bluemix_notm}}에 부여하지 않은 경우 **권한 부여**를 클릭하여 GitLab 웹 사이트로 이동하십시오. 활성 GitLab 세션이 없으면 로그인을 요구하는 프롬프트가 표시됩니다. **애플리케이션에 권한 부여**를 클릭하여 {{site.data.keyword.Bluemix_notm}}에서 사용자의 GitLab 계정에 액세스할 수 있도록 허용하십시오. 활성 GitLab 세션이 있지만 최근에 비밀번호를 입력하지 않은 경우 확인을 위해 GitLab 비밀번호 입력을 요구하는 프롬프트가 표시될 수 있습니다.
1. 자체 GitLab 서버의 저장소를 사용 중인 경우 구성 가능한 통합 섹션에서 **사용자 정의 서버 추가**를 클릭하십시오.

 {{site.data.keyword.Bluemix_notm}} 데디케이티드 환경에서 대상 GitLab 서버로 네트워크 액세스가 설정되어 있어야 합니다.
 {: tip}

 사용자 정의 GitLab 서버의 제목을 입력하고 서버의 루트 URL을 지정하십시오. 개인 액세스 토큰을 입력한 후 **사용자 정의 통합 저장**을 클릭하십시오.

  개인 액세스 토큰이 없으면 작성할 수 있습니다.

     a. GitLab 페이지에서 프로파일 아이콘을 클릭한 후 **설정**을 클릭하십시오.

     b. 액세스 토큰 페이지에서 액세스 토큰을 작성하려는 애플리케이션의 이름을 입력하십시오.

     c. 선택사항. 액세스 토큰의 만료 날짜를 선택하십시오.

     d. 개인 토큰에 대한 액세스 권한을 정의하려면 **api** 선택란을 선택하십시오.

     e. **개인 액세스 토큰 작성**을 클릭하십시오.

     f. 토큰을 보안이 유지되는 위치 또는 비밀번호 관리 앱에 복사하십시오. 보안상의 이유로, 이 페이지를 나가면 더 이상 토큰을 볼 수 없습니다.

1. GitLab 저장소의 기본 대상 저장소 위치를 검토하십시오. 해당 저장소는 샘플 저장소에서 복제됩니다. 필요한 경우 대상 저장소의 이름을 변경하십시오.

도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 다음 단계를 따르십시오.

1. DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.
1. **도구 추가**를 클릭하십시오.
1. 도구 통합 섹션에서 **GitLab**을 클릭하십시오.
1. 사용할 GitLab 서버를 클릭하십시오.
1. GitLab 저장소가 있으며 이를 사용하려면 저장소 유형에 대해 **기존**을 클릭하고 URL을 입력하십시오.
1. 새 GitLab 저장소를 사용하려는 경우, 해당 저장소의 이름을 입력하고 복제하거나 분기시킬 저장소의 URL을 입력하며 저장소 유형을 선택하십시오.

 a. 빈 저장소를 작성하려면 **새로 작성**을 클릭하십시오.

 b. GitLab 저장소의 사본을 작성하려면 **복제**를 클릭하십시오.

 c. 가져오기 요청을 통해 변경사항을 제공할 수 있도록 GitLab 저장소를 분기하려면 **분기**를 클릭하십시오.

1. 서버에 새 개인용 저장소를 작성하려는 경우 **이 저장소를 개인용으로 설정** 선택란을 선택 취소하십시오.
1. 문제 추적에 GitLab Issues를 사용하려면 **GitLab Issues 사용** 선택란을 선택하십시오.
1. 커미트의 태그와 주석 및 커미트에서 참조하는 문제의 레이블과 주석을 작성하여 코드 변경사항의 배치를 추적하려면 **코드 변경사항의 배치 추적** 선택란을 선택하십시오. 자세한 정보는 [Track where your code is deployed with toolchains![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/blogs/bluemix/2017/03/track-code-deployed-toolchains/){:new_window}를 참조하십시오.
1. **통합 작성**을 클릭하십시오.
1. 작업할 GitLab 저장소의 카드를 클릭하십시오. 선택한 저장소에 따라 저장소의 컨텐츠를 볼 수 있는 GitLab 웹 사이트 또는 회사의 GitLab 저장소가 열립니다.

  Eclipse Orion {{site.data.keyword.webide}}의 통합된 소스 코드 관리 도구를 사용하여 GitLab 저장소를 편집하고 작업공간에서 앱을 배치할 수 있습니다.
  {: tip}

1. GitLab Issues를 사용한 경우에는 **GitLab Issues**를 클릭하여 이를 여십시오. 도구 체인에 여러 개의 GitLab 저장소가 포함되어 있어도 전체 도구 체인에 대해 GitLab Issues의 이 인스턴스를 사용할 수 있습니다.    

링크 중인 저장소에 대해 소유자 또는 마스터 권한이 없으면 웹훅을 사용할 수 없으므로 통합이 제한됩니다. 웹훅은 커미트가 저장소에 푸시될 때 파이프라인을 자동으로 실행하는 데 필요합니다. 웹훅이 없으면 파이프라인을 수동으로 시작해야 합니다.
{: tip}

### GitLab에 대해 자세히 알아보기

GitLab에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [GitLab 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/code/tool_gitlab/){: new_window}를 참조하십시오.


## Jenkins 구성
{: #jenkins}

Jenkins는 지속적으로 소프트웨어를 빌드하고 테스트하는 오픈 소스, 서버 기반 도구이며, 지속적 통합 및 지속적 딜리버리의 사례를 지원합니다.

Jenkins 도구 통합을 작성하려면 먼저 Jenkins 서버가 있어야 합니다.
{: tip}

Jenkins 도구 통합을 사용하면 Slack 및 PagerDuty와 같은 도구 체인의 기타 도구에 Jenkins 작업 알림을 전송할 수 있습니다. 배치에서 코드를 추적하기 위해 배치 메시지를 Git 커미트 및 관련 Git 또는 JIRA issues에 추가할 수 있습니다. 또한 Toolchain Connections 페이지에서 배치를 볼 수도 있습니다. 사용자는 {{site.data.keyword.DRA_short}}에 테스트 결과를 피드하고 자동화된 품질 게이트를 추가하며 배치 위험성을 추적할 수 있습니다.

앱의 지속적 빌드, 테스트 및 배치를 자동화하도록 Jenkins를 구성하십시오.

1. 도구 체인을 작성하면서 이 도구 통합을 구성 중이면 구성 가능한 통합 섹션에서 **Jenkins**를 클릭하십시오.
1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하십시오. 그런 다음 **개요**를 클릭하십시오.  

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **Jenkins**을 클릭하십시오.

1. 도구 체인의 Jenkins 카드에서 이 도구 통합에 대해 표시할 이름을 입력하십시오.
1. 도구 체인에서 Jenkins 카드를 클릭할 때 열릴 Jenkins 서버의 URL을 입력하십시오.
1. 생성된 도구 체인 웹훅을 복사하십시오.
1. Jenkins 서버에서 다음 단계를 완료하십시오.

 a. [Install the IBM Cloud DevOps plug-in ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://wiki.jenkins-ci.org/display/JENKINS/IBM+Cloud+DevOps+Plugin#IBMCloudDevOpsPlugin-Installingtheplugin){: new_window}

 b. [Configure Jenkins to notify toolchains ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://wiki.jenkins-ci.org/display/JENKINS/IBM+Cloud+DevOps+Plugin#IBMCloudDevOpsPlugin-Notifyingtoolchains){: new_window}

 c. Jenkins 도구 통합의 통합 구성 페이지로 리턴하십시오.

1. **통합 작성**을 클릭하십시오.
1. 도구 체인에서 **Jenkins**를 클릭하여 Jenkins 서버를 보십시오.  

### Jenkins에 대해 자세히 알아보기

Jenkins에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [Jenkins 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/deliver/tool_jenkins/){: new_window}를 참조하거나 이 튜토리얼을 수행하십시오.

  * ["GitHub 및 Jenkins를 사용하는 Deployment Risk Analytics" 도구 체인을 사용하여 품질 배치 보장 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/ensure-quality-deployment-risk-analytics-with-github-and-jenkins-toolchain){:new_window}

## JIRA 구성
{: #jira}

JIRA는 소프트웨어와 관련된 문제와 버그를 추적하는 도구입니다. JIRA 도구 통합은 Jenkins 또는 {{site.data.keyword.deliverypipeline}}이 배치를 실행할 때마다 프로젝트의 문제를 업데이트합니다. JIRA 도구 통합이 문제를 추적할 수 있으려면 커미트 메시지에서 JIRA 스마트 커미트를 사용해야 합니다. JIRA 스마트 커미트에 대해 자세히 알아보려면 [Using Smart Commits![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://confluence.atlassian.com/fisheye/using-smart-commits-298976812.html){: new_window}를 참조하십시오.

품질 코드를 계획, 추적하고 전달하도록 JIRA 구성

1. 도구 체인을 작성하면서 이 도구 통합을 구성 중이면 구성 가능한 통합 섹션에서 **JIRA**를 클릭하십시오.
1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하십시오. 그런 다음 **개요**를 클릭하십시오.  

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **JIRA**를 클릭하십시오.

1. JIRA 프로젝트가 있으며 이에 연결하려면 JIRA 유형에 대해 **기존**을 클릭하십시오.

 a. JIRA 프로젝트의 JIRA 프로젝트 키를 입력하십시오. JIRA 프로젝트의 URL에서 프로젝트 키를 찾을 수 있습니다.

 b. JIRA 인스턴스의 기본 API URL을 입력하십시오. JIRA 인스턴스의 헤더에서 API URL을 찾을 수 있습니다. **관리** 아이콘을 클릭하고 **시스템**을 클릭하십시오.

 c. 개인용 JIRA 인스턴스에 연결 중인 경우 또는 공용 JIRA 인스턴스에서 추적성 정보를 받고자 하는 경우 JIRA 사용자 이름 및 비밀번호를 입력하십시오.

 d. 참조된 문제에 대한 레이블 및 주석을 작성하여 프로젝트에 대한 코드 변경사항의 배치를 추적하려면 **코드 변경사항의 배치 추적** 선택란을 선택하십시오. JIRA 스마트 커미트를 사용하여 GitHub 커미트의 JIRA 문제를 참조하는지 확인하십시오. 이 옵션을 선택하지 않으면 JIRA 도구 통합에서 커미트를 무시합니다.

1. JIRA 프로젝트를 작성하려면 JIRA 유형에 대해 **새로 작성**을 클릭하십시오.

 a. 새 프로젝트에 사용할 JIRA 프로젝트 키를 입력하십시오. 이 키는 프로젝트 URL의 고유 ID로 사용됩니다.

 b. JIRA 프로젝트의 이름을 입력하십시오.

 c. JIRA 인스턴스의 기본 API URL을 입력하십시오. JIRA 인스턴스의 헤더에서 API URL을 찾을 수 있습니다. **관리** 아이콘을 클릭하고 **시스템**을 클릭하십시오.

 d. 이 프로젝트에 사용할 JIRA 프로젝트 리더의 사용자 이름을 입력하십시오. JIRA 프로젝트 리더로서 임의의 사용자를 지정하려면 해당 사용자가 JIRA의 프로젝트 리더 권한을 보유해야 합니다.

 e. JIRA의 이 인스턴스에 대한 관리자의 사용자 이름을 입력하십시오.

 f. JIRA의 이 인스턴스에 대한 관리자의 비밀번호를 입력하십시오.

 g. 참조된 문제에 대한 레이블 및 주석을 작성하여 프로젝트에 대한 코드 변경사항의 배치를 추적하려면 **코드 변경사항의 배치 추적** 선택란을 선택하십시오. JIRA 스마트 커미트를 사용하여 GitHub 커미트의 JIRA 문제를 참조하는지 확인하십시오. 이 옵션을 선택하지 않으면 JIRA 도구 통합에서 커미트를 무시합니다.

1. **통합 작성**을 클릭하십시오.
1. 도구 체인에서 **JIRA**를 클릭하여 연결할 JIRA 프로젝트의 대시보드를 보십시오.

### JIRA에 대해 자세히 알아보기

JIRA에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [JIRA 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/code/tool_jira/){: new_window}를 참조하거나 이 튜토리얼을 수행하십시오.

  * ["GitHub 및 JIRA를 사용하는 Developer Insights 및 Team Dynamics" 도구 체인을 사용하여 통찰 얻기 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/gain-insights-developer-insights-and-team-dynamics-with-github-and-jira-toolchain){:new_window}


## Nexus 구성
{: #nexus}

Nexus 저장소(repo)에 빌드 아티팩트를 저장하도록 Nexus 저장소 관리자를 구성합니다.

1. 도구 체인을 작성하면서 이 도구 통합을 구성 중이면 구성 가능한 통합 섹션에서 **Nexus**를 클릭하십시오.
1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하십시오. 그런 다음 **개요**를 클릭하십시오.  

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **Nexus**를 클릭하십시오.

1. Nexus 도구 통합의 이 인스턴스에 대한 이름을 입력하십시오.
1. 도구 체인에서 Nexus 카드를 클릭할 때 열릴 Nexus 저장소의 URL을 입력하십시오.
1. 연결할 저장소 유형을 선택하십시오.
1. **npm 레지스트리**를 선택한 경우에는 다음 단계를 따르십시오.

 a. 레지스트리와 연관된 이메일 주소를 입력하십시오.

 b. 레지스트리와 연관된 인증 토큰을 입력하십시오.

 c. Nexus 서버의 개인용 레지스트리인 Nexus 릴리스 저장소의 URL을 입력하십시오.

 d. 여러 공용 및 개인용 npm 레지스트리를 결합하는 데 사용되는 URL을 입력하십시오. 예를 들어, 이 URL은 개인용 레지스트리 및 npm 글로벌 레지스트리의 캐시 모두에 액세스할 수 있는 Nexus 서버의 가상 레지스트리의 URL일 수 있습니다.

1. **Maven 저장소**를 선택한 경우에는 다음 단계를 따르십시오.

 a. 저장소와 연관된 사용자 ID를 입력하십시오.

 b. 저장소와 연관된 비밀번호를 입력하십시오.

 c. Nexus 서버의 개인용 릴리스 저장소인 Nexus 릴리스 저장소의 URL을 입력하십시오.

 d. Nexus 서버의 개인용 스냅샷 저장소인 Nexus 스냅샷 저장소의 URL을 입력하십시오.

 e. 여러 공용 및 개인용 Maven 저장소를 결합하는 데 사용되는 미러 또는 공용 저장소의 URL을 입력하십시오. 예를 들어, 이 URL은 개인용 저장소 및 Maven 중앙 저장소의 캐시 모두에 액세스할 수 있는 Nexus 서버의 가상 저장소의 URL일 수 있습니다.

1. **통합 작성**을 클릭하십시오.
1. 도구 체인에서 작업할 Nexus 저장소의 카드를 클릭하십시오. 저장소의 컨텐츠를 볼 수 있는 Nexus 웹 사이트가 열립니다.
1. 선택사항: {{site.data.keyword.Bluemix_notm}} 퍼블릭에서 도구 체인을 사용 중이며 npm에서 Nexus를 사용하여 앱을 빌드하려면 npm 빌드 작업을 추가하도록 파이프라인을 구성하십시오. 빌드 작업 구성에 대한 지시사항은 [파이프라인에서 Nexus npm 빌드 작업 구성](#config_nexus_npm) 절을 참조하십시오.
1. 선택사항: {{site.data.keyword.Bluemix_notm}} 퍼블릭에서 도구 체인을 사용 중이며 Maven에서 Nexus를 사용하여 앱을 빌드하려면 Maven 빌드 작업을 추가하도록 파이프라인을 구성하십시오. 빌드 작업 구성에 대한 지시사항은 [파이프라인에서 Nexus Maven 빌드 작업 구성](#config_nexus_maven) 절을 참조하십시오.

### 파이프라인에서 Nexus npm 빌드 작업 구성
{: #config_nexus_npm}

파이프라인에서 npm 빌드 작업을 구성하려면, 우선 입력으로서 빌드 SCM 저장소를 사용할 수 있는 작업 파이프라인이 있어야 하며 도구 체인의 Nexus를 구성해야 합니다. Nexus 구성에 대한 지시사항은 [Nexus](#nexus) 절을 참조하십시오.

npm 빌드 작업을 추가하도록 {{site.data.keyword.deliverypipeline}}을 구성하십시오.

1. 단계를 작성하고 적합한 SCM 저장소에 대한 입력을 설정하십시오.
1. 단계에서 빌드 작업을 추가하십시오.
1. 빌드 작업을 구성하십시오.
  ![npm 빌드 작업](images/nexus_npm_job.png)

  a. 빌더 유형에 대해 **NPM 빌드**를 선택하십시오.

  b. Nexus 도구 통합의 여러 인스턴스를 구성한 경우에는 npm 빌드 작업이 구성될 Nexus 도구 통합의 이름을 입력하십시오.

  c. 도구 통합 유형에 대해 **Nexus**를 선택하십시오.

  d. 빌드 명령에 대해 npm 모듈을 빌드하거나 이를 레지스트리에 공개하는 명령을 입력하십시오. 다음 예제는 모듈을 빌드하거나 이를 공개하는 명령을 보여줍니다.
     ```
     npm install
     # or
     npm publish --registry "${NPM_RELEASE_URL}"
     ```
  **팁:** Nexus 도구 통합을 위한 구성 설정의 레지스트리에 연결하는 데 사용된 URL 및 사용자 신임 정보를 찾을 수 있습니다.

  e. 빌드 작업이 Nexus 레지스트리에 공개되며 노드 모듈 버전의 형식이 `x.y.z-SNAPSHOT.w`인 경우에는 **스냅샷 모듈 버전 올리기** 선택란을 선택하십시오. 빌드 작업은 Nexus 레지스트리에 공개되기 전에 모듈 버전을 자동으로 업데이트합니다. 빌드 작업은 로컬 `package.json` 파일 및 npm 레지스트리에서 모듈의 최상위 버전을 선택하며 semver을 사용하여 모듈 버전을 올립니다. 빌드 작업은 변경사항을 SCM 저장소에 전달하지 않습니다.

1. **저장**을 클릭하십시오. 파이프라인이 실행될 때마다 이 빌드 작업은 Nexus 도구 통합의 구성 정보를 사용하여 npm 레지스트리에 연결합니다.

### 파이프라인에서 Nexus Maven 빌드 작업 구성
{: #config_nexus_maven}

파이프라인에서 Maven 빌드 작업을 구성하려면, 우선 입력으로서 빌드 SCM 저장소를 사용할 수 있는 작업 파이프라인이 있어야 하며 도구 체인의 Nexus를 구성해야 합니다. Nexus 구성에 대한 지시사항은 [Nexus](#nexus) 절을 참조하십시오.

Maven 빌드 작업을 추가하도록 {{site.data.keyword.deliverypipeline}}을 구성하십시오.

1. 단계를 작성하고 적합한 SCM 저장소에 대한 입력을 설정하십시오.
1. 단계에서 빌드 작업을 추가하십시오.
1. 빌드 작업을 구성하십시오.
  ![Maven 빌드 작업](images/nexus_maven_job.png)

  a. 빌더 유형에 대해 **Maven 빌드**를 선택하십시오.

  b. Nexus 도구 통합의 여러 인스턴스를 구성한 경우에는 Maven 빌드 작업이 구성될 Nexus 도구 통합의 이름을 입력하십시오.

  c. 도구 통합 유형에 대해 **Nexus**를 선택하십시오.

  d. 빌드 명령에 대해 Maven 모듈을 빌드하거나 이를 스냅샷 레지스트리에 공개하는 명령을 입력하십시오. 다음 예제는 모듈을 빌드하거나 이를 공개하는 명령을 보여줍니다.
     ```
     mvn -B clean package
     # or
     mvn -DaltDeploymentRepository="snapshots::default::${MAVEN_SNAPSHOT_URL}" deploy
     ```
  Nexus 도구 통합을 위한 구성 설정의 레지스트리에 연결하는 데 사용된 URL 및 사용자 신임 정보를 찾을 수 있습니다.
  {: tip}

1. **저장**을 클릭하십시오. 파이프라인이 실행될 때마다 이 빌드 작업은 Nexus 도구 통합의 구성 정보를 사용하여 Maven 저장소에 연결합니다.

### Nexus에 대해 자세히 알아보기

Nexus에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [Nexus 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/deliver/tool_nexus/){: new_window}를 참조하십시오.


## 사용자 정의 도구(기타 도구) 구성
{: #othertool}

사용자의 팀이 도구 체인 통합 목록에 포함되지 않은 도구를 사용하는 경우에는 사용자 정의 도구를 통합할 수 있습니다.

사용자 정의 도구를 구성하면 도구 체인에서 다른 도구와 함께 작동하며 사용자의 팀에 사용 가능합니다.

1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **기타 도구**를 클릭하십시오.

1. 도구 이름을 입력하십시오.
1. 도구와 가장 밀접하게 연관된 라이프사이클 단계를 선택하십시오. 이 선택사항은 개요 페이지에서 도구가 나열되는 카테고리를 판별합니다.
1. 아이콘 URL을 추가하십시오. 아이콘이 도구 통합의 카드에 표시됩니다.
1. 문서 URL을 추가하십시오.
1. 도구 인스턴스 이름을 지정하십시오. 예: My Team Tool.
1. 도구 인스턴스 URL을 추가하십시오. 이 URL은 도구 통합의 카드를 클릭할 때마다 열립니다.
1. 도구에 대한 설명을 추가하십시오.
1. (고급) 필요하면 특성을 더 추가하십시오. 예를 들어, 도구가 도구 체인의 기타 도구와 통합하는 데 필요한 속성 또는 정보를 나열하십시오.  
1. **통합 작성**을 클릭하십시오.

### 사용자 정의 도구에 대해 자세히 알아보기

사용자 정의 도구에 대해 자세히 알아보려면 [Introducing custom tool integration for {{site.data.keyword.Bluemix_notm}} toolchains![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/blogs/bluemix/2016/10/custom-tool-integration-with-bluemix-toolchains/){: new_window}를 참조하십시오.

  * [Add a custom tool integration to a toolchain ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/add-a-custom-tool-integration-to-a-toolchain){:new_window}


## PagerDuty 구성
{: #pagerduty}

PagerDuty는 여러 모니터링 시스템의 데이터를 단일 보기로 통합합니다. 문제가 발생하면 PagerDuty는 당시에 해당 문제를 가장 잘 수정할 수 있는 팀 구성원에게 알림이 전송되도록 합니다. 해당 팀 구성원이 문제점에 응답하지 않는 경우 해당 문제점을 두 번째 엔지니어 또는 운영 관리자에게 라우트하도록 에스컬레이션을 구성할 수 있습니다.

문제점을 보다 빨리 수정하여 가동중단시간을 줄이려면 파이프라인 단계 장애가 발생할 경우 알림을 전송하도록 PagerDuty를 구성하십시오.

1. 도구 체인을 작성할 때 이 도구 통합을 구성하는 경우, 구성 가능한 통합 섹션에서 **PagerDuty**를 클릭하십시오.
1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **PagerDuty**를 클릭하십시오.

1. API 키를 사용하여 계정 레벨에서 PagerDuty를 통합하려면 **계정**을 클릭하십시오.

 a. PagerDuty 계정의 API 액세스 키를 입력하십시오. PagerDuty 계정이 없으면 [register for one ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://signup.pagerduty.com/accounts/new){: new_window}을 수행하십시오. 키 찾기에 대한 지시사항은 [Generating an API Key![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://support.pagerduty.com/hc/en-us/articles/202829310-Generating-an-API-Key){: new_window}를 참조하십시오.

 b. 사용하는 PagerDuty 서비스의 이름을 입력하십시오.

 c. 1차 PagerDuty 담당자의 이메일 주소를 입력하십시오.

 d. 1차 PagerDuty 담당자의 전화번호를 입력하십시오.

1. 통합 키를 사용하여 서비스 레벨에서 PagerDuty를 통합하려면 **서비스**를 클릭하십시오.

 a. 경보를 게시할 PagerDuty 서비스의 URL을 입력하십시오.

 b. PagerDuty 통합 키를 입력하십시오. 사용자 키를 찾거나 PagerDuty 서비스 페이지의 통합 섹션에서 키를 작성할 수 있습니다.

1. **통합 작성**을 클릭하십시오.
1. **PagerDuty**를 클릭하여 pagerduty.com으로 이동하십시오. 도구 체인에 대해 이 도구 통합을 구성할 때 지정한 PagerDuty 서비스와 연관된 이벤트를 볼 수 있습니다.

### PagerDuty에 대해 자세히 알아보기

PagerDuty에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [PagerDuty 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/manage/tool_pagerduty/){: new_window}를 참조하거나 이 튜토리얼 및 Garage Method advocate 코스를 수행하십시오.

  * ["Cloud Foundry에서 마이크로서비스 개발 및 테스트" 도구 체인 사용 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}

  * [Become a Garage Method advocate ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/course/gm_advocate/){:new_window}


## Rational Team Concert 구성
{: #rationalteamconcert}

IBM Rational Team Concert&trade;는 반복 계획, 변경 관리, 결함 추적, 소스 제어, 빌드 자동화 및 보고를 포함하는 개발 태스크를 통합하는 팀 협업 도구입니다.

개발 환경에서 DevOps 접근 방법 및 지속적 딜리버리의 사례로 Rational Team Concert를 구성하십시오.

1. 도구 체인을 작성할 때 이 도구 통합을 구성하는 경우 구성 가능한 통합 섹션에서 **Rational Team Concert**를 클릭하십시오.
1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하십시오. 그런 다음 **개요**를 클릭하십시오.  

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **Rational Team Concert**를 클릭하십시오.

1. 도구 체인에서 Rational Team Concert 카드를 클릭할 때 열고자 하는 Rational Team Concert 서버의 URL을 입력하십시오.
1. Rational Team Concert 서버에 액세스하기 위해 사용하는 사용자 ID를 입력하십시오.
1. Rational Team Concert 서버에 액세스하기 위해 사용하는 비밀번호를 입력하십시오.
1. 도구 체인에 추가하려는 Rational Team Concert 프로젝트 영역이 있는 경우 다음 단계를 따르십시오.

 a. **프로젝트 영역 유형** 목록에서 **기존 프로젝트 영역**을 선택하십시오.

 b. 도구 체인에 추가할 프로젝트 영역의 이름을 입력하십시오.

1. 도구 체인에 추가할 Rational Team Concert 프로젝트 영역을 작성하려는 경우 다음 단계를 따르십시오.

 a. **프로젝트 영역 유형** 목록에서 **새 프로젝트 영역**을 선택하십시오.

 b. 도구 체인에 추가할 새 프로젝트 영역의 이름을 입력하십시오.

 c. 프로젝트 작성에 사용할 Rational Team Concert 프로세스 템플리트의 이름을 입력하십시오.

1. 작업 항목에 대한 태그 및 주석을 작성하여 프로젝트에 대한 코드 변경사항의 배치를 추적하려면 **코드 변경사항의 배치 추적** 선택란을 선택하십시오.
1. **통합 작성**을 클릭하십시오.
1. 도구 체인에서 **Rational Team Concert**를 클릭하여 구성한 Rational Team Concert 대시보드를 여십시오.

### Rational Team Concert에 대해 자세히 알아보기

Rational Team Concert에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [IBM Rational Team Concert 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/think/tool_rtc/){: new_window}를 참조하십시오.


## Sauce Labs 구성
{: #saucelabs}

Sauce Labs는 기능 단위 테스트를 실행합니다. {{site.data.keyword.deliverypipeline}}에서 Sauce Labs 테스트 스위트가 테스트 작업으로 구성되어 있는 경우, 이 테스트 스위트는 지속적 딜리버리 프로세스의 일부로 웹 또는 모바일 앱에 대해 테스트를 실행할 수 있습니다. 이러한 테스트는 프로젝트의 중요한 플로우 제어를 제공할 수 있으며 잘못된 코드의 배치를 방지하는 게이트 역할을 합니다.

 이 도구 통합은 {{site.data.keyword.Bluemix_notm}} 퍼블릭에서만 사용 가능합니다.
 {: tip}

여러 운영 체제 및 브라우저에서 자동화된 기능 테스트를 실행하도록 Sauce Labs를 구성하십시오. 그러면 사용자가 웹 사이트 또는 애플리케이션을 사용할 가능성이 있는 방법을 에뮬레이트할 수 있습니다.

1. 도구 체인을 작성할 때 이 도구 통합을 구성하는 경우, 구성 가능한 통합 섹션에서 **Sauce Labs**를 클릭하십시오.
1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **Sauce Labs**를 클릭하십시오.

1. 사용하는 Sauce Labs 계정과 연관된 사용자 이름을 입력하십시오. [Sauce Labs 계정 페이지의 위쪽에 있는 환영 메시지에서 사용자 이름 찾기![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://saucelabs.com/account){: new_window}를 수행할 수 있습니다.
1. Sauce Labs 계정의 액세스 키를 입력하십시오. [Sauce Labs 계정 페이지에서 키 찾기![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://saucelabs.com/account){: new_window}를 수행할 수 있습니다.
1. **통합 작성**을 클릭하십시오.
1. **Sauce Labs**를 클릭하여 saucelabs.com으로 이동하고 도구 체인의 테스트 활동을 보십시오.

 {{site.data.keyword.deliverypipeline}}에 Sauce Labs 테스트 작업을 추가한 경우 서비스 인스턴스를 선택할 수 있습니다. 파이프라인에서 테스트 작업을 구성하기 위한 지시사항은 [파이프라인에서 Sauce Labs 테스트 작업 구성](#config_saucelabs) 절을 참조하십시오.
 {: tip}

### Sauce Labs에 대해 자세히 알아보기

Sauce Labs에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [Sauce Labs 기사 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/deliver/tool_sauce_labs/){: new_window}를 참조하거나 다음 튜토리얼을 활용하십시오.

  * ["Cloud Foundry에서 마이크로서비스 개발 및 테스트" 도구 체인 사용 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}



## Slack 구성
{: #slack}

공용 Slack 채널에 게시되는 알림은 팀의 모든 구성원에게 표시됩니다. 컨텐츠를 게시한 사람이 해당 컨텐츠에 대한 책임을 집니다.
{: tip}

Slack은 클라우드 기반의 실시간 메시징 및 알림 시스템입니다. Slack은 팀 협업을 위해 이메일 대신 사용할 수 있는 대화성이 뛰어난 지속적 대화를 제공합니다. 전용 채널이나 작업과 직접 관련이 있는 채널 세트에서 팀과 통신할 수 있습니다. 채널을 통해 또는 둘 이상의 사용자 간의 직접 메시지에서 파일 및 이미지를 공유할 수도 있습니다. 직접 메시지 및 채널에서의 통신은 검색이 가능하도록 유지됩니다.

도구 통합에서 도구 체인에 대한 알림(예: 테스트 및 배치 활동)을 수신하도록 Slack을 구성하십시오.

1. 도구 체인을 작성할 때 이 도구 통합을 구성하는 경우, 구성 가능한 통합 섹션에서 **Slack**을 클릭하십시오.
1. 도구 체인이 있고 여기에 이 도구 통합을 추가하는 경우 DevOps 대시보드의 도구 체인 페이지에서 도구 체인을 클릭하여 해당 개요 페이지를 여십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하고 **개요**를 클릭하십시오.

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **Slack**를 클릭하십시오.

1. 수신 웹훅으로서 Slack에 의해 생성된 Slack 웹훅 URL을 수신하십시오. 도구 통합에서 도구 체인에 대한 알림을 받으려면 Slack 채널에 대한 Slack 웹훅 URL이 필요합니다. 웹훅 작성 또는 찾기에 대한 지시사항은 [Incoming Webhooks![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://api.slack.com/incoming-webhooks){: new_window}를 참조하십시오.

 Slack 채널에 대한 API 키를 사용하여 도구 통합에서 도구 체인에 대한 알림을 받은 경우에는 웹훅을 대신 사용하도록 구성을 업데이트해야 합니다.
 {: tip}

1. 알림을 전송할 Slack 채널의 이름을 입력하십시오. 채널이 있어야 하며 Slack 팀에서 이를 사용 중이어야 합니다.
1. 팀 URL에서 `.slack.com` 이전의 단어 또는 구문인 Slack 팀의 URL 호스트 이름을 입력하십시오. 예를 들어, 팀 URL이 `https://team.slack.com`이면 호스트 이름은 `team`입니다.
1. **통합 작성**을 클릭하십시오.

 지정된 Slack 채널 및 팀에 도달할 수 없는 경우에는 `Setup Failed` 오류가 Slack 카드에 표시됩니다. `Setup Failed` 메시지 위에 마우스 커서를 올려놓고 **재구성**을 클릭하십시오. Slack 팀의 URL 호스트 이름 및 Slack 웹훅 URL, Slack 채널에 대해 올바른 구성 매개변수를 사용 중인지 확인하십시오. 필요하면 설정을 업데이트하고 **통합 저장**을 클릭하십시오.
 {: tip}

1. **Slack**을 클릭하십시오. 구성된 Slack 채널에서 도구 체인의 모든 활동을 볼 수 있습니다.

### Slack에 대해 자세히 알아보기

Slack에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [Slack 기사 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/culture/tool_slack/){: new_window}를 참조하거나 다음 튜토리얼 및 Garage Method advocate 코스를 활용하십시오.

  * ["Cloud Foundry에서 마이크로서비스 개발 및 테스트" 도구 체인 사용 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}

  * [Become a Garage Method advocate ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/course/gm_advocate/){:new_window}


## SonarQube 구성
{: #sonarqube}

SonarQube에서는 소스 코드의 전체 상태와 품질의 개요을 제공하고 새 코드에서 발견된 문제를 강조표시합니다. 코드 분석기는 20개가 넘는 코딩 언어의 널-포인터 참조 해제, 논리 오류 및 리소스 유출과 같은 까다로운 버그를 발견합니다.

소스 코드의 품질을 지속적으로 분석하고 측정하도록 SonarQube를 구성하십시오.

1. DevOps 대시보드에서 **도구 체인**을 클릭하십시오. SonarQube를 추가할 도구 체인을 클릭하십시오. 또는 앱 개요 페이지의 Continuous Delivery 카드에서 **도구 체인 보기**를 클릭하십시오. 그런 다음 **개요**를 클릭하십시오.  

 a. **도구 추가**를 클릭하십시오.

 b. 도구 통합 섹션에서 **SonarQube**을 클릭하십시오.

1. SonarQube 도구 통합의 이 인스턴스에 대한 이름을 입력하십시오.
1. 도구 체인에서 SonarQube 카드를 클릭할 때 열리는 SonarQube 인스턴스의 URL을 입력합니다.
1. 선택사항: SonarQube 서버에 연결하는 데 사용할 사용자 이름을 입력하십시오.

 SonarQube 서버에 연결하기 위해 비밀번호를 사용하는 경우에만 사용자 이름을 지정해야 합니다. 인증 토큰을 사용하여 연결하는 경우 이 필드를 공백으로 두십시오.
 {: tip}

1. SonarQube 서버에 연결하는 데 사용할 비밀번호나 인증 토큰을 입력하십시오.
1. **통합 작성**을 클릭하십시오.
1. 도구 체인에서 **SonarQube**를 클릭하여 연결할 SonarQube 인스턴스의 대시보드를 보십시오.

### SonarQube에 대해 자세히 알아보기

SonarQube에 대해 자세히 알아보려면 IBM Cloud Garage Method에서 [SonarQube 기사![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/garage/content/learn/tool_sonarqube/){: new_window}를 참조하십시오.
