---
description: "질문: DOM, BOM, CSSSOM에 대해 설명해주세요.\_⭐⭐⭐"
---

# DOM, BOM, CSSOM

### 들어가기

호스트: JS가 돌아가는 플랫폼. 브라우저, 웹서버 심지어는 커피 머신이 될 수 있음.

호스트 환경: 각 플랫폼은 해당 플랫폼에 특정되는 기능을 제공

* 랭귀지 코어(ECMAScript에 더하여 플랫폼에 특정되는 객체, 함수 제공

> 웹 브라우저는 웹페이지를 제어하기 위한 수단 제공. Node.js는 서버 사이드 기능 제공



## 호스트 환경: 웹 브라우저

<figure><img src="../.gitbook/assets/스크린샷 2023-01-11 오후 11.16.53.png" alt=""><figcaption><p>출차: 모던 자바스크립트</p></figcaption></figure>



`window 객체`: 루트

1. JS 코드의 전역 객체
2. 브라우저 창을 대변, 이를 제어할 수 있는 메서드 제공

\-> 호스트 환경이 웹 브라우저이므로 server side에서는 window 객체에 접근할 수 없다.



#### DOM(Document Object Model: 문서 객체 모델)

> 브라우저의 렌더링 엔진은 웹 문서(HTML, XML)를 로드한 후, 파싱하여 웹 문서를 브라우저가 이해할 수 있는 구조로 구성하여 메모리에 적재. 이를 DOM이라 함.

> 1. 웹 페이지에 대한 인터페이스로 웹 페이지 내의 모든 컨텐츠를 객체(트리 구조, node로 구성됨.)로 나타내줌. 이 객체는 **수정 가능**
> 2. HTML, XML 문서의 프로그래밍 인터페이스이다.
> 3. DOM은 문서의 구조화된 표현(트리 구조)을 제공하며 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법(API) 제공하는 객체 모델. 그들이 문서 구조, 스타일, 내용을 변경할 수 있게 돕는다. -> 웹 페이지를 script or 프로그래밍 언어에서 사용될 수 있게 연결시켜줌.

`명세서:` [`https://dom.spec.whatwg.org`](https://dom.spec.whatwg.org)``

`document`: 페이지의 기본 진입점 역할, 이를 이용해 페이지 내 무엇이든 변경가능. 원하는 것을 만들 수도 있음.

window는 창을 컨트롤, document는 문서를 컨트롤.

특징

* DOM은 브라우저만을 위한 모델이 아니다. HTML 페이지를 다운로드하고 이를 가공해주는 Server Side 스크립트(Node.js)에서도 DOM을 사용한다.(명세서 일부만 지원)
* 많은 브라우저들이 표준 규약에서 제공하는 기능 외 추가 기능을 제공하기 때문에 작성한 문서들이 **각기 다른 DOM이 적용된 다양한 브라우저 환경에서 동작할 수 있다.**
* JS는 브라우저가 읽고 어떤 작업을 수행할 수 있는 언어. DOM은 이 작업이 이루어지는 장소.
* JS로 문서 객체를 생성한다?
  * 정적 생성: 브라우저가 HTML에 적혀져 있는 태그를 읽고 있는 그대로 문서 객체를 생성하는 것.
  * 동적 생성: 원본 HTML에는 없는 문서 객체를 JS(DOM API)를 이용하여 생성
  * JS로 문서 객체를 생성하는 것은 **동적 생성**



**DOM이 아닌 것들**

1. HTML코드는 DOM이 아니다. HTMl이 브라우저에 의해 파싱되면 DOM이 된다.
2. 페이지 view source는 DOM이 아니다. 해당 페이지를 이루고 있는 HTML을 보여줄 뿐이며 내가 작성한 HTML과 같다.
3. DevTools에서 보이는 코드는 DOM과 유사하지만 완전히 같지는 않다. css의 pseudo element와 같이 추가적으로 포함되는 것들이 있다.

#### CSSOM(CSS Object Model: CSS 객체 모델)

> 1. CSS규칙과 스타일시트는 HTML과는 다른 구조로 CSS 규칙과 스타일시트를 객체로 나타내고 이 객체를 어떻게 읽고 쓸 수 있을지에 대한 설명을 담은 별도의 명세서(JS로 조작하기 위함)\
>
> 2. JS가 CSS를 조작할 수 있는 api의 집합. DOM과 비슷하지만 HTML이 아닌 CSS를 위한 것. 유저는 CSS 스타일을 동적으로 읽고 수정할 수 있다.

명세서: [https://www.w3.org/TR/cssom-1/](https://www.w3.org/TR/cssom-1/)

1. 문서에 쓰이는 스타일 규칙을 수정할 때 DOM과 함께 쓰임.
2. 대부분 정적이기 때문에 CSSOM을 실무에서 자주 접하지는 않음.
3. JS를 이용해 CSS 규칙을 추가 or 제거하는 경우는 드물다. but 이때 사용됨.



#### BOM(Browser Object Model)

> 문서 이외의 모든 것(브라우저 창)을 제어하기 위해 브라우저(호스트 환경)가 제공하는 추가 객체

객체화한 이유는 브라우저를 스크립트로 제어하기 위함이다.

명세서: [https://html.spec.whatwg.org](https://html.spec.whatwg.org)

예시

* navigator: 브라우저와 운영체제에 대한 정보 제공.
  * navigator.userAgent, navigator.platform 등이 있음
* location: 현재 URL을 읽을 수 있게 해주고 새로운 URL로 변경(redirect)할 수 있게 해줌

최상단 그림에는 표현되어 있지는 않지만 document도 BOM에 포함된다. DOM도 BOM의 일부이다.



#### 참고자료

* 모던 자바스크립트
* MDN
* [https://choco4study.tistory.com/73](https://choco4study.tistory.com/73)
