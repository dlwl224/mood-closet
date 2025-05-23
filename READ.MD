# 인터넷 기초\[04] 과제2 - 나만의 인공지능 서비스

## 개요

* **서비스 명** : <span style="background-color:rgb(126,91,239)">Mood Closet</span>
* **서비스 설명** : 사용자로부터 **이름**, **성별**, **오늘 기분**, **현재 날씨**를 입력받으면, <span style="background-color:rgb(126,91,239)">Mood Closet</span>은 그 정보에 어울리는 오늘의 옷 코디를 감성적이면서도 현실적으로 추천해 주는 AI 스타일러입니다.
* **서비스 접속 주소** : [https://your-github-username.github.io/mood-closet]

---

## 서비스 구성 요소(1) - Gemini API

* 코디 추천 문장은 구글의 LMM 모델인 **Gemini API**를 활용해 생성합니다.
* **활용 모델** : Gemini-2.0-flash
* **시스템 프롬프트 주안점** :

  * 20년 경력의 패션 코디 전문가 역할 부여
  * 상의·하의·신발·아우터 중심의 현실적인 조합 제안
  * 스타일 키워드를 **해시태그** 형태로 제시
  * 마지막에는 **감성적인 한 줄 코멘트**로 마무리

---

## 서비스 구성 요소(2) - 프론트엔드

* **HTML**, **CSS**, **JavaScript**로 사용자가 값을 입력하고 결과를 확인할 수 있는 웹 페이지를 구현하였습니다.
* 메인 페이지 (`index.html`)와 스타일 시트 (`style.css`)로 구성되며, **GitHub Pages**로 배포되었습니다.
* 주요 UI 요소:

  * 이름, 성별, 기분, 날씨 입력 폼
  * 추천 결과 출력 영역
  * 반응형 레이아웃 및 그라데이션 버튼 디자인

---

## 서비스 구성 요소(3) - 백엔드

* 사용자 요청을 받아 Gemini API를 호출하고 결과를 반환하는 **서버리스 함수**를 Vercel에 배포하였습니다.
* **Node.js**, **@google/genai**, **dotenv** 라이브러리를 사용하여 API 키를 안전하게 관리합니다.
* 엔드포인트: `/api/ootdAI`

```bash
# 주요 파일
api/ootdAI.js    # 요청 처리 및 Gemini 호출 로직
.vercel.json     # 라우팅 설정
.env             # GEMINI_API_KEY 설정 (배포 시 환경 변수로 등록)
```

---

## 사용 방법

1. **웹 페이지 접속**: [https://your-github-username.github.io/mood-closet](https://your-github-username.github.io/mood-closet)
2. **입력**: 이름 · 성별 · 오늘 기분 · 현재 날씨 선택
3. **추천받기** 버튼 클릭
4. **추천 결과**: AI가 제안하는 상의/하의/신발/아우터 코디와 스타일 해시태그, 감성 코멘트 확인

---

## GitHub 레포지토리

* **프론트엔드**: [https://github.com/your-github-username/mood-closet](https://github.com/your-github-username/mood-closet)
* **백엔드**: [https://github.com/your-github-username/mood-closet-api](https://github.com/your-github-username/mood-closet-api)

---

© 2025 Mood Closet. All rights reserved.
