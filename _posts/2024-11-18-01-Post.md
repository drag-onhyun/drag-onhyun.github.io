---
title: "블로그에 우터런스(Utterances) 적용"
author: "Drag-onHyun"
date: 2024-11-18 00:00:00 +0900
categories: [Blog, 블로그 구축 과정]
---

GitHub Pages 블로그에 **우터런스(Utterances)**를 적용하면, 블로그 포스트에 GitHub Issues 기반의 댓글 시스템을 손쉽게 추가할 수 있습니다.  
이 글에서는 우터런스를 블로그에 적용하는 구체적인 과정을 설명합니다.

---

## 우터런스(Utterances) 적용 과정

### Step 1. GitHub 저장소 준비

1. 댓글을 적용할 GitHub 저장소 준비
   - 새 저장소를 생성하거나 기존 저장소를 사용할 수 있습니다.
   - 저장소는 **Public**으로 설정해야 합니다.

2. Issues 탭 활성화
   - GitHub 저장소의 **Settings** → **General** → **Features**에서 **Issues**를 활성화합니다.  
   - Issues 탭이 비활성화된 경우, 우터런스가 작동하지 않습니다.

### step 2. 우터런스 설치

1. [utterances 앱 설치](https://github.com/apps/utterances)
   - 링크를 클릭하여 우터런스 앱을 설치합니다.
   - 설치 과정에서 댓글 데이터를 저장할 저장소를 선택합니다.
2. 설치 시 선택 사항:
   - **All Repositories**: 모든 저장소에 적용.
   - **Only Select Repositories**: 특정 저장소에만 적용.  
     → 이 옵션을 선택하고, 댓글용 저장소를 지정합니다.

3. 설치 완료 후, 아래처럼 설정합니다:
   - **Theme**: 우터런스 테마 선택.
   - **Repo**: 댓글 데이터를 저장할 GitHub 저장소 경로 입력.

### step 3. 블로그에 우터런스 적용

#### 우터런스 HTML 스크립트 추가
- 블로그 프로젝트의 `_config.yml` 파일에 `comments`에 아래 코드를 추가합니다:

```yaml
 provider: "utterances"
 utterances:
  repo: "drag-onhyun/drag-onhyun.github.io"
  issue_term: "pathname"
```
### step 4. 깃허브에 푸시
- 모든 변경사항 커밋 및 푸시
- 커밋 메시지 주의
- 사이트 반영 확인 (예시: `https://karina.github.io`)

출처: [ansohxxn님의 블로그](https://ansohxxn.github.io/blog/utterances/#1-%EB%8C%93%EA%B8%80-issue-%EA%B0%80-%EC%98%AC%EB%9D%BC%EC%98%AC-%EC%A0%80%EC%9E%A5%EC%86%8C%EB%A5%BC-%EC%A0%95%ED%95%98%EA%B1%B0%EB%82%98-%ED%98%B9%EC%9D%80-%EC%83%9D%EC%84%B1%ED%95%9C%EB%8B%A4)