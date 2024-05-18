# Chapter01 소개

- 주변환경과 상호작용 -> 학습
- 강화학습(Reinforcement Learning): RL
- RL: 상호작용 + computational -> 목표(goal) 지향적인 학습

## 1.1 강화학습
- RL: 주어진 상황(환경(environment), 상태(state), ..)에서 어떤 행동(action)을 취할지를 학습자(agent)가 학습(최대한의 보상(reward)을 얻게 끔)
- RL 중요한 두 가지 특성: 시행착오(trial and error), 지연된 reward
- RL 체계화 <- 동적 시스템 이론(불확실한 Markov Decision Process(MDP))
- 가장 간단한 형태의 MDP <감지(detection), action, goal>
- RL이 갖는 어려운 점: 탐험(exploration)과 활용(exploitation)의 절충
- RL은 불확실한 주변 environment와 상호작용하는 goal 지향적인 agent에 대한 모든 문제를 고려

## 1.2 예제
- 체스, 바둑
- agent와 불확실한 요소를 가진 environment 사이의 interaction 안에서 agent는 goal을 이루기 위하여 올바른 action 선택을 해야함
- 그러기 위해서는 action의 간접적인 영향과 지금의 action이 일정 시간이 지난 후에 미칠 효과를 고려해야하고, 이를 위해 예지력이나 계획(planning)이 필요할 수 도 있음
- 하지만, action의 결과를 완전히 정확하게 예측할 수는 없기 때문에 agent는 주변 environment를 자주 모니터링하고 적절한 대응을 해야함
- agent는 자신이 직접 관찰한 사실을 통해 현 상황이 goal에 얼마나 가까이 다가가 있는지 판단할 수 있음 -> goal을 분명하게 인식 가능
- agent는 자신의 경험을 활용하여 시간이 지남에 따라 action의 능력을 키우게 됨

## 1.3 강화학습의 구성 요소
- 학습자(agent), 주변 환경(environment), 정책(policy), 보상 신호(reward signal), 가치 함수(value function), environment에 대한 모델(model)-(필수x)
- policy: 특정 시점에 agent가 취하는 action을 정의
  - 일반적으로, policy는 확률론적(stochastic)으로 action을 선택
- reward signal: RL이 성취해야 할 goal을 정의
  - 매 시간마다 environment은 agent에게 reward를 전달
  - agent의 유일한 목표는 장기간에 걸쳐 agent가 획득하게 되는 reward의 총합을 최대로 만드는 것
  - reward는 agent가 직면한 문제를 정의하는 즉각적인 신호
  - reward signal은 policy를 바꾸는 주된 원인
  - 일반적으로, reward signal은 environment의 state와 취해진 action에 대해 확률적으로 그 값이 선택되는 stochastic 함수
- value function: 장기적인 관점에서 무엇이 좋은 것인가를 알려줌
  - value: 그 state의 시작점에서부터 일정 시간 동안 agent가 기대할 수 있는 reward의 총량(장기적 관점(long-term))
  - 어떤 결정을 내리고 그 결정을 평가할 때 가장 많이 고려하는 것은 value
  - value 추정이 RL에서 핵심적 역할
- environment model: environment의 변화를 모사 - (필수x)
  - 일반적으로, environment가 어떻게 변화해 갈지를 추정할 수 있게 해줌
  - model은 planning을 위해 사용 됨
    - planning: 미래의 상황을 실제로 경험하기 전에 가능성만을 고려하여 일련의 action을 결정하는 방법
  - model + planning -> 모델 기반(model-based)
  - agent의 trial and error -> 모델 없는 방법(model-free)
  - trial and error을 통해 environment model을 학습하고 동시에 그 model을 사용하여 planning하는 과정을 수행하는 RL 시스템도 존재

## 1.4 한계와 범위
