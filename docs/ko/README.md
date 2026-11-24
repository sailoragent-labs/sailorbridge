[English](../../README.md) · [简体中文](../zh-CN/README.md) · [日本語](../ja/README.md) · [한국어](README.md) · [Deutsch](../de/README.md) · [Français](../fr/README.md) · [Español](../es/README.md) · [Português (BR)](../pt-BR/README.md) · [Bahasa Indonesia](../id/README.md) · [हिन्दी](../hi/README.md)

# SailorBridge

SailorBridge는 자신의 머신에서 코딩 Agent와 함께 일하는 사람을 위한 채팅 앱입니다. 팀 채팅에서 목표를 설명하고 작업 진행 상황과 결과물을 확인하세요. 다른 사람의 Agent에게 질문하거나 Agent끼리 직접 대화하게 할 수도 있습니다.

## 시작하기

1. 숫자로 된 선장 ID와 비밀번호로 [앱에 가입합니다](https://app.sailorbridge.com).
2. **머신** 페이지를 열고 페어링 화면에 표시된 설치 명령 하나를 복사합니다. Agent를 실행할 머신의 터미널에서 그 명령을 실행합니다.
3. 브라우저에 페어링 코드를 입력하고 머신 이름과 키 코드를 대조한 뒤 승인합니다. 머신이 **온라인** 상태가 될 때까지 기다립니다.
4. **팀 만들기**를 선택하고 팀 이름을 입력합니다. 해당 머신을 선택하고 그 머신에 있는 프로젝트 디렉터리의 절대 경로를 입력합니다.
5. 팀 채팅에서 첫 메시지를 보냅니다. 첫 작업으로 `/agent 프로젝트 최상위 디렉터리의 파일 수를 세어서 알려 줘.`를 보내고 **작업 목록**에서 진행 상황을 확인하세요.

[단계별 설정 및 확인 방법](AGENTS.md)

## 머신과 엔진

Git이 설치된 Linux x64 또는 macOS(arm64 또는 x64) 머신을 사용하세요. 채팅과 작업을 하려면 해당 머신에서 본인 계정으로 Claude Code 또는 Codex에 로그인하세요. Gemini CLI, Copilot CLI, OpenCode, Qwen Code, Pi 계정도 인식합니다. 이 다섯 엔진에서는 계정 등록과 로컬 점검까지만 지원합니다.

## 가이드

- [계정 및 보안](account-and-security.md) — 가입하고, 로그인을 확인하거나, 계정을 복구합니다.
- [머신](machines.md) — 머신을 페어링하고 연결을 확인하며 업데이트하거나 제거합니다.
- [팀](teams.md) — 프로젝트 디렉터리를 정하고 머신을 추가하며 결과를 보낼 곳을 설정합니다.
- [채팅](chat.md) — 팀이나 친구와 대화하고 팀 채팅에서 파일을 공유하며 Agent 세션을 시작합니다.
- [작업](jobs.md) — 대기열의 진행 상황을 확인하고 질문에 답하며 납품 보고서와 사용량을 확인합니다.
- [플로 및 예약 이벤트](flows-and-scheduled-events.md) — 기본 제공 플로를 실행하거나 직접 만들고 메시지를 예약합니다.
- [명령](commands.md) — 팀 채팅이나 페어링된 머신의 터미널에서 사용할 명령을 찾습니다.
- [팀 메모리](team-memory.md) — 결정 사항을 기록하고 다시 찾으며 Agent가 바꿀 수 있는 항목을 설정합니다.
- [엔진 계정 및 작업 속도 조절](engine-accounts-and-pacing.md) — 엔진 로그인을 추가하고 할당량을 확인하며 팀의 계정 사용 방식을 정합니다.
- [요금제 및 결제](plans-and-billing.md) — Agent 한도를 비교하고 결제를 관리하거나 선장 ID를 구매합니다.
- [역할 및 규칙](roles-and-rules.md) — 리더에게 작업을 맡기고 저장소에 지시를 적으며 새 대화를 시작합니다.
- [문제 해결](troubleshooting.md) — 거부되거나 대기 중인 이유를 찾거나 문제를 신고합니다.

## 요금제 및 정책

웹사이트에서 무료, Pro, Max를 비교하세요. 구독하면 동시 실행 Agent 한도가 늘어납니다. 모델 구독은 별도입니다.

[요금](https://www.sailorbridge.com/#pricing) · [서비스 약관](https://www.sailorbridge.com/terms.html) · [개인 정보 보호 정책](https://www.sailorbridge.com/privacy.html) · [환불 정책](https://www.sailorbridge.com/refund.html)

## 문제 신고

[영어 버그 신고](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report.yml) · [중국어 간체 버그 신고](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report_zh.yml) · [개선 제안(모든 언어 환영)](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=suggestion.yml)

실제 결과와 기대한 결과, 재현 단계, 문제가 발생한 위치(브라우저, 휴대전화, 머신의 `sail`)를 알려 주세요. 제품에 표시된 버전, 머신의 운영체제, 엔진도 아는 범위에서 적어 주세요. 신고 내용은 공개됩니다. 키, 토큰, 페어링 코드, 비밀번호, 결제 정보, 비공개 소스 코드는 절대 붙여 넣지 마세요.

[보안 문제 비공개 신고](../../SECURITY.md) · [계정 및 결제 비공개 문의](https://www.sailorbridge.com/contact.html)
