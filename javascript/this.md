---
description: "this에 대해 설명해주세요\_⭐⭐⭐"
---

# this

this는 **자신이 속한 객체** 또는 **자신이 생성할 인스턴스**를 가리키는 **자기 참조 변수**다. this를 통해 **자신이 속한 객체 또는 자신이 생성할 인스턴스의 프로퍼티나 메서드를 참조**할 수 있다.

this는 자바스크립트 엔진에 의해 암묵적으로 생성된다. 함수를 호출하면 arguments 객체와 this가 암묵적으로 함수 내부에 전달된다. 함수 내부에서 arguments 객체를 지역 변수처럼 사용할 수 있는 것처럼 this도 지역 변수처럼 사용할 수 있다.

단, this 바인딩은 함수 호출 방식에 의해 **동적으로 결정**된다.



### 일반 함수의 this와 화살표 함수의 this의 차이점

기본적으로 this에는 전역 객체가 바인딩된다.

* 일반 함수를 호출하면 함수 내부의 this에는 전역 객체(window)가 바인딩된다.
* 화살표 함수는 스스로의 this를 가지지 않는다. 그래서 화살표 함수 내에서 `this`에 접근하면 스코프 상의 this를 참조한다.
  * `this`가 위치한 스코프에서 `this`가 무엇인지 찾고, 해당 스코프에 `this`가 없다면 스코프 체인을 타고 올라가며 가장 가까운 `this`를 참조하게 된다.

### call, apply, bind

call, apply, bind 메서드는 Function.prototype의 메서드다. 즉, 이들 메서드는 모든 함수가 상속받아 사용할 수 있다.

* **call()**은 모든 함수에서 사용 가능하며, this를 특정 객체로 지정할 수 있다.

```javascript
const dog = {
  age: 24 
};
function printDogAge() {
  console.log(this.age)
}
printDogAge.call(dog);    // 24

/* 매개변수를 전달할 경우 */
const dog = {
  age: 12 
};
function printDogAge(name, location) {
  console.log(this.age, name, location)
}
printDogAge.call(dog, 'mike', 'seoul');    // 24, mike, seoul
```

* **apply()**는 call()과 유사하지만 매개변수 처리 방법에 차이가 있다. call()은 일반적인 함수처럼 매개변수를 받지만, apply()는 배열 형태로 매개변수를 받는다.

```javascript
const dog = {
  age: 24 
};
function printDogAge(name, location) {
  console.log(this.age, name, location);
}
printDogAge.apply(dog, ['mike', 'seoul']);    // 24, mike, seoul
```

* **bind()**가 call(), apply()와 다른 점은 함수를 실행하지 않는 점이다. 대신 bind된 함수를 리턴한다.

```javascript
const dog = {
  age: 24 
};
function printDogAge() {
  console.log(this.age);
}
const print = printDogAge.bind(dog);
print();    // 24
```

### use strict 모드에서의 this

this는 객체의 프로퍼티나 메서드를 참조하기 위한 자기 참조 변수이다. 따라서 객체를 생성하지 않는 일반 함수에서 this는 의미가 없다. strict mode가 적용된 일반 함수 내부의 this에는 **undefined**가 바인딩된다.



### 참고

모던 자바스크립트 Deep Dive 22장

[https://velog.io/@raram2/%ED%99%94%EC%82%B4%ED%91%9C-%ED%95%A8%EC%88%98%EB%A5%BC-%EB%82%A8%EC%9A%A9%ED%95%98%EB%A9%B4-%EC%95%88%EB%90%98%EB%8A%94-%EC%9D%B4%EC%9C%A0](https://velog.io/@raram2/%ED%99%94%EC%82%B4%ED%91%9C-%ED%95%A8%EC%88%98%EB%A5%BC-%EB%82%A8%EC%9A%A9%ED%95%98%EB%A9%B4-%EC%95%88%EB%90%98%EB%8A%94-%EC%9D%B4%EC%9C%A0)

