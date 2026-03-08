---
layout: page
title: 서버 접근 하는 방법
description: 서버 접근 하는 방법에 대해 설명을 합니다.
---

# 1. Mac에서 SSH 접속

Mac에서는 기본적으로 터미널을 사용하여 SSH에 접속할 수 있습니다.

### 사용 방법

```sh
ssh 사용자이름@서버주소 -p 포트번호
```

### 예제

```sh
ssh root@192.168.1.100 -p 22
```

그리고 비빌번호를 입력후 접근을 합니다.

# 2. Linux에서 SSH 접속

Linux에서도 터미널을 이용하여 SSH 접속이 가능합니다.

### 사용 방법

```sh
ssh 사용자이름@서버주소 -p 포트번호
```

### 예제

```sh
ssh user@203.0.113.1 -p 22
```

그리고 비빌번호를 입력후 접근을 합니다.

# 3. Windows에서 SSH 접속

Windows에서는 `PowerShell` 또는 `PuTTY`를 이용하여 SSH에 접속할 수 있습니다.

### 1 PowerShell을 이용한 접속

Windows 10 이상에서는 기본적으로 SSH 클라이언트가 포함되어 있습니다.

#### 사용 방법

```powershell
ssh 사용자이름@서버주소 -p 포트번호
```

#### 예제

```powershell
ssh admin@192.168.0.200 -p 22
```

그리고 비빌번호를 입력후 접근을 합니다.

### 2 PuTTY를 이용한 접속

1. [PuTTY 다운로드](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
2. PuTTY 실행 후 `Host Name`에 서버 주소 입력
3. `Port`에 포트 번호 입력 (기본값: 22)
4. `Open` 버튼 클릭하여 접속

# 4. OS별 SSH 기본 사용자 및 키 접속 방법

Cloud-init을 통해 생성된 인스턴스는 운영 체제(OS)에 따라 기본 사용자 ID가 다릅니다. 또한 보안을 위해 비밀번호 대신 SSH Key를 이용한 접속을 권장합니다. 각 OS별 기본 사용자 ID 및 SSH Key 접속 방법은 아래와 같습니다.

### 1. Ubuntu

- **기본 사용자 ID**: `ubuntu`
- **키 접속 방법**:
  ```sh
  ssh -i /키가_있는_경로/개인키.pem ubuntu@서버주소 -p 포트번호
  ```

### 2. Rocky Linux

- **기본 사용자 ID**: `rocky`
- **키 접속 방법**:
  ```sh
  ssh -i /키가_있는_경로/개인키.pem rocky@서버주소 -p 포트번호
  ```

### 3. Debian

- **기본 사용자 ID**: `debian`
- **키 접속 방법**:
  ```sh
  ssh -i /키가_있는_경로/개인키.pem debian@서버주소 -p 포트번호
  ```

### 4. CentOS

- **기본 사용자 ID**: `centos`
- **키 접속 방법**:
  ```sh
  ssh -i /키가_있는_경로/개인키.pem centos@서버주소 -p 포트번호
  ```

### 5. Alpine Linux

- **기본 사용자 ID**: `alpine`
- **키 접속 방법**:
  ```sh
  ssh -i /키가_있는_경로/개인키.pem alpine@서버주소 -p 포트번호
  ```

## 추가 팁

- 접속 포트가 기본값(22)이 아닐 경우 `-p` 옵션을 사용하여 포트를 지정해야 합니다.
- 보안 강화를 위해 `SSH Key` 인증 방식을 사용하는 것이 좋습니다.
- 방화벽 설정을 확인하여 SSH 포트가 열려 있는지 확인하세요.
