# Chapter02 다중 선택
- 지도학습의 학습 방법: 올바른 행동을 알려주는 지침(instruct)
- 강화학습의 학습 방법: 행동의 좋고 나쁨을 평가(evaluate)
- 비연합(nonassociative) 구조: 하나의 상황에 대해서만 행동을 학습하는 구조
- nonassociative 구조로부터 evaluate feedback과 instruct feedback의 차이 및 그 둘의 결합을 먼저 공부할 예정 -> 연합적(associative) 구조로 확장하여 강화학습 문제를 전체적으로 다룰 예정

## 2.1 다중 선택 문제
- 단일 선택(one-armed bandit)
- 다중 선택 문제(k-armed bandit problem)의 원형
  - k개의 서로 다른 옵션(행동) 중 하나를 반복적으로 선택
  - 매 선택 후에는 숫자로 된 보상이 주어짐 (보상을 나타내는 값은 정상 확률 분포(stationary probability distribution)로부터 얻어짐)
    - stationary probability distribution: 시간에 따라 변하지 않는 확률 분포
  - 선택의 목적은 일정 기간 또는 n개의 시간 간격(time step)동안 주어지는 보상의 총량에 대한 기댓값을 최대화하는 것
