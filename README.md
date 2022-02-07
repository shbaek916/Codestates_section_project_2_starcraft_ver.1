# Codestates_section_project_2_starcraft_ver.1
## _스타크래프트 2 승패 예측 및 분석_

#### 개요 & 데이터에 대한 설명
- 2020년 4월 종료된 행동 데이터 분석 인공지능 AI 경진대회 (DACON)
- 주소 : https://dacon.io/competitions/official/235583/overview/description
- 행동 데이터 : 사용자가 서비스를 사용하며 겪게 되는 행동을 데이터화 한 것 이 데이터의 경우 한 게임의 두 플레이어가 게임 중 하게 되는 행동의 로그기록을 데이터화 한 것
- 데이터 구성 방법 : 로그데이터의 event 칼럼에 따라, 겜의 각 플레이어들이 그 event를 얼마나 실행했는지 합하여 새로운 데이터셋을 생성

#### 풀고자하는 문제(새로 생성한 데이터셋에서)
스타2 플레이어들의 어떤 특성이 그들을 이기거나 지게 하는 것인가
- game_id : 게임 고유 ID
- winner : 게임의 승자 (타겟)
- time : 게임 종료 시간
- species : 플레이어의 종족 T: 테란 || P: 프로토스 || Z: 저그
- camera : 게임 시간동안 화면을 움직인 횟수
- selection : 게임 시간동안 객체 선택 횟수
- right click : 게임 시간동안 마우스 우클릭 횟수
- ability : 게임 시간동안 생산, 공격 등 플레이어의 주요행동 횟수 (운용능력)
- getcontrolgroup : 게임 시간동안 부대 불러오기 횟수
- setcontrolgroup : 게임 시간동안 부대 지정 횟수
- addtocontrolgroup : 게임 시간동안 부대에 추가 횟수
- APM : 1분당 지시한 명령 횟수
- worker : 게임 시간동안 일꾼 생산 명령 횟수
- nonworker : 게임 시간동안 일꾼 외 유닛 생산 명령 횟수

#### 가설과 탐색

- 플레이어들의 유닛과 건물 운용능력(Ability)이 승패를 좌우할 것이다 : player_0_Ability, player_1_Ability
- 플레이어들이 생산한 일꾼(유닛)의 수가 승패를 좌우할 것이다 : player_0_worker, player_1_worker
- 베이스라인 모델 : 최빈값
- 평가지표 : 정확도와 F1
- F1 선택 이유 : 정확도가 높은 것이 두가지 클래스를 모두 정확하게 분류한다는 뜻은 아니기 때문에 이를 보정하고 오류를 줄일 수 있다.


