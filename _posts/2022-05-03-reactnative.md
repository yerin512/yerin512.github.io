---
layout: post
title: 리애트 네이티브 안드로이드 스튜디오 환경셋팅 
subtitle: React-Native
categories: Troubleshooting
tags: [TIL, React-Native, Troubleshooting]
---


리액트 네이티브 환경설정만 순수 시간으로 따지면 3일 걸린 거 같다.
구글링 미친듯이 하고 재설정하고 재설치하고 버전 업그레이드를 해도 안 되던 게 

`react-native doctor`

이거 하나에 끝났다.

![image](https://user-images.githubusercontent.com/73337811/166461186-e4f48ee2-a1d2-4c13-a59c-411a083667dd.png)



![image](https://user-images.githubusercontent.com/73337811/166461092-e72ee010-e1e0-41a0-87dd-42cc3538f12b.png)



분명 sdk android_home jdk
제대로 다 설치하고 환경변수까지 입력했는데도 다 x 표시되어있었는데
f랑 e 하고 재부팅 하니까 됐다.
Android SDK는 계속 fix 하고 error 고치기를 해도 N/A가 뜨길래 구글링하면서
한 번 run android 하니까 성공적으로 켜졌다.
