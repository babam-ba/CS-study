---
description: "meta 태그에 대해 설명해주세요 -\_⭐"
---

# meta 태그

## 정의 및 특징

1. 해당 문서에 대한 정보인 메타데이터(metadata)를 정의할 때 사용한다.
2. base, link, script, style, title 요소와 같이 다른 메타데이터 관련 요소들이 나타낼 수 없는 다양한 종류의 메타데이터를 제공할 때 사용되며, **이렇게 제공된 정보는 브라우저나 검색 엔진, 다른 웹 서비스에서 사용하게 된다.** -> **웹 페이지에 나타나지 않고, 검색 엔진 or 웹 크롤러를 통해 수집된다. 따라서 SEO를 위해서는 적절한(웹사이트에 대해 필요한 정보가 있는) 메타 태그를 넣어주어야 한다.**
3. meta 요소는 언제나 head 요소 내부에 위치해야 한다.
4. name or http-equiv 속성이 명시되었다면 반드시 content 속성도 함께 명시되어야 하며, 반대로 두 속성이 명시되지 않았다면 content 속성 또한 명시될 수 없다.

### 종류

1. 키워드(keyword)
2. 설명(description)
3. 저자(author)
4. 리다이렉트(redirect)
5. viewport
6. 검색 로봇 제어(robots)
7. 제작일(date)
8. 위치(location)
9. 저작권(copyright)
10. 인코딩 방식(charset)
11. 제작 도구(generator)
12. 배포자(distribution)
13. 새로고침(refresh)

등

### 속성

1. **name**: 메타데이터의 "이름"을 나타내는 속성
2. **http-equiv**
   1. content 속성에 명시된 값에 대한 http 헤더를 제공(`http-equiv: content` 와 같은 형식)
   2. http 응답 헤더를 시뮬레이션할 때 사용할 수 있음
   3. http-equiv가 있으면 content가 반드시 있어야 한다.
   4. refresh, content-type, default-style, content-security-policy를 사용할 수 있음
3. **content**: 메타데이터의 이름(name, http-equiv)에 대한 값을 나타냄
4. **charset**: 페이지의 문자 인코딩 선언

### 참고자료

[http://www.tcpschool.com/html-tags/meta](http://www.tcpschool.com/html-tags/meta)

[https://yozm.wishket.com/magazine/detail/816/](https://yozm.wishket.com/magazine/detail/816/)

[https://developer.mozilla.org/ko/docs/Web/HTML/Element/meta](https://developer.mozilla.org/ko/docs/Web/HTML/Element/meta)

[https://www.w3schools.com/tags/att\_meta\_http\_equiv.asp](https://www.w3schools.com/tags/att\_meta\_http\_equiv.asp)
