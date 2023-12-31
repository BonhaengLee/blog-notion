---
title: 하이퍼링크 만들기
sidebar_position: 5
slug: /hyperlink
---



웹을 웹답게 만든다는 점에서 하이퍼 링크는 중요하다.


| 사전 지식 | [HTML 시작하기](https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML/Getting_started)에서 설명하는 기본적인 HTML 숙련도. [HTML text fundamentals](https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals)에서 설명하는 HTML 텍스트 포맷팅에 대한 지식. |
| ----- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 목표    | 하이퍼링크를 효과적으로 다루는 방법과 수많은 파일들을 함께 연결하는 방법을 배웁니다.                                                                                                                                                                                                                             |


# **하이퍼링크란** {#1fbddc95c08c4db0a9151a25d2bc0957}


하이퍼링크는 처음부터 웹의 기능이었으며 웹을 웹으로 만드는 요소입니다. 하이퍼링크를 사용하면 문서를 다른 문서나 리소스에 연결하거나, 문서의 특정 부분에 연결하거나, 웹 주소에서 앱을 사용할 수 있다.


> **참고:** URL은 HTML 파일, 텍스트 파일, 이미지, 텍스트 문서들, 비디오와 오디오 파일들, 그리고 웹상에서 존재할 수 있는 어느 것이든 연결할 수 있습니다.   
> 웹 브라우저가 파일을 표시하거나 처리하는 방법을 모르는 경우 파일을 열 것인지(이 경우 파일을 열거나 처리해야 할 의무가 장치의 적절한 기본 앱에 전달됨) 또는 파일을 다운로드할 것인지(이 경우 나중에 처리를 시도할 수 있음) 묻는 메시지가 표시됩니다.


# **링크의 구조** {#f3383bad460944e6ae73e7b54c49649e}


기본 링크는 텍스트 또는 block level links를 `<a>` 요소 안에 감싸고 웹 주소를 포함하는 `href` 속성(**Hypertext Reference** 또는 **target**)을 사용하여 생성된다.


:::note

**왜 block level links를 허용할까?**

HTML5에서도 여전히 일반적으로 인라인 요소 내에 블록 레벨 요소를 넣는 것은 문법 오류로 간주됩니다. 
인라인 요소는 보통 작은 청크의 콘텐츠를 감싸거나 스타일링을 적용하기 위해 사용되며, 블록 레벨 요소는 구조를 생성하고 레이아웃을 정의하는 데 사용됩니다.

### **인라인 요소 (Inline Elements):**

- **`<span>`**, **`<a>`**, **`<strong>`**, **`<em>`**, **`<abbr>`**, 등

- 인라인 요소는 텍스트의 일부를 감싸며, 텍스트 흐름과 인라인 형식 컨텍스트에서만 사용됩니다.

### **블록 레벨 요소 (Block-level Elements):**

- **`<div>`**, **`<p>`**, **`<h1>`** ~ **`<h6>`**, **`<ol>`**, **`<ul>`**, **`<table>`**, 등

- 블록 레벨 요소는 콘텐츠의 구조를 생성하며, 새로운 박스를 생성하여 다른 요소와 분리됩니다.

### **예외:** **`<a>`** **요소**

HTML5에서 **`<a>`** 요소는 예외적으로 블록 레벨 요소를 포함할 수 있게 되었습니다. 이 변경은 위에서 언급한 사용성(큰 클릭 가능 영역을 제공), 접근성, 디자인 유연성(큰 이미지, 텍스트 블록 또는 다른 요소를 링크로 사용할 수 있어 더 동적이고 풍부한 인터페이스) 등의 이유로 인해 이루어졌습니다. 그러나 다른 인라인 요소들에 대해서는 여전히 블록 레벨 요소를 내부에 넣는 것이 허용되지 않습니다.

### **예제:**

- **허용되는 경우:**

- **허용되지 않는 경우:**

따라서 일반적인 규칙을 따르되, <u>**`<a>`**</u> <u>태그와 같은 특별한 경우에 대한 예외를 인식하는 것이 중요합니다.</u>

:::




## **Block level 링크들** {#06694aaf90a84c1ca58ec7aae82e6d4b}


어떤 것이든 링크로 바꿀 수 있다. 


## **이미지 링크들** {#5278be8868cb41f29c64523de64aa34f}


…


## **title 속성에 부가적인 정보를 더하기** {#1f8901e640954ea593098ad315bcc6a3}


Title은 페이지에 포함된 정보 또는 웹 사이트에서 주의해야 할 사항 등 **링크에 대한 추가 정보**를 포함하고 있습니다.


```html
<p>
  I'm creating a link to
  <a
    href="https://www.mozilla.org/en-US/"
    title="The best place to find more information about Mozilla's
          mission and how to contribute">
    the Mozilla homepage</a>.
</p>
```


> **참고:** 링크 제목은 <u>**마우스 호버에만 표시**</u>되므로 키보드 컨트롤이나 터치스크린을 사용하여 웹 페이지를 탐색하는 사용자는 제목 정보에 액세스하는 데 어려움을 겪습니다. Title의 정보가 페이지의 사용에 있어서 <u>**정말로 중요하다면, 해당하는 정보를 일반 텍스트로 넣어줌으로써 모든 사용자가 접근할 수 있는 방식으로 표시**</u>해야 합니다.


# **URL과 path에 대한 기본 지침** {#2662abba549644daac37334c964125f0}


URL, 혹은 Uniform Resource Locator은 단순히 무언가가 **웹상의 어디에 위치하는지 결정하는 하나의 텍스트 문자열**이다.


