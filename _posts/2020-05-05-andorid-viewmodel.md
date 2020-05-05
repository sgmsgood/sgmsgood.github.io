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

2. 사용법 </br>
 1) 의존성 설정하기 'build.gradle (:app)'
```kotlin
implementation "android.arch.lifecycle:extensions:1.1.1"
```
 2) ViewModel 클래스 작성
```kotlin
class Test1ViewModel: ViewModel() {
    var user: MutableLiveData<User1>;

    fun getUser(): MutableLiveData<User1> { 
        if (user == null) {
            user = MutableLiveData<User1>()
            user.postValue(User("gildong", "hong"))
        }
        return user
    }
}
```
 3) 선언된 뷰모델 이용하기 (activity)
```kotlin
private lateinit var user: Test1ViewModel

private fun initViewModel() {
    activity?.let{
        val factory = ViewModelProvider.AndroidViewModelFactory.getInstance(it.application)
        user = ViewModelProvider(it, factory).get(Test1ViewModel::class.java)
        user.getUser()
 
        user.getUser().observe(this, user -> {
            
        })
    }
}
```
