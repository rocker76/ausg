
### *Activation function*

### 정의
  - 뉴럴 네트워크의 개별 뉴런에 들어오는 입력신호의 총합을 출력신호로 변환하는 함수를 활성화 함수라고 합니다. 활성화 함수 유무는 초창기 모델일 퍼셉트론과 뉴럴네트워크의 유일한 차이점이기도 한다. 
  - 활성화 함수는 대개 비선형 함수 (non-linear function)를 사용합니다.
  - 선형 함수를 사용하지 않는 이유는? 
  > *선형 함수인 h(x)= cx 를 활성화 함수로 사용한 3 층 네트워크를 떠올려 보세요. 이를 식으로 나타내면 y(x)=h(h(h(x)))가 됩니다. 이는 실은 y(x)=ax와 똑같은 식입니다. a=c^3이라고만 하면 끄이죠. 즉, 은닉층이 없는 네트워크로 표현할 수 있습니다. 뉴럴네트워크에서 층을 쌓는 혜택을 얻고 싶다면 활성화함수로는 반드시 비션형 함수를 사용해야 합니다. <'밑바닥부터 시작하는 딥러닝>*
  
  
### 종류
1. #### 시그모이드 함수(로지스틱 함수) : Curved in two directions, like the letter "S"
    - 수식 : $\sigma (wx+b)=\frac { { e }^{ wx+b } }{ 1+{ e }^{ wx+b } } $
    - 범위 : (0,1)
    - 시그모이드 함수는 완전히 값을 전달하지 않거나(0) 혹은 완전히 전달한다(1)는 특성 때문에 실제 인테의 뉴런과 유사하다고 생각되어 널리 사용되었으나, 현재는 점차 사용하지 않는 추세입니다. 
    - 이유 : 
    > Vanishing Gradient: sigmod함수는 뉴런의 활성화 값이 0 또는 1에 매우 가깝다면 해당 편미분 값이 0에 매우 가까워지는 특성이 있습니다. 인공신경망의 back propagation에서 가장 일반적으로 사용되는 gradient descent의 경우 chain rule을 이용하는데, 이 과정에서 0에서 매우 작은 갑싱 계속 곱해진다면 그 값은 0 으로 점점 더 수렴합니다. 즉, 학습의 결과가 back propagation 과정에서 전달되지 못하고 이에 따라 weight 값의 조정이 이루어지지 않습니다. 이는 학습의 과정에 문제가 됩니다. 그럼 우리의 신경망 모델의 정확도는 감소한다. 이것이 vanishing gradient problem입니다.
    
    