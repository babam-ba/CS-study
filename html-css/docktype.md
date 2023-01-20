---
description: "질문:DOCTYPE에 대해 설명해주세요. -\_⭐⭐"
---

# DOCKTYPE

## 들어가기

### DTD(Document Type Definition)

문서 타입 정의로 웹 문서 최상단에 선언하는 코드.

브라우저에게 문서 형식을 알려주는 부분으로 이 선언부에 따라 브라우저는 렌더링 모드를 바꾸고 해당 렌더링 모드에 맞게 사용할 수 있는 태그와 속성이 변경된다.

1. 문서의 구조 및 해당 문서에서 사용할 수 있는 적법한 요소와 속성 정의
2. 엔티티를 정의할 수 있으며, 빠른 개발을 위한 내부 DTD를 사용할 수 있음
3. 새로운 문서의 구조를 정의함으로써 새로운 문서 타입을 만들 수 있음

\-> 이렇게 생성된 DTD는 새로운 문서 타입을 이용한 데이터의 교환에서 표준으로써 활용됨.

더 딥한 DTD의 내용은 [http://www.tcpschool.com/xml/xml\_dtd\_intro](http://www.tcpschool.com/xml/xml\_dtd\_intro)를 참고하세요.

## \<!DOCKTYPE html>이란

> ducument type의 약어로, 웹 문서가 어떠한 형식으로 작성되었는지 최상단에 문서의 형식을 선언하는 것. 대소문자 구분 X

HTML 4.01에서 DOCTYPE 선언은 SGML을 기반으로 하기 때문에 DTD를 참조해야 한다. DTD는 브라우저가 콘텐츠를 정확하게 표현하도록 마크업 언어에 대한 규칙을 명시한다.

하지만 HTML5는 [SGML](https://developer.mozilla.org/en-US/docs/Glossary/SGML)을 기반으로 하지 않기 때문에 DTD를 참조할 필요가 없다.

1. HTML 문서가 어떤 버전으로 작성되었는지 브라우저에게 알려주는것.
2. 브라우저에게 HTML의 버전 및 웹브라우저 내용을 잘 출력할 수 있도록 도와주는 역할
3. 문서 파일의 최상단에 위치해야 한다. -> 어떤 문서의 형식인지 브라우저에게 알려주기 위함.

### 선언하는 이유

1. **문서 간 호환성을 높이기 위함** -> 브라우저에게 문서 버전을 알림으로써 문서를 동일하게 인식하기 위함.
2. **선언을 통해 구버전, 신버전에 알맞게 문법을 검사하는 것.** HTML도 버전마다 적용되는 태그, 적용되지 않는 태그가 있다. 구버전에서 신버전의 HTML 태그를 사용한다면, 웹브라우저는 문법오류로 간주할 것이다.

### 선언하지 않으면?

> 브라우저가 해당 문서의 형식을 알 수 없게 된다.

브라우저는 비표준 모드로 렌더링 모드를 변경하게 되면서 문서 제작자가 의도한 레이아웃(태그의 구조, CSS 등)이 깨지게 되어 사용자에게 비정상적인 상태의 문서를 보여줄 수 있다.

따라서 웹 호환성(Cross Browsing)을 지키기 위해서는 DOCTYPE을 선언해야 한다.

### 예시

1. HTML 5: `<!DOCTYPE html>`
2. HTML 4.01 Strict: `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http:www.w3.org/TR/html4/strict.dtd">`

### 참고자료

* [http://www.tcpschool.com/xml/xml\_dtd\_intro](http://www.tcpschool.com/xml/xml\_dtd\_intro)
* [http://www.tcpschool.com/html-tags/doctype](http://www.tcpschool.com/html-tags/doctype)
* [https://kenna-hwa.tistory.com/97](https://kenna-hwa.tistory.com/97)
* [https://developer.mozilla.org/ko/docs/Glossary/Doctype](https://developer.mozilla.org/ko/docs/Glossary/Doctype)
* [https://rypro.tistory.com/187](https://rypro.tistory.com/187)
