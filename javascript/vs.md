---
description: "동기와 비동기의 차이에 대해 설명해주세요\_⭐⭐⭐"
---

# 동기 vs 비동기

## 들어가기

### JS는 싱글 스레드로 동작한다.

싱글 스레드란 하나의 프로그램에서 동시에 하나의 코드만 실행할 수 있다는 뜻이다.

코어가 여러 개 있어도 메인 스레드라고 하는 싱글 스레드에서만 작업을 하며 **하나의 힙, 콜 스택**을 가진다. 하나의 콜 스택을 가진다는 것은 앞선 일이 완료될 때까지 다음 일은 하지 못한다는 것이다.(블로킹)

## 동기

### 정의

1. 하나의 요청이 오면 완료가 되어야 다음 요청을 실행하는 방식
2. 순차적, 직렬적으로 태스크 수행

### 특징

순차적으로 로직이 수행되므로 흐름을 쉽게 예츨할 수 있음

### 장단점

#### 장점

태스크를 순서대로 하나씩 처리하므로 실행 순서가 보장된다.

#### 단점

어떤 작업이 실행하는 동안 다른 작업은 실행할 수 없다. 웹, 앱 등 사용자와 상호작용을 하는 응용 소프트웨어의 경우 치명적이다.(앞선 태스크가 종료될 때까지 이후 태스크들이 블로킹된다.)

## 비동기

작업이 완료될 때까지 기다리지 않고 잠재적으로 오래 실행되는 작업을 시작하여 해당 작업이 실행하는 동안에도 다른 이벤트에 응답할 수 있게 하는 기술. 작업이 완료되면 프로그램이 결과를 제공.

### 정의

1. 어떤 요청이 오면 완료가 되기 전에 다음 요청을 실행하는 방식
2. 병렬적으로 태스크 수행

### 특징

여러 작업을 동시에 효율적으로 처리할 수 있음.

즉시 응답을 받지 못해서 적절히 처리가 되지 않으면 예상 밖의 결과가 나올 수 있음

### 장단점

#### 장점

현재 실행 중인 태스크가 종료되지 않은 상태라 해도 다음 태스크를 곧바로 실행하므로 블로킹이 발생하지 않는다.

#### 단점

태스크의 실행 순서가 보장되지 않는다.

### 비동기의 목표

1. 함수를 호출함으로써 장기적으로 실행되는 작업을 시작
2. 이 함수로 작업을 시작하고 즉시 복귀하여 다른 이벤트에 계속 응답할 수 있음
3. 작업이 완료되면 결과를 알려줌

### 그럼 왜 필요할까?

요청을 하고 응답이 많이 걸리는 작업 같은 경우 동기적으로 처리하면 어떤 문제가 발생할까? 요청이 온 다음에 다른 작업을 할 수 있으므로 잠시 앱이 멈춰 사용자는 앱을 사용하지 못할 것이고 그로 인해 이탈할 것이다. 그럼 비동기로 처리하면 어떨까? 사용자는 앱의 멈춤 없이 사용하다가 어떤 요청에 대해 응답이 왔을 때, 그 요청이 필요했던 기능을 사용할 수 있다.

일상 생활로 예시를 들자면 세탁기를 돌리고(1시간) 점심을 준비(1시간)해야 하는 상황이다. 동기로 처리하게 된다면 세탁기가 돌아가는 1시간을 기다리고 나서 점심을 준비하는 것이다. 이렇게 되면 총 2시간이 걸리게 될 것이다. 반면 비동기적으로 세탁기를 돌리고 나서 점심을 준비하면 어떨까? 시간 소모가 훨씬 줄어들 것이다.

물론 여기서 말하는 예시는 100% 동기, 비동기가 아니지만 비유하자면 이렇다.

#### 결론

위 내용으로 미루어 봤을 때, 엄청나게 많은 정보와 용량을 갖고 있는 작업 여러 개를 처리한다고 했을 때, 보다 **자원을 효율적으로 사용하기 위해서는 비동기적 프로그래밍이 필요하다. 특히 싱글 스레드 언어인 JS에서는 더더욱 말이다.**

****

근데 JS는 싱글 스레드 언어이면서 비동기는 어떻게 처리할까? 한 번에 한 가지 작업밖에 수행하지 못하는데..? 이 내용은 뒤 내용에서 다루도록 하겠다.

### **참고자료**

****[**https://developer.mozilla.org/ko/docs/Learn/JavaScript/Asynchronous/Introducing**](https://developer.mozilla.org/ko/docs/Learn/JavaScript/Asynchronous/Introducing)

