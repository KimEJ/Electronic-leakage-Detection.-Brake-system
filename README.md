# Electronic leakage Detection / Brake system

## What is EDB

### 개발 배경

현대의 사람들에게 전기는 가정, 회사 그리고 길거리를 비롯한 모든 곳에서 사용되는 꼭 필요한 존재이다. 이렇듯 전기는 사람들에게 많은 도움과 편리함을 제공하지만 무의식적으로 전기를 허비 하거나 누진세로 인해 전기세 폭탄이라는 부담을 주기도 한다. 본 팀은 사용전력을 시각화하여 제공함으로써 사람들의 금전적 부담을 감소시킬 수 있는 ‘EDB’를 진행하고자 한다. 


### 제품 설명

기존 전력 계량기, 누전차단기, 스마트 허브 등은 비슷한 기능을 하고 있음에도 각각의 제품이 나오고 있다. 이 제품은 그런 점을 보완하기위해 누전차단기에 전력 계량기, smart Hub가 결합된 형태로 사용자가 전력 사용량을 모니터링하고 제어할 수 있다. 이로서 전력 계량기, 누전차단기의 정보를 스마트허브에서 사용할 수 있는 등 서로의 정보를 공유해 더욱 효율적이고 편리한 전력 운용이 가능한 제품이다.


### 개발 방향

누전차단기가 사용자가 정의한 절전 설정에 따라 가내 사용전력, 전력 수급 현황 등을 모니터링하여 제어할 수 있고, 사용자의 제어에 따라 가전기기들을 제어할 수 있도록 개발 될 것이다. 이 모든 설정, 제어는 누전차단기에서 이루어지지 않고 클라이언트에서 누전차단기 서버에 접속해 제어하여 사용이 용이하게 할 것이다. 또한 모니터링된 자료와 그를 통해 정제된 데이터들을 클라이언트에서 시각화하여 사용자에게 제공하여 사용자의 안정적인 전력 운용을 도울 것이다.


### 시제품 형태

사용자가 설정할 수 있고, 상황을 모니터링, 제어할 수 있는 클라이언트, 누전차단기와 서버의 역할을 하는 하드웨어가 제작될 것이다. 하드웨어의 경우 누전차단기와 전력량계, smart Hub가 하나로 결합된 형태로 만들어 질 것이다. 클라이언트의 경우 서버가 되는 누전차단기에 접속해서 절전모드를 설정하거나 직접 차단, 해제시킬 수 있게 만들어질 것이다.


### 파급효과 

이와 같은 제품이 상용화가 된다면 비슷한 여러 기능들을 하나로 묶어 활용도가 높아질 것이고, 각각의 제품을 구비해야했던 기존에 비해 필요 예산을 줄일 수 있을 것이다. 또한 전력 사용현황을 알 수 있고 실시간으로 절전이 가능해 자원절약이 용이해질 것이다.





## 역할

* 김동현 - 서버
* 김어진 - 임베디드
* 박소현 - 안드로이드
* 유성민 - 임베디드
* 윤태훈 - 서버





## 각 분야별 기능

### client

1. 모니터링
	* 서버에서 데이터를 받아와 시각화
		
		-> 안드로이드 배터리 사용량 그래프처럼
		![battery](http://cfile1.uf.tistory.com/image/232AF93D55E1906433C9A3)
	* 모니터링은 5분 주기
		* 새로고침 버튼
		* 주기 변경
2. 절전 설정
	* 전력 사용량 기준
	* 시간대 기준
	* 요일 기준
3. 전원 on/off 토글 스위치
	* 누전차단기에 있는 스위치를 제어


### server

1. 모니터링
	* 1분주기로 하드웨어에서 받아옴
2. 전력 제어
	* 주기별로 환경설정 DB조회 -> 제어
	* 주기는 10분 단위
3. 사용 스레드 목록
	* 추가 예정


### DB

추가 예정


### hardware

1. 모니터링
	* 전력 측정 모듄
	* 실시간 조회 -> 서버의 요구시(1분 주기) 데이터 전송
2. 차단 기능
	* 릴레이 사용
	* 절전 차단
	* 누전 차단
