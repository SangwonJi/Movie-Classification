# 📽️ 영화 분류 프로젝트 (Movie Classification Project)

## 프로젝트 개요
주어진 영화 대본 테이블에서 특정 단어의 사용 빈도를 통해 영화가 코미디인지 스릴러인지 예측하는 분류 모델을 구축하는 프로젝트입니다.

자연어 처리 및 기계 학습 기술을 활용하여 텍스트 데이터를 분석하고 예측 모델을 만들었습니다.

## 사용된 언어
- Python

## 주요 기능

### 데이터 로드 및 탐색
- `movies = Table.read_table('movies.csv')`: 영화 데이터셋을 로드하고 각 영화의 단어 빈도를 확인
- Bag-of-Words 모델을 사용하여 텍스트 데이터를 특징으로 변환

### 특징 선택 및 유클리드 거리 계산
- 특정 단어 특징을 선택하고 두 영화 간의 유사성을 결정하기 위해 유클리드 거리를 계산
```python
def distance(features_array1, features_array2):
    return sum((features_array1 - features_array2) ** 2) ** 0.5
```

### K-Nearest Neighbors (k-NN) 분류기 구현
- k-NN 알고리즘을 사용하여 영화 장르를 예측
```python
def classify(test_row, train_features, train_labels, k):
    # 주어진 영화와 가장 가까운 k개의 이웃을 찾고, 그 중 가장 흔한 장르로 예측
```

### 분류기 평가
- `test_guesses = test_my_features.apply(classify_feature_row)`: 전체 테스트 세트에 대해 분류기를 사용하여 정확성을 평가
- `proportion_correct = np.count_nonzero(test_guesses == test_movies.column("Genre")) / len(test_guesses)`: 예측 정확성을 측정

### 특징 선택 및 새로운 분류기 구축
- `new_features = make_array("oh", "well", "case", "murder", "happen")`: 더 효율적인 분류를 위해 새로운 특징을 선택
```python
def another_classifier(row):
    # 최대 5개의 단어만을 사용하여 새로운 분류기를 구축하고 평가
```

### 게임 시뮬레이션 및 전략 개발
- `play(strategy0, strategy1, update, score0, score1, dice, goal)`: 지정된 전략과 득점 규칙을 사용하여 두 플레이어 간의 전체 게임을 시뮬레이션 진행
- 다양한 전략을 구현하고 테스트하여 최적의 전략을 개발

### 인사이트
- 주사위 굴리기와 게임 결과를 통해 확률 및 통계 분석을 이해
- Python을 사용한 게임 메커니즘 및 규칙을 구현
- 시뮬레이션을 통한 전략 개발 및 평가를 수행
- 재귀 함수 (Recursion) 및 고차 함수 (Higher Order) 활용을 실습
- 자연어 처리, 기계 학습, 확률 분석에 대한 종합적인 연습을 진행
