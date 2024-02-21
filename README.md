## 학습 플랫폼 이용자 구독 갱신 예측 해커톤
제공된 데이터를 통해 이용자들의 학습 패턴, 구독 이력, 로그인 활동 등 다양한 이용 행태를 분석

## 프로젝트 개요

### 프로젝트 기간

2023.11 ~ 2023.12

### 필요한 라이브러리
``` python


import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
import os

```


##데이터 가설 설정
구독 유형과 구독 유지 여부
 
구독유형은 Basic과 Premium으로 구분되어있다.
Basic이 Premium보다 가격이 저렴하기 때문에 유지율이 높을것 같다.
Premium이 선호하는 난이도가 Basic보다 높을것이다.
완료한 총 코스 수가 많을 수록 커뮤니티 참여도도 높고 구독 유지를 할 것이다.
 
## 데이터 살펴보기
user_id: 사용자의 고유 식별자
subscription_duration: 사용자가 서비스에 가입한 기간 (월)
recent_login_time: 사용자가 마지막으로 로그인한 시간 (일)
average_login_time: 사용자의 일반적인 로그인 시간
average_time_per_learning_session: 각 학습 세션에 소요된 평균 시간 (분)
monthly_active_learning_days: 월간 활동적인 학습 일수
total_completed_courses: 완료한 총 코스 수
recent_learning_achievement: 최근 학습 성취도
abandoned_learning_sessions: 중단된 학습 세션 수
community_engagement_level: 커뮤니티 참여도
preferred_difficulty_level: 선호하는 난이도
subscription_type: 구독 유형
customer_inquiry_history: 고객 문의 이력
payment_pattern
  사용자의 지난 3개월 간의 결제 패턴을 10진수로 표현한 값.
  - 7: 3개월 모두 결제함
  - 6: 첫 2개월은 결제했으나 마지막 달에는 결제하지 않음
  - 5: 첫 달과 마지막 달에 결제함
  - 4: 첫 달에만 결제함
  - 3: 마지막 2개월에 결제함
  - 2: 가운데 달에만 결제함
  - 1: 마지막 달에만 결제함
  - 0: 3개월 동안 결제하지 않음
target: 사용자가 다음 달에도 구독을 계속할지 (1) 또는 취소할지 (0)를 나타냄
## 데이터 출처
https://dacon.io/competitions/official/236179/overview/description


