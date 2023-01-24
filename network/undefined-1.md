---
description: 네트워크 식별자가 무엇인가요?
---

# 네트워크 식별자

<img src="../.gitbook/assets/image.png" alt="" data-size="original">

## Mac 주소

> **NIC(LAN 카드)**에 대한 식별자\
> LAN카드란 네트워크에 물리적으로 접속할 수 있게 하기 위해 컴퓨터 내에 설치된 확장 카드(하드웨어)

* **LAN카드**라고 붙은 것들은 무조건 **Mac 주소**를 가지고 있다.
* 유/무선 LAN카드를 동시에 가질 경우 Mac 주소는 2개다.
* Mac주소는 **자주 변경되는게 아니지만 변경가능**하다.
* Mac주소는 **H/W주소**라고도 한다.

## IP 주소(v4, v6)

> **Host**에 대한 식별자

* Host란 **인터넷(네트워크)에 연결된 컴퓨터**
* IP 주소는 **컴퓨터(Host)에 부여**된다.
* 한 컴퓨터가 **N개의 IP주소**를 가질 수 있다.
* IP 주소는 **NIC(LAN) 하나에 여러 개를 매핑**(바인딩)할 수 있다.

## Port 번호

> 어떤 Layer에서 관련된 일을 하는지에 따라 여러가지 형태로 **식별의 대상이 달라진다.**

* S/W: `Process` 식별자
* Network: `Service` 식별자
* H/W: `인터페이스 번호` (공유기 단자)

### 참고자료

* [https://youtu.be/JDh\_lzHO\_CA](https://youtu.be/JDh\_lzHO\_CA)
