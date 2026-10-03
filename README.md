# 피돌이

자기 Mac에서 AI 에이전트 서버를 돌리고, iPhone·Mac 피돌이 앱에서 글·음성으로 요청해요. **3총사**의 PM이 정리하고 워커가 실행하고 리뷰어가 확인해요.

이 저장소는 Mac 호스트 설치 파일과 안내를 배포해요.

## 시작해요

**[최신 릴리스에서 설치](https://github.com/Sim-jaeil/pidory-host-releases/releases/latest)** — 준비물·설치·앱 연결·변경 내용을 한곳에서 확인해요.

| 준비물 | 기준 |
|---|---|
| Mac | Apple Silicon · macOS 14 이상 · 여유 공간 8GB 이상 |
| AI 계정 | 사용할 Claude·Codex·Grok·Cursor·Gemini 계정 하나 이상 (Gemini는 무료 개인 구글 계정) |
| Tailscale | Mac과 iPhone에서 같은 본인 계정으로 로그인 |
| 피돌이 앱 | [공개 베타 링크](https://testflight.apple.com/join/JVDZDb5v)에서 TestFlight로 설치 |

아래 명령으로 최신 정식 버전을 설치해요. 기존 설치도 같은 명령으로 업그레이드해요.

```sh
curl -fsSL https://github.com/Sim-jaeil/pidory-host-releases/releases/latest/download/install.sh | bash
```

CLI를 고르고 피돌이 전용 기록 폴더에 로그인해요. 완료 화면의 서버 주소·연결 키를 앱 › 서버 추가에 넣고 **피돌이** 폴더의 PM에게 첫 요청을 보내요.

[AI 에이전트용 설치 안내](https://github.com/Sim-jaeil/pidory-host-releases/releases/latest/download/INSTALL-FOR-AGENTS.md)를 에이전트에게 주고 설치를 맡길 수도 있어요. 개인 CLI 로그인 파일이나 연결 키를 대화에 보내지 않아요.

## 기록 이전·업데이트

예전 디스코드 기록은 `~/.local/bin/pidory-host migrate discord`로 점검하고 채널을 골라 옮겨요. 첨부는 1GiB까지예요. 못 옮긴 파일은 완료 화면과 출력된 이전 보고 파일의 `unrecovered_attachments`에서 확인해요. [상세 안내](https://github.com/Sim-jaeil/pidory-host-releases/releases/latest/download/guide-ko.md)를 따라 봇·호스트를 중지하고 적용해요.

새 서버 버전은 앱의 **“업데이트가 있어요”**에서 확인하고 앱 › 설정 › 서버 › 서버 업데이트로 적용해요. 시험판 받기를 켜면 시험판도 확인할 수 있어요. 자동 적용은 하지 않아요.

```sh
~/.local/bin/pidory-host status
~/.local/bin/pidory-host restart
~/.local/bin/pidory-host connect-info
~/.local/bin/pidory-host uninstall
```

제거는 DB·대화·설정을 보존해요. 데이터 삭제는 `uninstall --delete-data`에서 별도로 확인해요. 설치 로그는 `~/Library/Application Support/Pidory/native-runtime/install/`에 있어요.

이번 팀 배포는 Private/Tailscale 방식이라 Tailscale이 필요해요. 공개 인터넷 접속은 지원하지 않아요. 서버 Mac이 잠자거나 로그아웃하면 연결이 끊기고, 재부팅 뒤에는 계정 로그인이 필요해요. iPhone 푸시는 별도 설정을 건너뛰면 꺼져요.

로그인하면 자동으로 이어져요. 안 되면 `pidory-host restart`로 다시 시작해요.

## 1.1.0에서 할 수 있어요

- 앱에서 서버 업데이트·시험판 받기와 AI 추가를 관리해요. 무료 개인 구글 계정으로 Gemini도 사용할 수 있어요.
- 앱·서버 호환 안내를 확인하고, 서버 프로젝트 파일을 찾아 첨부하거나 MCP 도구를 관리해요.
- 보관한 대화를 확인 후 영구 삭제하고, 무음 대화의 배지·안 읽음 표시를 줄여요.
- Claude 1M 지원을 자동 확인하고, 대화별 신뢰 구성원과 관리자 승인 카드로 실행을 관리해요.
- 대화 진행 현황을 기기 간에 맞추고, 위임·재시작·업데이트 안정성을 개선했어요.

앱 공개 베타는 Apple 외부 심사가 끝나면 공개 링크에서 새 빌드를 받을 수 있어요.
