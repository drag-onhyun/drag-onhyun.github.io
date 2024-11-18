---
title: "블로그 검색 엔진에 노출"
author: "Drag-onHyun"
date: 2024-11-18 00:00:00 +0900
categories: [Blog, 블로그 구축 과정]
---

## Google 검색 엔진에 노출

### step 1. Google Search Console에 블로그 등록

1. [Google Search Console](https://search.google.com/search-console/about) 접속 후 로그인
2. `시작하기` 버튼 클릭
3. 속성 유형 중 `URL 접두어` 선택 후 내 블로그 주소 입력 후 `계속` 버튼 클릭

### step 2. 소유권 확인

   - HTML 파일 추가
   - HTML 태그 추가
   - Google 애널리틱스
   - Google 태그 관리자
   - 도메인 이름 공급업체
1. 위 방법 중 `HTML 태그 추가` 사용
   → 이유: Jekyll 블로그에는 HTML 파일 추가의 방법으로는 적용이 어려울 수 있음.
2. HTML 태그 복사 
   → 아직 `확인` 버튼 클릭 X
   → 적용이 되지 않았기 때문에 에러 발생 가능
3. _config.yml에 `webmaster_verifications:`에 `google:`에 **HTML 태그의 content 부분** 붙여넣기

### step 3. 깃허브에 푸시

- 모든 변경사항 커밋 및 푸시
- 커밋 메시지 주의

### step 4. 소유권 확인

1. step 2의 2번에서 나온 `확인` 버튼 클릭
2. 소유권이 확인됐다는 작은 창이 뜸
3. 그 창에 있는 `속성으로 이동` 버튼 클릭

### step 5. 사이트맵 제출

1. 왼쪽에 있는 Sitemaps 탭 → 새 사이트맵 추가 → 사이트 주소 뒤에 `sitemap.xml` 작성 `제출` 버튼 클릭
2. 사이트맵이 제출됐다는 작은 창이 뜸

#### 사이트맵 제출 버그
1. 제출된 사이트맵 상태가 **가져올 수 없음**으로 표시
   → 화면 상의 버그이고 실제로는 정상적으로 동작함
  (길면 하루정도 뒤에 정상적으로 동작됨)

출처: [jaehee-kim24님의 블로그](https://jaehee-kim24.github.io/posts/github%EB%B8%94%EB%A1%9C%EA%B7%B8_%EA%B2%80%EC%83%89%EB%85%B8%EC%B6%9C%ED%95%98%EA%B8%B0/)

---

## Naver 검색 엔진에 노출

### step 1. Naver Search Advisor에 블로그 등록

1. [Naver Search Advisor](https://searchadvisor.naver.com/) 접속 후 로그인
2. 아래로 스크롤을 내려 `웹마스터 도구 사용하기` 버튼 클릭
3. 내 블로그 주소 입력 후 오른쪽 끝에 있는 `→` 버튼 클릭

### step 2. 소유권 확인

   - HTML 파일 추가
   - HTML 태그 추가
1. 위 방법 중 `HTML 태그 추가` 사용
   → 이유: 위의 `Google 검색 엔진에 노출`의 `step 2의 1번에서 설명`
2. HTML 태그 복사 
   → 아직 `소유확인` 버튼 클릭 X
   → 적용이 되지 않았기 때문에 에러 발생 가능
3. _config.yml에 `webmaster_verifications:`에 `naver:`를 만들어 **HTML 태그의 content 부분** 붙여넣기

### step 3. 깃허브에 푸시

- 모든 변경사항 커밋 및 푸시
- 커밋 메시지 주의

### step 4. 소유권 확인

1. step 2의 2번에서 나온 `소유확인` 버튼 클릭
2. 오류발생

#### 메타태그 인식 실패

1. `/_includes/head.html` 에 HTML 메타태그 전체를 `{{ seo_tags }}` 밑에 붙여넣기
2. `step 2` 3번에서 적은 코드 지우기 
3. `step 3` 다시 실행 후 `소유확인` 버튼 클릭
4. 소유권이 확인됐다는 작은 창이 뜸

### step 5. 사이트맵 제출

1. 왼쪽에 있는 요청 탭 → 사이트맵 제출 → 블로그 사이트 주소 뒤에 `sitemap.xml` 작성 `확인` 버튼 클릭
2. 아래에 제출된 사이트맵에 표시됨

#### 검색 불가
- Naver에 검색하면 며칠 후 검색 가능

출처: [jaehee-kim24님의 블로그](https://jaehee-kim24.github.io/posts/github%EB%B8%94%EB%A1%9C%EA%B7%B8_%EA%B2%80%EC%83%89%EB%85%B8%EC%B6%9C%ED%95%98%EA%B8%B0_naver/)