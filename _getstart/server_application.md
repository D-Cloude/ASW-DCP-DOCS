---
layout: page
title: 서버 신청
description: 서버 신청하는데 필요한 정보를 제공합니다.
---
{% include alert.html type="info" title="안내사항" content="이 부분에서는 DCP하고 ASW하고 보이는 부분이 차이가 날수 있어서 공통된 부분은 `공통` 으로 표기가 되고 아닐경우 따로 표기가 됨니다." %}

# 페이지 이동 (공통)
메인 페이지에서 서버 신청이라는 버튼을 찾아서 눌려주세요.<br/>
<img src="../assets/img/server.png" width="100" height="100"><br/>
이래 페이지로 이동하는지 확인해주세요.<br/>

## DCP 화면
![img](../assets/img/server_main.png)<br/>

## ASW 화면
![img](../assets/img/asw_server_mainpage.png)

# 대여 정보 (공통)
<img src="../assets/img/Rental_information.png" width="250" height="250"><br/>
대여 정보에서 정확한  날짜와 사유를 입력해주세요. 관리자가 심의 할때 유용한 정보로 활용될수 있습니다.

{% include alert.html type="warning" title="주의사항" content="대여 날자를 정확히 입력해 주세요. 분기 말에 전체 확인을 해서 초과한  VM대해서는 무통보 삭제가 될수 있습니다." %}

# 서버 정보 (DCP)
![img](../assets/img/dcp_server_info.png)<br/><br/>
자신이 필요하는 성능하고 운영체제를 적어주세요. <br/>

{% include alert.html type="warning" title="안내사항" content="서버 이름은 소문자로 설정 해주세요. 대문자로 설정 할경우 임의로 변경이 될수 있고 아래 CPU,RAM,Storage에 규격을 정확히 적어주세요." %}
{% include alert.html type="danger" title="경고사항" content="정보를 올바르게 입력을 했으나 서버 자원이 부족할경우 관리자가 이메일을 주거나 임의로 거부가 될수가 있습니다." %}

# 서버 정보 (ASW)
![img](../assets/img/asw_server info.png)<br/><br/>
DCP와 다르게 서버타입이 설정이 되어있어서 학과에서 실습하는 정도에 따라서 타입을 설정하시고 서버 이용 용도에 `XXX 과목에 이용할 예정입니다` 라고 적어주세요.
{% include alert.html type="danger" title="경고사항" content="서버 자원이 부족시 DCP로 옮겨질수 있으며 관리자 재량에 따라 해당 과목에 과도한 성능이면 거부 될당할수 있습니다." %}

# 서버 계정 정보 (공통)
![img](../assets/img/asw_server_account.png)<br/><br/>
계정 정보는 대문자 말고 소문자로 입력 해주시고 보안이 취약하지 않게 5자리 이상 으로 입력해주시기 바람니다.<br/>
네트워크 추가 사항 같은 경우 필요한 포트를 입력해주면 관리자가 이메일을 통해 결과를 통보해 드리겟습니다.
> ASW같은 경우 기본 적으로 SSH,DB,WEB포트는 NAT으로 다른 포트로 제공해드리고 있습니다.
{% include alert.html type="info" title="만약 80,443 포트 및 도메인이 필요할 경우" content="정보를 
리버스 프록시 서버를 통해 웹 사이트를 연결해 드립니다.<br/>
443 및 80 포트는 관리자와 협의후 공인 IP가 별도로 할당된 경우에만 직접 사용 가능합니다.<br/>
기존 사용자는 도메인을 연결 할경우 네트워크 추가 요청 시 다음 정보를 기재해 주세요:<br/><br/>

[웹 도메인 연결 요청]<br/>
1. 내부망에서 사용할 웹 포트(ex: front 3000 , backend 3002 )<br/>
2. 원하시는 서브도메인 (선택사항) or 자신이 연결할 도메인 주소<br/>
3. SSL 생성여부: Yes or No<br/>
> ASW 같은 경두도 네트워크 추가 사항에 입력해주시면 반영해드리겟습니다.
" %}
