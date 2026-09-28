# 피돌이 호스트 릴리스

[피돌이](https://github.com/deokdory/pidory) 앱 호스트의 **macOS 실행 파일만** 올리는 저장소입니다.
소스 코드는 여기에 없습니다.

- 각 릴리스: 디스크 이미지(`Pidory-Host-<버전>-macOS-<아키텍처>.dmg`), `manifest.json`, `manifest.json.sig`, `SHA256SUMS`
- 실행 파일은 ALCON Co., Ltd. (Apple 팀 225VA7QY26) Developer ID 로 서명되고 Apple 공증을 받았습니다.
- `manifest.json.sig` 는 모든 파일의 SHA-256 목록에 대한 ed25519 서명입니다. 설치기와 자동 업데이트는
  호스트에 고정된 공개키로 이 서명을 확인한 뒤에만 설치합니다.

공개키(ed25519, base64): `AOwtf4ajURvHfvxoT4cVPzQ9p/EH2f14Mq5DVfbD+mY=`

라이선스: Apache License 2.0 (각 이미지의 `LICENSE`, `NOTICE`, `THIRD_PARTY_LICENSES`).
원작 deokdory/pidory 를 수정·확장한 배포본입니다.
