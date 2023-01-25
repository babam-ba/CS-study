---
description: "var, let, const의 차이점에 대해 설명해주세요\_⭐⭐⭐"
---

# var, let, const의 차이점

자바스크립트에서 변수 선언은 `선언 → 초기화` 단계를 거쳐 수행된다.

* **선언 단계**: 변수명을 등록하여 자바스크립트 엔진에 변수의 존재를 알린다.
* **초기화 단계**: 값을 저장하기 위한 메모리 공간을 확보하고 암묵적으로 undefined를 할당해 초기화한다.

## var

* 변수 중복 선언 가능하기 때문에 예기치 못한 값을 반환할 수 있다.
* 함수의 코드 블록만을 지역 스코프로 인정한다. -> 이를 **함수 레벨 스코프**라고 함.
* 함수 레벨 스코프로 인해 함수가 아닌 곳에 선언한 변수는 모두 전역 변수로 된다.

```javascript
var a = 1;

if (true) {
  var a = 5
};

console.log(a); // output: 5
```

* 변수 선언문 이전에 변수를 참조하면 언제나 undefined를 반환한다.

```javascript
console.log(sjy) // output: undefined

var sjy = 'sjy'
console.log(sjy) // output: sjy
```

## let

* 변수 중복 선언이 불가능하다.
* 재할당은 가능하다.
* 코드 블록(ex. 함수, if, for, while, try/catch 등)을 지역 스코프로 인정하는 **블록 레벨 스코프**를 따른다.

```javascript
let a = 1;

if (true) {
  let a = 5
};

console.log(a); // output: 1
```

* 변수 호이스팅: **선언 단계와 초기화 단계가 분리되어 진행**된다.
  * 즉, 런타임 이전에 자바스크립트 엔진에 의해 선언 단계가 먼저 실행된다.\
    만약, 초기화 단계가 실행되지 않았을 때 해당 변수에 접근하려고 하면 참조 에러가 뜬다.

```javascript
console.log(name); // output: Uncaught ReferenceError: name is not defined

let name = 'sjy';
```

## const

* 변수 중복 선언이 불가능하다.
* 재할당도 불가능하다.
  * 원시 값은 불가능하지만, 객체는 가능하다.\
    const 키워드는 재할당을 금지할 뿐, '불변'을 의미하지 않는다.

```javascript
// 원시값의 재할당
const name = 'sjy';
name = 'new sjy'; // output: Uncaught TypeError: Assignment to constant variable.

// 객체의 재할당
const name = {
  eng: 'sjy',
};
name.eng = 'new sjy';

console.log(name); // output: { eng: "new sjy" }
```

* 변수 호이스팅: **선언 단계와 초기화 단계가 동시에 진행**된다.
  * const의 경우 선언과 초기화가 런타임에 동시에 이루어지기 때문에 초기화가 진행되지 않은 상태에 변수에 접근하려고 하면 let과 다르게 초기화가 되지 않았다는 오류가 뜬다.

```javascript
console.log(name); // output: Uncaught ReferenceError: Cannot access 'name' before initialization

const name = 'sjy';
```



### 참고

[https://www.howdy-mj.me/javascript/var-let-const](https://www.howdy-mj.me/javascript/var-let-const)
