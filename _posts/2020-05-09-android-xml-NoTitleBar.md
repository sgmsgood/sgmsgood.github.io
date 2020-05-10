---
layout: post
title: app style 지정하기
categories: [Android_XML]
comments: true
---
# 타이틀 바 없애기
(res -> style)
```kotlin
<resources>
    <style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">

    // 모바일 타이틀 바
    <item name="colorPrimary">@color/colorPrimary</item>
    // 모바일 상태 표시줄 
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
    //que
        <item name="colorAccent">@color/colorAccent</item>

    //모바일 타이틀 바 제거
        <item name="windowNoTitle">true</item>

</resources>
```