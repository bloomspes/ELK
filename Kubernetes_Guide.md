# IBM Cloud platform 을 활용한 Kubernetes node 사용 가이드 
## 1. IBM cloud kubernetes CLI installation guide

- 모든 클라우드 서비스는 CLI를 설치 하는 것에서 부터 출발합니다. 그 이유는, CLI를 통해 클라우드의 리소스를 제어 할 수 있는 기능이 GUI 방식에 비해 더 간편하고, 많기 때문 입니다. IBM Cloud의 CLI를 인스톨 하는 url은 [IBM CLI Install](https://cloud.ibm.com/docs/containers?topic=containers-cs_cli_install) 에서 참조할 수 있습니다.

## 2. Analyze logs in Kibana for an app that is deployed in a Kubernetes

- 뒤에서 더 자세하게 다루겠지만, ELK의 CRUD(Create, Read, Update, Delete)작업은 **REST API**를 호출해서 이루어 집니다. Kibana 서비스는 자동 완성과 쿼리 형식을 지원하므로, ELK Document 작업시 함께 사용하는 경우가 많습니다. Kubernetes Cluster에 배포된 앱에 대해서 [Kibana로 로그 분석을 하는 과정 살펴보기](https://cloud.ibm.com/docs/services/CloudLogAnalysis?topic=cloudloganalysis-container_logs&_ga=2.119110990.675818140.1567592592-1867362325.1567592592&cm_mc_uid=80779148459215667943334&cm_mc_sid_50200000=92217161567659999051&cm_mc_sid_52640000=28871961567660367421
)

## 3. How to run ELK on IBM Cloud Kubernetes

- 여기서는 IBM Cloud 플랫폼 만이 아닌, 호환 되는 다른 오픈스택 플랫폼과 클라우드 엔진에서 ELK를 실행 하는 방법에 대해 업로드 했습니다.
[ELK 실행 하기](https://portworx.com/run-ha-elasticsearch-elk-ibm-cloud-kubernetes-service/)

## 4. Install and Configure with calicoctl (Networking policy)

- 쿠버네티스의 **파드(pod)** 는 쿠버네티스 어플리케이션의 실행 단위 입니다. 파드와 파드간 통신을 위해 외부 엔드포인트 설정 작업이 필요한데, IBM Kubernetes 클러스터 에서는 Calico 라는 네트워크 플러그인으로 기본 네트워크 정책을 설정합니다. Calico 정책은 ``calicoctl`` 이라는 명령어를 사용합니다.
[IKS 네트워크 정책 설정](https://cloud.ibm.com/docs/containers?topic=containers-network_policies#cli_install)

## 5. Deploy on IBM Kubernetes Cluster

- 마지막으로, [IKS에서 어플리케이션을 배포하는 방법](https://github.com/IBM-Cloud/get-started-node/blob/master/README-kubernetes.md)에 대해서 알아봅니다.

- **free cluster를 하나 생성하시면, 한 달 동안 한 개의 worker node로 IKS를 이용할 수 있습니다.**
