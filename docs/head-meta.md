---
title: head 태그에는 무엇이 있을까? HTML의 메타데이터
sidebar_position: 3
slug: /head-meta
---



head는 페이지를 열 때 브라우저에 표시되지 않는다. head는 &lt;title&gt;이나, css의 링크, favicon, 다른 메타 데이터(작성자, 중요 키워드 등 HTML에 대한 내용)를 포함합니다. 


| 사전 지식: | HTML의 기본 구조, [Getting started with HTML](https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML/Getting_started) 문서의 내용을 사전에 읽으면 좋습니다. |
| ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| 목적:    | HTML의 head을 사용하는 목적과 HTML 문서에 어떤 영향을 끼칠 수 있는지에 대해 학습합니다.                                                                                              |


# **HTML head란?** {#a88ef96aa33d42869f4081e96b76dd0a}


head의 내용이 하는 일은 페이지에 대한 [metadata](https://developer.mozilla.org/ko/docs/Glossary/Metadata)를 포함하는 것이다.


# **제목 달기** {#80b061ad52ce4fd3ab7fb30f71e0d6a6}


&lt;h1&gt;은 가끔 title을 가리키기는 하지만 &lt;title&gt;과는 엄연히 다르다.

- `<h1>`은 일반적으로 페이지당 한 번씩 사용하는데, 페이지 내용물의 제목을 표시하기 위해 쓴다.
- `<title>`은 (문서의 컨텐츠가 아니라) HTML 문서 전체의 타이틀을 표현하기 위한 메타데이터

 


## 능동적 학습 : 간단한 예제 살펴보기 {#4634f9d87f0d4619908c0b3ec9167d83}


…


`<title>` 요소는 브라우저에서 사이트를 북마크할 때, `<title>`의 내용물을 추천하는 북마크 이름으로 사용하기도 한다.


:::note

북마크할 때 들어가는 값이 &lt;title&gt;이라는 것을 정확하게 알고 있지는 않았는데 새롭게 알게 됨.

:::




![](/notion_imgs/1873796296.png)


# **메타데이터: &lt;meta&gt; 요소** {#d0823a9c1ac64202885217e1583a9653}


메타데이터는 데이터를 설명하는 데이터다.


HTML에서 문서에 공식적으로 메타데이터를 적용하는 방법이 `<meta>`다. 


## **문서의 character 인코딩을 특정하기** {#c41c693d31364429b7f1609fe088e1a8}


```html
<meta charset="utf-8" />
```


이는 웹 페이지에서 어떤 문자라도 취급할 수 있다는 것을 의미한다. 작성할 모든 페이지에서 character 집합을 utf-8로 지정하는 것은 좋은 생각이다.


만약 (라틴 알파벳 사용을 위해서) `ISO-8859-1`로 characterset을 설정한다면, 페이지가 엉망으로 렌더링된다.


![](/notion_imgs/1251742926.png)


> **참고:** 크롬과 같은 어떤 브라우저는 자동으로 잘못된 인코딩을 고치기 때문에, 어떤 브라우저를 사용하는가에 따라 이 문제를 겪지 않을 수도 있습니다. 그래도 다른 브라우저에서 있을 잠재적인 문제를 피하기 위하여 인코딩을 `utf-8` 으로 설정해야 합니다.


:::note

크롬과 같은 브라우저가 아니라 다른 브라우저를 사용하는 경우에 이런 잘못된 character 렌더링을 겪어본 기억이 있다. 

:::




## **능동적 학습: character 인코딩 실험** {#96abd7a732e747b5a840f1735f71a0d6}


...


## **저자와 설명을 추가** {#2b0fa5aa2d744d0186f1bc05618908dd}

- `name` 은 메타 요소가 어떤 정보의 형태를 갖고 있는지 알려준다.
- `content`는 실제 메타데이터의 컨텐츠.

이를 이용해서 일부 컨텐츠 관리 시스템에는 페이지 작성자 정보를 자동으로 추출해서 사용할 수 있는 기능이 있다.


:::note

작성자 정보를 추출해서 사용하는 기능이 어떤 기능을 말하는 것인가.

:::




또한, <u>페이지 컨텐츠 관련 키워드를 포함시켜서 검색엔진에 이 페이지가 더 많이 표시될 가능성이 생기게 한다.</u> (이를 Search Engine Optimization, SEO라고 한다.)


> **참고:** Google에서는 메인 MDN 홈페이지 링크 아래에 MDN의 몇 가지 관련 **서브 페이지가 표시**된다. 이를 **사이트 링크**라고하며 <u>**Google의 웹 마스터 도구에서 구성할 수 있다.**</u> 그리고 이는 Google 검색 엔진에서 사이트의 검색 결과를 개선하는 방법이다.


:::note

페이지 내 서브 페이지를 표시하고 싶다면 참고해서 작업을 수행한다.

:::




> **참고:** 많은 `<meta>` 기능들이 더이상 사용되지 않는다. (예를들어 `<meta name="keywords" content="fill, in, your, keywords, here">` 같은, 다른 검색 용어에 대해 해당 페이지의 관련성을 부여하기 위해 검색 엔진에 제공하던 키워드 등..) 스팸 발송자들이 키워드 목록에 수백 개의 키워드를 채워버리는 악용 사례가 생겨 버렸기 때문에 이것들은 검색 엔진들이 아예 무시를 해버리게 되었다.


:::note

현재 프로젝트에서 작성한 meta 태그 중에 검색엔진에서 무시해버리는데도 사용하고 있는 것들이 있는가?

:::




## **Other types of metadata** {#97711bfe081e4ca39e2b2968ea475645}


특정 사이트에서 사용할 수 있는 특정 정보를 제공하도록 설계된 경우도 있다. 


[Open Graph Data](https://ogp.me/) 는 Facebook이 웹 사이트에 더 풍부한 메타 데이터를 제공하기 위해 발명한 메타 데이터 프로토콜이다.


```html
<meta
  property="og:image"
  content="https://developer.mozilla.org/mdn-social-share.png" />
<meta
  property="og:description"
  content="The Mozilla Developer Network (MDN) provides
information about Open Web technologies including HTML, CSS, and APIs for both Web sites
and HTML5 Apps. It also documents Mozilla products, like Firefox OS." />
<meta property="og:title" content="Mozilla Developer Network" />
```


트위터 내에서 표시될 때도 비슷한 게 있다.


```html
<meta name="twitter:title" content="Mozilla Developer Network" />
```


# **맞춤 아이콘 추가하기** {#3021ead02b874eeeb70ad6c75a87b6bf}


커스텀 아이콘 레퍼런스를 메타데이터에 추가하고 특정 컨텐츠에서 이것을 보여지게 할 수 있다.


열린 페이지의 탭이나 북마크 패널 페이지 쪽에서 favicon을 볼 수 있다.

1. 인덱스 페이지와 같은 디렉토리에 `.ico` 포멧의 파일을 저장한다. (most browsers will support favicons in more common formats like `.gif` or `.png`, but using the ICO format will ensure it works as far back as Internet Explorer 6.)
1. 다음 줄을 HTML &lt;head&gt;에 추가하여 favicon을 참조하라 :

	```html
	<link rel="shortcut icon" href="favicon.ico" type="image/x-icon" />
	```


다른 많은 아이콘 타입이 있다.


```html
<!-- third-generation iPad with high-resolution Retina display: -->
<link
  rel="apple-touch-icon-precomposed"
  sizes="144x144"
  href="https://developer.mozilla.org/static/img/favicon144.png" />
<!-- iPhone with high-resolution Retina display: -->
<link
  rel="apple-touch-icon-precomposed"
  sizes="114x114"
  href="https://developer.mozilla.org/static/img/favicon114.png" />
<!-- first- and second-generation iPad: -->
<link
  rel="apple-touch-icon-precomposed"
  sizes="72x72"
  href="https://developer.mozilla.org/static/img/favicon72.png" />
<!-- non-Retina iPhone, iPod Touch, and Android 2.1+ devices: -->
<link
  rel="apple-touch-icon-precomposed"
  href="https://developer.mozilla.org/static/img/favicon57.png" />
<!-- basic favicon -->
<link
  rel="shortcut icon"
  href="https://developer.mozilla.org/static/img/favicon32.png" />
```


지금 당장 모든 아이콘을 구현할 부담을 느낄 필요가 없다. 이는 고급 기능이며 여러 지식을 습득해야 한다.


# **HTML에 CSS 와 JavaScript 적용하기** {#b9434be98ce841e980cf66d244c6ae4a}


현대 모든 웹사이트는 상호작용 기능이 많은 영상 플레이어, 지도, 게임 등을 위해 [JavaScript](https://developer.mozilla.org/ko/docs/Glossary/JavaScript)가 필요하고, 이것들을 더 멋져 보이게 하기 위해 [CSS](https://developer.mozilla.org/ko/docs/Glossary/CSS)가 사용된다. 
이것들은 [`<link>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/link) 요소와 [`<script>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/script) 요소를 사용하여 웹 페이지에 가장 일반적으로 적용된다.

- [`<link>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/link)는 항상 문서의 head 부분에 위치한다. 
이것은 두 가지 속성을 취하는데, `rel="stylesheet"`, 즉 문서의 스타일 시트임을 나타냄과 동시에 스타일 시트 파일의 경로를 포함하는 `href`를 내포한다.

	```html
	<link rel="stylesheet" href="my-css-file.css" />
	```

- [`<script>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/script) 는 head에 들어갈 필요가 없다. `</body>` 태그 바로 앞, 문서 본문의 맨 끝에 넣는 것이 좋으며, JavaScript를 적용하기 전에 모든 HTML 내용을 브라우저에서 읽었는지 확인하는 것이 좋다. 
액세스 과정에서 JavaScript가 아직 존재하지 않는 요소라고 판단하며 에러가 날 수 있다.

**Note**: `<script>` 태그가 비어있다고 보일 수도 있지만 그렇지 않으며, 반드시 태그를 닫아주어야 한다(&lt;/script&gt;). 
외부 스크립트 파일을 지정하는 대신 스크립트를 `<script>` 안에 넣을 수도 있다.

```html
<script src="my-js-file.js"></script>
```


# **문서의 기본 언어 설정** {#10d3146bfb234356923c8bc519b5460c}


```html
<html lang="en-US"></html>
```


이것은 여러 방면에 유용하다. 검색엔진에 효과적으로 색인화되며(언어별 결과에 올바르게 표시) 스크린 리더를 사용하는 시각 장애가 있는 사용자에게 유용하다.(ex. 6이라는 숫자는 프랑스어와 영어에서 모두 존재하지만, 각기 다른 발음이 적용된다.)


또한, 특정 하위 섹션만 다른 언어로 인식되도록 할 수 있다. 


```html
<p>Japanese example: <span lang="jp">ご飯が熱い。</span>.</p>
```

