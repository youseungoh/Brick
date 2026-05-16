# 🧱 벽돌깨기 게임 (Brick Breaker)

> Design Code Lab의 첫 바이브코딩 프로젝트 — HTML5 Canvas로 만든 클래식 아케이드 게임

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![License](https://img.shields.io/badge/License-All_Rights_Reserved-red.svg)

추억의 벽돌깨기 게임을 순수 바닐라 자바스크립트와 HTML5 Canvas만으로 구현한 단일 파일 웹게임입니다. 외부 라이브러리 없이 100% 네이티브 기술로 작동하며, 데스크톱·모바일 모두 지원합니다.

---

## ✨ 주요 기능

- 🎮 **3가지 조작 방식 지원** — 키보드 방향키, 마우스, 터치스크린
- 🌈 **컬러풀한 5층 벽돌** — 빨강·주황·노랑·초록·파랑의 무지개 그라데이션
- 💖 **생명 시스템** — 3번의 기회로 진행되는 클래식 룰
- 🎯 **반응형 패들 물리 엔진** — 패들에 닿는 위치에 따라 공이 튕기는 각도가 달라집니다
- 🏆 **클리어 / 게임 오버 화면** — 시각적 피드백으로 게임 상태를 명확히 안내
- 📱 **모바일 친화적** — 터치 이벤트 완벽 지원
- 🔄 **레거시 브라우저 호환** — `roundRect` 미지원 브라우저용 폴리필 내장

---

## 🚀 시작하기

### 필요 환경

- 모던 웹브라우저 (Chrome, Edge, Safari, Firefox)
- 별도의 빌드 도구나 의존성 없음

### 실행 방법

```bash
# 1. 저장소 클론
git clone https://github.com/your-username/brick-breaker.git

# 2. 폴더 진입
cd brick-breaker

# 3. index.html을 브라우저로 열기
open index.html      # macOS
start index.html     # Windows
xdg-open index.html  # Linux
```

또는 `index.html` 파일을 더블클릭하기만 하면 즉시 실행됩니다.

---

## 🎮 게임 조작법

| 입력 장치 | 조작 |
|---------|------|
| ⌨️ 키보드 | `←` `→` 방향키로 패들 이동 |
| 🖱️ 마우스 | 마우스 좌우 이동으로 패들 제어 |
| 👆 터치 | 화면을 좌우로 드래그 |
| ⏯️ 재시작 | `Space` 키 또는 "다시 시작" 버튼 |

### 게임 규칙

1. 패들로 공을 튕겨 화면 상단의 벽돌을 모두 깨뜨립니다
2. 공을 떨어뜨리면 생명이 1개 감소합니다
3. 생명이 0이 되면 게임 오버
4. 모든 벽돌을 깨면 클리어!

---

## 🛠️ 기술 스택

| 분야 | 기술 |
|-----|------|
| 렌더링 | HTML5 Canvas API |
| 로직 | Vanilla JavaScript (ES6+) |
| 스타일 | CSS3 (Radial Gradient, Box Shadow) |
| 애니메이션 | `requestAnimationFrame` |
| 입력 처리 | KeyboardEvent, MouseEvent, TouchEvent |

---

## 📁 프로젝트 구조

```
brick-breaker/
└── index.html      # 모든 코드가 담긴 단일 파일
    ├── <style>     # 게임 UI 스타일
    ├── <canvas>    # 게임 렌더링 영역 (720 × 480)
    └── <script>    # 게임 로직
```

### 핵심 함수 구성

```javascript
makeBricks()           // 벽돌 배열 초기화
drawBall()             // 공 렌더링 (하이라이트 포함)
drawPaddle()           // 패들 렌더링
drawBricks()           // 벽돌 렌더링
drawScore()            // 점수·생명·레벨 UI
collisionDetection()   // 공-벽돌 충돌 판정
draw()                 // 메인 게임 루프
restartGame()          // 게임 리셋
```

---

## 🎨 게임 설정값

`index.html` 상단의 변수를 수정하면 난이도와 외형을 자유롭게 커스터마이징할 수 있습니다.

```javascript
let ballRadius = 10;          // 공 크기
const paddleWidth = 120;      // 패들 너비
const paddleHeight = 14;      // 패들 높이
const brickRowCount = 5;      // 벽돌 행 수
const brickColumnCount = 9;   // 벽돌 열 수
let dx = 4; let dy = -4;      // 공 초기 속도
let lives = 3;                // 시작 생명
```

색상 팔레트는 `drawBricks()` 함수 내부에서 변경 가능합니다.

```javascript
const colors = ["#f87171", "#fb923c", "#facc15", "#4ade80", "#60a5fa"];
```

---

## 🗺️ 로드맵

향후 추가 예정 기능들입니다.

- [ ] 아이템 시스템 (멀티볼, 패들 확장, 레이저)
- [ ] 사운드 이펙트 및 배경음악
- [ ] 최고 점수 LocalStorage 저장
- [ ] 레벨별 벽돌 패턴 다양화
- [ ] 파티클 이펙트 (벽돌 파괴 시)
- [ ] 일시정지 기능
- [ ] 난이도 선택 화면

---

## 💡 학습 포인트

이 프로젝트는 바이브코딩 입문자에게 다음과 같은 개념을 가르치는 좋은 예제입니다.

- Canvas 2D Context로 도형 그리기
- 게임 루프와 `requestAnimationFrame`의 원리
- 충돌 감지 알고리즘 (AABB)
- 키보드·마우스·터치 이벤트 핸들링
- 2D 벡터 기반 물리 시뮬레이션 기초
- 브라우저 호환성을 위한 폴리필 작성

---

## 👨‍💻 개발자

**Seungoh You** — Design Code Lab

> 가르치며 배우고, 만들며 성장합니다.

---

## 📄 라이선스

```
Copyright © Seungoh You. All rights reserved.
```

이 프로젝트는 교육 및 학습 목적으로 자유롭게 참고할 수 있으나, 무단 재배포 및 상업적 이용은 금지됩니다.

---

<div align="center">

### 🎮 Made with ❤️ and Vibe Coding

`첫 줄의 코드가 모든 위대한 프로젝트의 시작입니다`

</div>
