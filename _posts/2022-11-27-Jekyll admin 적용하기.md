---
layout: post
title: Jekyll admin 적용하기

comments: true
---
# Jekyll admin 설치방법
프로젝트 파일 내의 Gemfile을 열어 마지막 줄에 다음 문구를 작성한다.

```
gem 'jekyll-admin', group: :jekyll_plugins
```

터미널로 프로젝트 폴더를 들어간 뒤, 다음 명령어를 실행한다.

```
bundle install
```

# Jekyll admin 사용방법
`bundle exec jekyll serve`를 실행한 후 브라우저에서 `http://127.0.0.1:4000/admin`을 접속한다.