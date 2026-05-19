![Windows](https://img.shields.io/badge/platform-Windows-blue)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# AI Usage Monitor

![Screenshot](.github/animation.gif)

Claude Code, Codex, Gemini, Antigravity를 포함한 여러 AI 도구들의 사용량을 모니터링하기 위한 가벼운 Windows 작업 표시줄 위젯입니다.

터미널이나 제공자 웹사이트를 열 필요 없이, 작업 표시줄에 자리 잡아 남은 사용량 한도를 바로 보여줍니다.

## 주요 기능 (What You Get)

- Claude Code, Codex, Gemini, Antigravity 한도에 대한 실시간 사용량 표시줄 제공
- 각 한도가 초기화될 때까지의 실시간 카운트다운 (예: 세션 및 주간 윈도우)
- Windows 작업 표시줄에 직접 표시되는 작고 네이티브한 위젯
- 활성화된 모델의 사용량 퍼센트를 보여주는 시스템 트레이 아이콘 배지
- 트레이 아이콘을 좌클릭하여 작업 표시줄 위젯을 켜거나 끌 수 있음
- 우클릭 옵션을 통한 새로고침, 표시할 모델 선택, 업데이트 빈도, 언어, 시작프로그램 등록, 업데이트 기능 제공

## 권장 대상 (Who This Is For)

이 앱은 **Claude Code**, **Codex**, **Gemini**, 또는 **Antigravity**와 같은 CLI나 앱 기반 AI 도구를 사용하는 Windows 사용자를 위해 만들어졌습니다.

우클릭 **Models** 메뉴에서 모든 모델을 개별적으로 켜거나 끌 수 있습니다.

"내 남은 한도가 얼마지?"를 항상 띄워놓고 간단히 확인하고 싶은 분들에게 가장 유용합니다.

## 요구 사항 (Requirements)

- Windows 10 또는 Windows 11
- 지원되는 AI 도구 중 최소 한 개 이상이 설치 및 인증되어 있어야 함 (Claude Code, Codex, Gemini, 또는 Antigravity)

WSL을 통해 이러한 도구들을 사용하는 경우에도 지원됩니다. 모니터링 앱은 Windows 또는 WSL 환경에서 자격 증명을 읽을 수 있습니다.

## 설치 (Install)

WinGet을 사용하여 최신 버전을 설치하세요:

```powershell
winget install CodeZeno.ClaudeCodeUsageMonitor
```

WinGet을 사용하고 싶지 않으시다면, [Releases](https://github.com/CodeZeno/Claude-Code-Usage-Monitor/releases) 페이지에서 최신 `claude-code-usage-monitor.exe` 파일을 다운로드하여 직접 실행하실 수 있습니다.

## 사용법 (Use)

WinGet으로 설치한 후 다음 명령어를 실행하세요:

```powershell
claude-code-usage-monitor
```

실행되면 작업 표시줄과 알림 영역의 시스템 트레이 아이콘으로 표시됩니다.

- 왼쪽 구분선을 드래그하여 작업 표시줄 위젯의 위치를 이동할 수 있습니다.
- 작업 표시줄 위젯이나 트레이 아이콘을 우클릭하여 새로고침, 표시 모델, 업데이트 주기, Windows 시작 시 실행, 위치 초기화, 언어, 업데이트, 종료 등의 메뉴를 사용할 수 있습니다.
- 트레이 아이콘을 좌클릭하여 작업 표시줄 위젯을 켜거나 끌 수 있습니다.
- 로그인할 때 자동으로 앱을 실행하려면 우클릭 메뉴에서 `Start with Windows`를 활성화하세요.

### 모델 (Models)

우클릭 **Models** 메뉴를 사용하여 위젯에 표시할 항목을 선택할 수 있습니다:

- **Claude Code**, **Codex**, **Gemini**, **Antigravity**를 개별적으로 활성화하거나 비활성화할 수 있습니다.

여러 모델이 표시될 때 각 모델은 고유의 사용량 표시줄과 그에 맞는 텍스트 색상을 가지며, 접두사(C, X, G, A)로 구분됩니다.

### 시스템 트레이 아이콘 (System Tray Icon)

트레이 아이콘은 현재 세션 사용량을 퍼센트 배지로 표시합니다.

활성화된 각 모델마다 개별적인 트레이 아이콘이 표시됩니다. 각 모델의 트레이 아이콘은 해당 브랜드나 테마 색상에 맞춘 고유한 스타일을 사용합니다.

트레이 아이콘에 마우스를 올리면(Hover) 해당 모델의 구체적인 사용량 값이 표시됩니다.

## 진단 (Diagnostics)

시작이나 화면 표시와 관련된 문제를 해결하려면 다음 명령어로 실행하세요:

```powershell
claude-code-usage-monitor --diagnose
```

다음 경로에 로그 파일이 작성됩니다:

```text
%TEMP%\claude-code-usage-monitor.log
```

설정은 다음 경로에 저장됩니다:

```text
%APPDATA%\ClaudeCodeUsageMonitor\settings.json
```

## 계정 지원 (Account Support)

이 앱은 각 CLI가 지원하는 것과 동일한 계정 유형을 지원합니다.

**2026년 3월 19일** 기준, Anthropic의 Claude Code 설정 문서에 따르면:

- **지원됨:** Pro, Max, Teams, Enterprise, Console 계정
- **지원되지 않음:** 무료 Claude.ai 플랜

만약 Anthropic이 향후 Claude Code의 가용성을 변경하더라도, 동일한 인증 엔드포인트를 통해 사용량 데이터가 계속 노출되는 한 이 앱은 Claude Code가 지원하는 모든 사항을 동일하게 따릅니다.

## 프라이버시 및 보안 (Privacy And Security)

이 프로젝트는 **오픈 소스**이므로 앱이 어떤 동작을 하는지 정확히 검사하실 수 있습니다.

앱이 읽어들이는 데이터:

- 지원되는 AI 도구들의 로컬 OAuth 자격 증명 및 환경 설정 (예: `~/.claude/.credentials.json`, Codex `auth.json`, Gemini 및 Antigravity 설정 파일)
- 필요한 경우, 설치된 WSL 배포판 내의 동일한 자격 증명 파일

앱이 네트워크를 통해 전송하는 데이터:

- 사용량 및 속도 제한(Rate-limit) 정보를 읽기 위해 각 제공자의 엔드포인트로 보내는 요청
- 앱의 업데이트 확인 / 자동 업데이트 기능을 사용할 때만 GitHub로 보내는 요청
- `HTTPS_PROXY`, `HTTP_PROXY`, 또는 `ALL_PROXY`와 같은 프록시 환경 변수가 설정된 경우, 이러한 아웃바운드 요청은 해당 프록시를 사용할 수 있습니다.

앱이 로컬에 저장하는 데이터:

- 위젯 위치
- 폴링(Polling) 빈도
- 언어 설정
- 마지막 업데이트 확인 시간
- 표시 모델 설정

앱이 **하지 않는** 행동:

- 자격 증명을 다른 타사 서버로 전송하지 않습니다.
- 별도의 백엔드 서비스를 사용하지 않습니다.
- 분석(Analytics)이나 텔레메트리 데이터를 수집하지 않습니다.
- 프로젝트 파일을 업로드하지 않습니다.
- 자격 증명 파일을 직접 수정하지 않습니다.

참고 사항:

- 토큰이 만료된 경우, 앱이 백그라운드에서 해당 제공자의 로컬 CLI에 토큰 갱신을 요청할 수 있습니다. 모니터 앱은 자격 증명 파일을 직접 작성하지 않으며, 모든 갱신 처리는 CLI에 의해 수행됩니다.
- 포터블(Portable) 버전의 경우 이 저장소에서 최신 릴리즈를 다운로드하여 스스로 업데이트할 수 있습니다.
- 프록시 사용 시, 사용량 요청에는 TLS 연결 내부에 OAuth 베어러 토큰(Bearer token)이 포함되어 전송되므로 신뢰할 수 있는 프록시를 사용해야 합니다.

## 작동 방식 (How It Works)

모니터링 앱은 다음과 같이 작동합니다:

1. 활성화된 모델의 로그인 자격 증명을 찾습니다.
2. 각 제공자로부터 현재 사용량을 읽어옵니다.
3. Windows 작업 표시줄에 결과를 직접 표시합니다.
4. 백그라운드에서 주기적으로 새로고침합니다.

만약 최신 사용량 엔드포인트를 사용할 수 없는 경우, Claude의 Messages API 등이 반환하는 속도 제한(Rate-limit) 헤더를 읽어오는 방식으로 대체(Fall back)할 수 있습니다.

## 오픈 소스 (Open Source)

이 프로젝트는 MIT 라이선스를 따릅니다.

동작을 점검하거나 코드를 감사(Audit)하고 싶으시다면 이 저장소의 모든 것을 확인하실 수 있습니다.
