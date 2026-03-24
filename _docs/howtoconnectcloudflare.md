---
layout: page
title: Cloudflare Tunnel 도메인 연결 방법
description: Cloudflare Tunnel을 사용하여 로컬 서버나 프라이빗 서버에 도메인을 안전하게 연결하는 방법입니다.
---

# Cloudflare Tunnel 도메인 연결 방법

Cloudflare Tunnel을 사용하면 복잡한 공유기 포트포워딩 설정 없이 내부 서버를 안전하게 외부 도메인에 연결할 수 있습니다.

## 1. Cloudflared 설치

운영체제에 맞게 `cloudflared` 프로그램을 설치해야 합니다.

### Windows

명령 프롬프트나 PowerShell에서 최신 버전의 실행 파일을 다운로드합니다.

```powershell
winget install --id Cloudflare.cloudflared
```

### macOS

Homebrew를 사용해 간편하게 설치할 수 있습니다.

```bash
brew install cloudflare/cloudflare/cloudflared
```

### Linux (Ubuntu/Debian)

```bash
curl -L 'https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb' -o cloudflared.deb
sudo dpkg -i cloudflared.deb
```

## 2. Cloudflare 로그인

설치가 완료되면 터미널(또는 명령 프롬프트)에서 아래 명령어를 입력합니다.

```bash
cloudflared tunnel login
```

명령어를 실행하면 웹 브라우저가 열립니다. 연결할 도메인이 등록되어 있는 Cloudflare 계정으로 로그인하고 사용할 도메인을 선택하여 인증을 완료합니다.

## 3. 터널 생성

이제 새로운 터널을 생성합니다. `<원하는-터널-이름>` 부분은 기억하기 쉬운 이름(예: `my-server`)으로 변경하세요.

```bash
cloudflared tunnel create <원하는-터널-이름>
```

터널이 성공적으로 생성되면 터널의 ID와 인증서가 위치한 경로가 화면에 표시됩니다.

## 4. 도메인 연결 설정

생성한 터널과 실제 도메인 주소를 연결합니다.

```bash
cloudflared tunnel route dns <터널-이름> <연결을-원하는-도메인>
```

**예제:**

```bash
cloudflared tunnel route dns my-server app.my-domain.com
```

## 5. 터널 실행 (서버 연결)

내부에서 실행 중인 서비스(예: 백엔드 서버의 포트가 4000인 경우 `http://localhost:4000`)를 터널을 통해 외부 접속이 가능하도록 실행합니다.

```bash
cloudflared tunnel run --url http://localhost:4000 <터널-이름>
```

명령어가 실행되고 나면, 설정한 도메인으로 접속했을 때 로컬 환경의 서비스 화면을 외부에서도 그대로 볼 수 있습니다.