URL은 파일들을 찾기위해 path를 이용합니다. **path는 당신이 관심있어 하는 파일이 파일 시스템 어디에 있는지 구체적으로 명시**하구요. 디렉토리 구조에 대한 예제를 보시죠. ([하이퍼링크 만들기](https://github.com/mdn/learning-area/tree/master/html/introduction-to-html/creating-hyperlinks)를 보세요.)


![](/notion_imgs/1715172405.png)


이 디렉토리 구조의 **root**를 `creating-hyperlinks`라고 부릅니다. 웹사이트를 로컬 단에서 다룰 때에는 전체 웹사이트가 모두 들어갈 수 있는 하나의 디렉토리를 가져야 할 것입니다. Root 안에서 우리는 `index.html` 파일과 `contacts.html` 파일을 갖습니다. 실제 웹사이트에서 `index.html` 는 우리의 **홈페이지 또는 랜딩 페이지**(웹사이트의 접속 포인트 또는 웹사이트의 특정 부분이 되는 페이지)가 될 것이다.


:::note

`creating-hyperlinks` 는 처음 들어본다.

:::



- **같은 디렉토리(폴더):** `contacts.html`을 가리키는 하이퍼링크를 `index.html`(최상위 레벨 `index.html`) 안에 포함하려면 현재 파일과 동일한 디렉토리에 있으므로 연결하려는 파일의 이름만 지정하면 된다. 따라서 사용할 URL은 `contacts.html` 다.

```html
<p>
  Want to contact a specific staff member? Find details on our
  <a href="contacts.html">contacts page</a>.
</p>
```

- **하위 디렉토리로 하향 이동:**

```html
<p>저의 <a href="projects/index.html">프로젝트 홈페이지</a>에 방문해주세요.</p>
```

- **부모 디렉토리로 상향 이동:** `pdfs/project-brief.pdf`를 가리키는 하이퍼링크를 `projects/index.html` 안에 포함하려면 디렉토리 레벨을 올린 다음 다시 pdf 디렉토리로 내려가야 합니다. "상위 디렉터리 이동"은 두 개의 점(`..`)을 사용하여 표시합니다. 따라서 사용할 URL은 `../pdfs/project-brief.pdf` 입니다.

```html
<p>나의 <a href="../pdfs/project-brief.pdf">프로젝트 개요</a> 링크입니다.</p>
```


## **문서 조각** {#2928de2929404bf79107b7bc7c869df8}


HTML 문서 내부의 특정 부분(Document fragments, 문서 조각)에 연결할 수 있다.


그러기 위해서는 먼저 연결하고 싶은 태그에 `id` 속성을 넣어야 한다.


```html
<h2 id="**Mailing_address**">Mailing 주소</h2>
```


```html
<p>
  우리에게 메일을 보내고 싶나요? 그럼
  <a href="contacts.html**#Mailing_address**">메일 주소</a>를 확인해주세요.
</p>
```


```html
<p>
  <a href="#Mailing_address">회사 메일 주소</a>는 페이지의 하단에서 찾을 수
  있습니다.
</p>
```


## **절대 URL과 상대 URL** {#3ee950f977e84c3691c79607f1a1b473}


**절대 URL:** [<u>**protocol**</u>](https://developer.mozilla.org/ko/docs/Glossary/Protocol)<u>**과**</u> [<u>**domain name**</u>](https://developer.mozilla.org/ko/docs/Glossary/Domain_name)<u>**을 포함한, 웹에서 정의된 절대적인 위치**</u>를 가리킵니다. 예를 들어, 만약 `index.html` 페이지가 `projects` 폴더에 업로드되면 이는 웹 서버의 root 안에 위치하게 되고 웹 사이트의 도메인이 `http://www.example.com`라면, 해당 페이지는 `http://www.example.com/projects/index.html` (혹은 그저 `http://www.example.com/projects/`가 됩니다. <u>_**대부분의 웹 서버는 URL에서 명시되지 않은 경우 페이지를 불러오기 위해**_</u> <u>_**`index.html`**_</u><u>_**과 같은 랜딩 페이지를 찾습니다.**_</u>)


절대 URL은 **어디에 사용되든 항상 같은 장소를 가리킵니다.**


**상대 URL:** 연결되어 있는 파일(과거 섹션의 파일 같은)로부터 상대적인 위치를 가리킵니다. 예를 들어, 여러분이 예시 파일 `http://www.example.com/projects/index.html`에서 같은 디렉토리에 있는 PDF 파일로 연결하고 싶다면, URL은 `project-brief.pdf` 과 같이 파일이름이어야 할 것입니다. 추가 정보는 필요 없습니다. 만약 PDF 파일이 `projects`의 하위 디렉토리인 `pdfs`에 있다면, 상대 URL은 `pdfs/project-brief.pdf`일 것입니다. (같은 URL이지만 절대 경로로는 `http://www.example.com/projects/pdfs/project-brief.pdf`로 표현할 수 있습니다.)


상대 URL은 파일의 실제 위치가 어디냐에 따라 다른 장소를 가리킬 것입니다. 예를 들어 여러분이 `index.html` 파일을 `projects` 디렉토리에서 웹사이트의 root로 옮긴다면 (어느 디렉토리에도 포함되지 않는 최상위 디렉토리), `pdfs/project-brief.pdf` 의 상대 URL은 `http://www.example.com/pdfs/project-brief.pdf`를 가리킬 것입니다. `http://www.example.com/projects/pdfs/project-brief.pdf`를 가리키지 않습니다.


# **Link 실습** {#343f27bb8bd042cdb68262be39d9477a}

