---
title: "블로그에 고트카운터(goatcounter) 적용"
author: "Drag-onHyun"
date: 2024-11-18 00:00:00 +0900
categories: [Blog, 블로그 구축 과정]
---

## 고트카운터(goatcounter) 적용 과정

### step 1. 고트카운터 계정 생성

1. [GoatCounter 홈페이지](https://www.goatcounter.com/)에 접속
2. "Sign up" 버튼을 눌러 회원 가입
3. 회원 가입 완료 후 이메일을 확인하여 계정 검증

### step 2. 고트카운터 설정

1. 우측 상단에 있는 settings 을 누르고 들어가서 방문자가 조회수를 볼 수 있게 설정
2. 왼쪽 제일 아래에 꼭 save를 눌러주자.

### step 3. _config.yml 수정

1. 회원 가입할 때 썼던 내 코드 (서브도메인)을 적기

``` yaml
# Web Analytics Settings
analytics:
  google:
    id: 
  goatcounter:
    id: 내코드  # fill in your GoatCounter IDs
```
2. provider 에 goatcounter 를 할당

``` yaml
pageviews:
  provider: goatcounter # now only supports 'goatcounter'
```

### step 4. 깃허브에 푸시
- 모든 변경사항 커밋 및 푸시
- 커밋 메시지 주의
- 사이트 반영 확인 (예시: `https://karina.goatcounter.com/settings/main`)

출처: [ju-ing님의 블로그](https://blog.ju-ing.com/posts/jekyll-theme-chirpy-goatcounter/)