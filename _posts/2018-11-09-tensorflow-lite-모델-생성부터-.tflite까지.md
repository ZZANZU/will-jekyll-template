---
layout: post
title: "TensorFlow Lite(1)"
date: 2018-11-09 03:54:51
image: '/assets/img/'
description: "TensorFlow Lite 모델 생성부터 .tflite까지 + Google Colab Files"
tags:
- TFLite
- Tensorflow
- Colab
categories:
- DeepLearning
- Tutorial
twitter_text:
---

이번 학기 프로젝트 중에 2개나 모바일에 딥러닝 모델을 사용해야할 필요가 생겨서(사실은 지난 학기에 텐서플로우 라이트를 맛본게 화근이었다...왠지 모를 자신감 상승...) 튜토리얼 정도 수준이 아닌 능동적인 수준의 실력이 필요하게 됐다.
TensorFlow-for-poet같은 구글 코드랩의 예제 앱들을 보면서 어떻게 이렇게 되는걸까 항상 궁금했는데, 한 번 기초부터(Linear Regression 모델) 적용해보고자 한다.

이 글을 준비하기 위해 여러 블로그 글과 유투브 강의들을 참고하였다.

## 당신이 이 글을 통해 배울 수 있는 것
1. 내가 만든 그래프를 freeze하기
2. 약간의 Google Colab



## 모델을 freeze한다?
모델을 freeze한다는 것은 weight나 bias값을 variable에서 constant로 만들어준다는 의미이다.(말그대로 출렁이던 모델을 꽁꽁 얼려버린다는 의미이다)

## 모델을 왜 freeze하는건데?
이유는 별거 없다.
1. 트레이닝 과정을 더이상 거치지 않고, 필요하지도 않다고 판단되어서.
2. 텐서플로우는 gradient값이나 meta data등을 만들어내게 되는데, 이러한 것들이 실제로 결과값을 inference하는 단계에서는 더이상 필요하지 않기 때문.
3. 모델의 파라미터들을 export하기위한 준비를 하려고.

## 어떻게 freeze하는데?
우선 예제 코드(라고 부를 정도로 기초탄탄 코드는 아니다. 죄송하다...) 링크이다.
https://colab.research.google.com/drive/1pHT172kXrhLCPBv-7YaVfoa47p-DLO73

