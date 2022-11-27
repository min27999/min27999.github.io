---
layout: post
title: Google Analytics 적용하기

comments: true
---
# Google Analytics란
Google Analytics란, 구글에서 제공하는 무료 웹분석 서비스이다.

이 서비스를 이용하면 방문자 통계 등의 자료를 쉽게 얻어낼 수 있다.

# GitHub 블로그에 적용하는 방법
먼저 [Google Analytics](https://analytics.google.com)에 접속해서 가입을 진행한다.

가입 후에 우리가 필요한 정보는 측정 ID이다. 측정 아이디는 'G-'로 시작한다.

이제 이 코드를 깃허브 블로그에 적용시켜야 한다.

총 두 개의 파일을 수정할 것이다.

먼저 lanyon 테마를 기준으로 프로젝트 폴더 안을 보면, _includes 폴더가 있다. 이 폴더 안에 있는 head.html을 연다.

head.html 파일에는 이미 Google Analytics 관련 코드가 있다. 하지만 기본 상태로는 작동하지 않는다.

`ga('create', ~~~~~)`, `ga('send', ~~~~)` 부분에서 ga를 gtag로 수정해준다. 그리고 아래 코드도 추가해준다.

```
<script async src="https://www.googletagmanager.com/gtag/js?id=측정 ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', '측정 ID');
</script>
```
이제 config 파일을 수정할 차례이다.
_config.yml 파일에 다음 코드를 추가해준다.

```
analytics:
  provider               : "google" 
                          # false (default), "google", "google-universal", "google-gtag", "custom"
  google:
    tracking_id          : "측정 ID"
    anonymize_ip         : true
                            # true, false (default)
```
깃허브에 업로드 하면 정상작동할 것이다.