---
layout: post
title: Asyncronous
categories: [Android]
comments: true
---
# 안드로이드 비동기 처리
### 1. 동기와 비동기
* 동기 (synchronous)
: '요청'과 '결과'가 동시에 발생
: 즉, 요청에 대한 **처리 시간과는 상관없이** '결과'를 반환해주어야 함.
    * 장점: 설계가 간단하고 직관적
    * 단점: 결과가 주어질 때까지 다른 작업들이 실행되지 않음
    
    예) A의 대화 종료 후, B의 대화 시작 

* 비동기 (asynchronous)
'요청'과 '결과'가 동시에 발생하지 않음
    * 장점: '요청'에 대한 결과가 반환되는 시간동안 다른 작업을 진행할 수 있음
    * 단점: 설계가 동기보다 복잡함

    예) A의 대화 도중에 B가 대화 시작

### 2. 메인 쓰레드(UI Thread)와 비동기 처리
* UI Thread 기능
: 안드로이드 어플리케이션 UI(Button, TextView, RecyclerView 등)는 UI Thread라고 불리는 '메인 쓰레드'가 관여하고 처리
: '데이터를 다운로드하는 버튼 + 다운로드 행위'를 메인 쓰레드에서 작업 시, 
다운로드를 하는 동안에 앱에 있는 다른 UI들의 이벤트 처리가 먹통이 됨.

* 비동기 처리
: 비동기 처리를 통해서 위와 같은 문제를 해결
    * 메인 쓰레드: UI 처리 
    * Async Task: 실질적인 작업 수행

### 3. Async Task란?
: 메인 쓰레드 작업을 좀 더 효율적이게 해줄 수 있는 백그라운드 기법
: 작업 진행이 수 초간 진행될 때 추천
: 오랜 시간이 걸리는 작업의 경우, Async Task가 아닌  java.util.concurrent패키지에서 제공하는 Executor, ThreadPoolExecutor 및 FutureTask 추천



