# 🔧 MCP 설정하기

## 🎯 목표

Kiro에 **AWS 문서 MCP**를 연결해서 AI가 외부 지식에 접근할 수 있게 만듭니다.

---

## 사전 준비: uv 설치 📦

MCP 서버를 실행하려면 **uv**가 필요합니다. 이미 설치되어 있는지 먼저 확인해봅시다.

### 설치 여부 확인

Kiro IDE 하단 터미널에서 아래 명령어를 입력하세요:

> 💡 터미널 여는 법: 상단 메뉴 **Terminal → New Terminal** 또는 `` Ctrl+` ``

```
uvx --version
```

- 버전이 나오면 → ✅ 설치 완료! Step 1로 넘어가세요
- "command not found" 또는 에러 → 아래 설치를 진행하세요

### Windows 설치

터미널에서 아래 명령어를 실행하세요:

```
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

설치 후 Kiro IDE를 **재시작**하세요.

### Mac 설치

터미널에서 아래 명령어를 실행하세요:

```
curl -LsSf https://astral.sh/uv/install.sh | sh
```

설치 후 Kiro IDE를 **재시작**하세요.

---

## Step 1: MCP 설정 파일 열기

1. Kiro에서 **Command Palette**를 엽니다
   - Mac: `⌘ + Shift + P`
   - Windows: `Ctrl + Shift + P`

2. `MCP`를 입력하고 **"Kiro: Open MCP Configuration"** 을 선택합니다

---

## Step 2: 설정 코드 붙여넣기

열린 파일에 아래 내용을 **그대로 복사해서 붙여넣기** 하세요:

```json
{
  "mcpServers": {
    "aws-docs": {
      "command": "uvx",
      "args": [
        "awslabs.aws-documentation-mcp-server@latest"
      ],
      "env": {
        "FASTMCP_LOG_LEVEL": "ERROR"
      },
      "disabled": false
    }
  }
}
```

---

## Step 3: 저장하기

- Mac: `⌘ + S`
- Windows: `Ctrl + S`

저장하면 Kiro가 자동으로 MCP 서버를 감지하고 연결합니다.

---

## Step 4: 연결 확인하기

채팅창에 다음과 같이 입력해보세요:

```
AWS S3가 뭔지 공식 문서에서 찾아서 설명해줘
```

AI가 AWS 공식 문서를 검색해서 답변하면 성공입니다! 🎉

> 💡 처음 실행 시 약간의 시간이 걸릴 수 있습니다 (패키지 다운로드)

---

## ⚠️ 트러블슈팅

### "MCP 서버가 연결되지 않아요"
- 파일을 저장했는지 확인하세요
- JSON 형식이 정확한지 확인 (중괄호, 쉼표 등)
- Kiro를 재시작해보세요

### "uvx 명령어를 찾을 수 없어요"
- 위 사전 준비 단계에서 uv를 설치했는지 확인하세요
- 설치 후 Kiro IDE를 재시작했는지 확인하세요

---

> ✅ **완료!** 이제 AI가 AWS 공식 문서에 접근할 수 있습니다. 실습으로 넘어가볼까요?

---

👉 다음: [MCP 활용 실습](hotel-news.md)
