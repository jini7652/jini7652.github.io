## 유명 CNN Architecture
CNN에 대한 이해를 좀 더 깊게 하기 위해 유명 CNN Architecture에 대해 하나씩 살펴보겠다.
(상세한 설명한 추후에 다루어보도록 하겠다.)

### LeNet
- Yann LeCun이 1990년대 발표한 구조로, 처음에 CNN이라는 개념을 성공적으로 도입
- 주로 우편번호나 숫자 등을 인식하기 위해 개발

### AlexNet
- Computer Vision 분야에서 CNN이 널리 적용되도록 한 계기가 된 구조.
- CNN 분야에서 유명한 Krizhevsky와 Hinton 등에 의해 개발
- 2012년 ImageNet ILSVRC 대회에서 2위와 큰 성능차(AlexNet의 오차율은 16%, 2위의 오차율은 26%)를 보이며 우승.
- AlexNet의 구조는 LeNet과 유사하지만, 보통 Conv. Layer 다음에 Pooling(Sub-Sampling) Layer가 오는 기본 구조와는 달리, Conv. Layer 뒤에 Conv. Layer가 오는 점이 특이하다.

### ZF Net
- ILSVRC 2013년 대회에서 우승을 한 구조이며 뉴욕대의 Mathew Zeiler와 Rob Fergus에 의해서 개발됨.
- Zeiler와 Fergus의 앞 글자를 딴 ZF Net으로 알려지게 되었다.
- AlexNet의 Hyper-parameter를 수정하여 성능을 좀 더 개선.
- 특히 중간에 있는 Conv. Layer의 크기를 늘렸다.

### GoogLeNet
- ILSVRC 2014년 대회에서 우승한 구조
- Google의 Szegedy 등에 의해서 개발.
- `Inception Module` 개념을 도입하여 네트워크의 parameter 수를 대폭 줄일 수 있게 되었다.
(참고로 AlexNet은 60M 파라미터이지만, GoogLeNet의 경우 4M임.)

### VGGNet
- ILSVRC 2014년 대회에서 2등을 한 구조.
- 영국 Oxford 대학교의 Karen Simonyan과 Andrew Zisseman에 의해서 개발됨.
- 대량의 이미지를 인식함에 있어 네트워크 깊이(depth)가 정확도에 어떤 영향을 주는지 보여줌.
- 네트워크의 시작부터 끝까지 동일하게 3*3 Convolution과 2*2 Max Pooling을 사용하는 단순한(homogeneous)구조에서 depth가 16일 때 최적의 결과가 나오는 것을 보여줬다.
- GoogLeNet에 비해 분류 성능은 약간 떨어졌지만, 다중 전달 학습 과제에서는 오히려 더 좋은 결과를 나았다.
그러므로 CNN 연구 그룹에서는 VGGNet의 구조를 좀 더 선호하는 경향이 있다.

### ResNet
- ILSVRC 2015년 대회에서 우승한 구조
- MS의 Kaiming He 등에 의해 개발됨.
- 기존 DNN(Deep Neural Network)보다 layer 수가 훨씬 많은 Deeper NN에 대한 학습(Training)을 쉽게 할 수 있도록 해 주는 residual framework 개념을 도입함.

\* 참고로 ImageNet과 ILSVRC에 대해 간단히 소개를 하면 다음과 같다.

## ImageNet
세계 최대의 영상 데이터 베이스이며, 마치 사람이 보고 판단할 수 있는 것처럼 컴퓨터 비전을 연구하는 사람들이 벤치마크로 사용할 수 있는 영상 데이터 베이스이다. 현재 약 22000종으로 분류가 가능한 1500만장의 인터넷 기반의 영상이 확보되어 있다.
구성은 WordNet의 계층 구조를 따라 만들어졌으며 1개의 synset(synonym set)에 대해 평균 1000장 이상의 영상이 확보되어 있으며 사람들이 각각의 영상에 대해 label을 붙여놨기 때문에 머신러닝 기반의 computer vision 프로그램을 개발하거나 자신이 개발한 프로그램의 성능을 평가할 때 사용하기에 적합하다. ImageNet에 확보된 영상에 대해서는 저작권을 주장하지 않기 때문에 누구나 편안하게 다운로드하여 사용이 가능하다.
이 영상 데이터베이스는 2009년 Stanford 대학교의 Li Fei-Fei 교수가 중심이 되어 확보되었으며 현재는 여러 대학교 및 구글이나 마이크로소프트 같은 기업에서도 참여를 한다.

## ILSVRC
ImageNet Large Scale Visual Recognition Challenge의 약자.
ImageNet 영상 데이터베이스를 기반으로 computer vision 분야의 성능의 우열을 가리기 위한 대회
2010년부터 매년 열리고 있음.
이 대회를 통해 놀라운 성능을 보이는 논문들이 많이 발표가 됨에 따라 ImageNet은 점ㅁ차 대량 영상 인식분야에서 표준 벤치마트로 자리를 잡아가고 있음.
대회의 분야는 image classification, single-object localization 및 object detection으로 나뉜다.
Image classification과 single-object localization은 그림에 여러 개의 object가 있더라도 1개를 확실하게 구별할 수 있으면 맞은 것으로 처리.

단, localization의 경우 위치까지 찾아야 한다.
