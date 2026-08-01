# 🏃 우송 걷뛰 (Woosong Walk-Run)

우송대학교 주변에서 걷기/러닝을 시작하는 초심자를 위한 **6개월(26주) 플랜 PWA 앱**입니다.

- 🎯 목표: 종아리 근육 재활 → 심폐지구력 → 체중 감량 → 30분 연속 조깅
- 🗺️ 우송대 주변 실제 코스 5곳 (대동천 · 대전천 둔치 · 우암사적공원 · 캠퍼스 트랙 · 계족산)
- 📅 단계별 주차 계획 + 기간별 예상 신체 변화
- ✍️ 운동 기록 + 종아리 상태 트래킹 (데이터는 내 폰에만 저장됨)
- 📱 홈 화면에 추가하면 일반 앱처럼 실행, 오프라인에서도 동작

## GitHub Pages로 배포하기

이미 GitHub 계정과 git 기본 사용법을 알고 있다는 전제의 안내입니다.

### 1. 저장소 만들기

GitHub에서 **New repository** → 이름은 예를 들어 `woosong-walkrun` → **Public** → Create.

### 2. 코드 올리기

이 폴더 안에서:

```bash
git init
git add .
git commit -m "우송 걷뛰 첫 배포"
git branch -M main
git remote add origin https://github.com/<내아이디>/woosong-walkrun.git
git push -u origin main
```

### 3. GitHub Pages 켜기

저장소 페이지 → **Settings** → 왼쪽 메뉴 **Pages** →
**Source**: `Deploy from a branch` → **Branch**: `main`, 폴더 `/ (root)` → **Save**.

1~2분 후 `https://<내아이디>.github.io/woosong-walkrun/` 에서 앱이 열립니다.

### 4. 폰 홈 화면에 설치 (PWA)

- **안드로이드(크롬)**: 위 주소 접속 → 메뉴(⋮) → **홈 화면에 추가** (또는 "앱 설치" 배너)
- **아이폰(사파리)**: 위 주소 접속 → 공유 버튼 → **홈 화면에 추가**

이후 홈 화면 아이콘으로 열면 주소창 없는 앱 형태로 실행됩니다.

## 파일 구성

```
index.html     # 앱 전체 (화면 + 로직, 단일 파일)
manifest.json  # PWA 설치 정보 (이름, 아이콘, 테마색)
sw.js          # 서비스 워커 (오프라인 캐시)
icons/         # 앱 아이콘 (192px, 512px)
```

## 수정하고 싶을 때

- **운동 계획 수정**: `index.html`의 `PHASES` 배열 (주차별 처방 텍스트)
- **코스 추가/수정**: `index.html`의 `COURSES` 배열
- **색상 변경**: `index.html` 상단 `:root`의 CSS 변수
- 수정 후 `git add . && git commit -m "수정" && git push` 하면 1~2분 내 반영됩니다.
- `sw.js`의 `CACHE` 버전 문자열(`v1` → `v2`)을 올리면 폰에 캐시된 옛 버전이 확실히 갱신됩니다.

## ⚠️ 주의

이 앱의 계획과 예상 변화는 일반적인 초심자 가이드라인 기반의 참고용입니다.
종아리 **저림이 반복되거나 쉬어도 가라앉지 않으면** 혈관·신경 문제일 수 있으니
운동 강도를 올리기 전에 정형외과/혈관외과 진료를 먼저 받아 보세요.
