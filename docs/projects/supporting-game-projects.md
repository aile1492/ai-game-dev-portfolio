# AI와 함께 만든 게임

게임을 직접 기획하고 구현하며 AI를 협업 도구로 활용한 개인 프로젝트입니다. 대표 프로젝트인 Word Bloom을 먼저 소개하고, Sweet Crunch와 2048 Puzzle이 이를 보완합니다.

## Word Bloom: 대표 프로젝트

기획부터 구현, 일부 그래픽 제작, Android 빌드와 Google Play 출시까지 혼자 진행한 단어 퍼즐 게임입니다.

- 단어 퍼즐 규칙과 글자 배치 구현
- 화면 흐름, 저장과 모바일 조작 대응
- ComfyUI를 활용한 일부 그래픽 제작
- AI를 기획, 구현 보조, 코드 검토와 문서화에 활용
- Google Play 출시 완료

[Google Play](https://play.google.com/store/apps/details?id=com.wordbloom.game) · [GitHub 저장소](https://github.com/aile1492/word-bloom)

## Sweet Crunch

같은 그림의 블록을 3개 이상 연결하는 디저트 테마 퍼즐 게임입니다.

- 보드 교환, 같은 그림 찾기, 제거와 연쇄 처리
- 특수 블록과 장애물
- 점수, 이동 횟수와 목표 처리
- 규칙을 조합해 레벨을 만드는 데이터 구조
- TypeScript와 Phaser 3 사용

[GitHub 저장소](https://github.com/aile1492/sweet-crunch)

## 2048 Puzzle

같은 숫자 블록을 합쳐 더 큰 숫자를 만드는 퍼즐 게임입니다.

- 이동, 합치기, 점수 계산과 종료 규칙
- 여러 게임 모드
- 테스트 가능한 게임 로직과 화면 표현 분리
- 팝업을 열어도 게임 상태가 유지되는 화면 구조
- Godot와 GDScript 사용

[웹에서 실행](https://aile1492.github.io/2048-puzzle-web) · [GitHub 저장소](https://github.com/aile1492/2048-puzzle)
