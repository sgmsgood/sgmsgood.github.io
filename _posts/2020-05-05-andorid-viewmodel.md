---
layout: post
title: ViewModel
categories: [Android]
comments: true
---
## MVVM (Model-View-ViewModel)
1. ViewModel 이란?
- ViewModel: 모델과 뷰의 중간에 뷰모델을 두어 뷰에서 뷰모델에 일을 시키고, 뷰모델은 모델을 이용
- 뷰 (업무 처리해줘 뷰모델!) -> 뷰모델 (모델아 도와줘) -> 모델 (업무 로직 처리)

2. 사용법
 1) 의존성 설정하기 'build.gradle (:app)'
```java
implementation "android.arch.lifecycle:extensions:1.1.1"
```