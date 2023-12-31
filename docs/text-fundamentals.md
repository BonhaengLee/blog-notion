---
title: HTML text fundamentals
sidebar_position: 4
slug: /text-fundamentals
---



HTML의 주요 작업 중 하나는 브라우저가 텍스트를 올바르게 표시할 수 있도록 텍스트 구조와 의미(semantics)를 제공하는 것이다. 


| 선행 학습: | [HTML 시작하기](https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML/Getting_started)에서 다뤄봤던 HTML의 기초에 익숙해지기. |
| ------ | -------------------------------------------------------------------------------------------------------------------------- |
| 목표:    | 문단, 제목, 목록, 강조 및 인용구를 포함한 구조와 의미를 부여하기 위해 텍스트의 기본 페이지를 표시하는 방법에 대해 배웁니다.                                                   |


# **기본적인 것: 제목과 단락** {#43c436cd6a4f45fe8230e9ba02486726}


대부분 구조화된 텍스트는 제목과 단락으로 구성된다.


HTML에서 각 단락은 &lt;p&gt; 요소 안에 둘러싸여 있어야 한다.


각 제목은 heading 요소 안에 둘러싸여 있어야 한다.


heading 요소는 총 6개가 있다. - [`<h1>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Heading_Elements), [`<h2>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Heading_Elements), [`<h3>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Heading_Elements), [`<h4>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Heading_Elements), [`<h5>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Heading_Elements), [`<h6>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Heading_Elements).


### **구조화된 계층을 구현하기** {#a595633044f442a7871fcca4e7c30f49}


구조를 만들 때 다음의 몇 가지 관례만 기억하면 된다.

- 가급적 페이지 당 하나의 `<h1>` 만 사용해야 한다.
- 각 표제들은 계층적으로 올바른 순서여야 한다.
- 6개의 heading이 있지만 꼭 필요한 게 아니면 한 페이지에 3개 이상 사용하지 않는다. 많은 목차 레벨을 가진 문서는 탐색이 어렵다. 이런 경우는 가급적 컨텐츠를 여러 페이지로 나누는 것이 바람직하다.

### **왜 우리는 구조가 필요할까요?** {#d1b502eb05d64f2598e80393e5c72e71}


![](/notion_imgs/1339526310.png)


텍스트가 한 덩어리로 뭉쳐있다.


이는 컨텐츠에 구조를 입히는 요소가 없기 때문이다.

- 웹 페이지를 보는 유저는 필요한 컨텐츠를 빠르게 훑어보는 경향이 있고 자주 heading만 읽기도 한다. 몇 초 안에 필요한 어떤 것도 찾지 못하면 실망하고 다른 곳으로 간다.
- 검색엔진들은 페이지 내 heading을 페이지 검색 순위에 영향을 주는 중요 키워드로 고려해 indexing한다.
- 시각 장애를 가진 유저는 웹 페이지를 읽지 못한다. 대신 듣는다. 이는 [screen reader](http://en.wikipedia.org/wiki/Screen_reader) 라고 불리는 소프트웨어를 사용해 이루어진다. 이것은 heading을 읽어줌으로서 문서의 개요를 제공하며 그들의 사용자들이 필요로 하는 정보를 빠르게 찾을 수 있도록 한다. heading이 없어서 스크린 리더가 어쩔 수 없이 문서 전체를 읽어야 했을 것이다.
- 컨텐츠를 [CSS](https://developer.mozilla.org/ko/docs/Glossary/CSS)로 꾸미거나, [JavaScript](https://developer.mozilla.org/ko/docs/Glossary/JavaScript)로 흥미로운 일을 하게 하기 위해서, 관련 컨텐츠를 감싸는 element가 필요하다.

### **활동적인 학습: 컨텐츠에 구조 입히기** {#0d3caf2e33d945f3b6fb001c72fbb837}


…


### **우리는 왜 Semantic을 필요로 할까?** {#69f4a45c55954cf6aed1d8279720a124}


…


예를 들어, 우리는 빨간 신호등을 멈춤, 초록 신호등을 출발로 인식한다. 잘못된 semantic들이 적용되는 경우 상황이 복잡해진다. 


의미론적인 가치는 다양한 방식으로 사용된다. 위에서 예를 든 검색엔진이나 screen reader 등에 의해서.


반면에, 어떤 요소든 최상위 heading처럼 보이게 할 수 있다.


```html
<span style="font-size: 32px; margin: 21px 0;"
  >Is this a top level heading?</span
>
```


이것은 [`<span>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/span) 요소로 의미가 없다. 


당신은 컨텐츠에 추가적인 의미를 더하지 않고 CSS를 적용하고 싶을 때(혹은 JavaScript를 적용해 무언가를 하고 싶을 때) 이것을 사용한다. 
우리는 span에 CSS를 더해 최상위 heading처럼 보이게 했지만, 이것이 semantic(의미론적인) 가치는 없기 때문에, 위에서 서술된 추가적인 이득들은 얻지 못한다. <u>작업에 관계있는 HTML 요소를 사용하는 것이 좋은 생각</u>이다.


# **Lists** {#fa26f0640e8144e1a67f7b31e0c4a948}


## **Unordered (순서 없음)** {#8fba70707706453ebacda263dd984bf2}


```html
<ul>
  <li>milk</li>
  <li>eggs</li>
  <li>bread</li>
  <li>hummus</li>
</ul>
```


### **활동적인 학습 : 순서 없는 리스트 만들기** {#0009e61efe6745108589d8bc2b4f3572}


…


## **Ordered (순서 있음)** {#f8b16169953b4362b399438738ab5ef8}


```html
<ol>
  <li>Drive to the end of the road</li>
  <li>Turn right</li>
  <li>Go straight across the first two roundabouts</li>
  <li>Turn left at the third roundabout</li>
  <li>The school is on your right, 300 meters up the road</li>
</ol>
```


### **활동적인 학습: 순서가 있는 리스트를 만들어보자** {#3490e127d6234754b4f9103a064602ea}


…


## **활동적인 학습: 우리의 레시피 페이지를 만들어보자** {#d525e30e616f4749a6c59a34c0284491}


…


## **리스트 내부의 리스트(Nesting lists)** {#84d00b98543a4487813f3e1838539071}


```html
<ol>
  <li>Remove the skin from the garlic, and chop coarsely.</li>
  <li>Remove all the seeds and stalk from the pepper, and chop coarsely.</li>
  <li>Add all the ingredients into a food processor.</li>
  <li>
    Process all the ingredients into a paste.
    <ul>
      <li>
        If you want a coarse "chunky" hummus, process it for a short time.
      </li>
      <li>If you want a smooth hummus, process it for a longer time.</li>
    </ul>
  </li>
</ol>
```


# **중요와 강조** {#cc53c56ecf464a228873c4fc32e822be}


## **중요(Emphasis)** {#7cca1169ddd24e4bbd6dbaf2ea393bad}


말을 하면서 특정 단어를 강세를 두고 발음하는 방법으로 의미를 다르게 표현한다. 글에서는 단어에 강세를 두기 위해 이탤릭체로 표현하는 경향이 있다. 


예를 들어, 다음 두 문장은 다른 의미를 가진다.


I am glad you weren't late.


I am _glad_ you weren't _late_.


첫 문장은 진심으로 안도하는 것, 두 번째 문장은 비꼬거나 짜증난 것처럼 들린다.


HTML에서 이 경우를 표시하기 위해 [`<em>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/em) (emphasis) 요소를 사용한다. 문서에서 더 흥미롭게 읽게 되고 스크린 리더에 인식되도 다른 톤의 목소리로 표현된다. 브라우저에서 기본적으로 이탤릭체 스타일을 지정하지만 이탤릭체 스타일링을 위해 사용하는 건 지양해야 한다.(span + css이나 i를 쓰자)


## **강조(Strong importance)** {#3ff142ba43f747ce9e7f3f0976cde90b}


강세를 두거나 글자를 두껍게 표현하는 것.


예를들면,


This liquid is **highly toxic**.


I am counting on you. **Do not** be late!


HTML에서는 이러한 경우를 표시하기 위해 [`<strong>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong)[ (en-US)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong) (strong importance)요소를 사용한다. 문서를 더 유용하게 만드는 것뿐만 아니라, 화면판독기에 인식되면 다른 톤의 목소리로 표현다. 브라우저에서는 기본적으로 굵은 텍스트로 스타일을 지정하지만, 단지 굵게 스타일링하기 위해 이 태그를 사용하는 것은 지양해야 한다. .(span + css이나 b를 쓰자)


## **Active learning: Let's be important!** {#a046d3de56354f60b1bd6f82d4425336}


…


## **Italic, bold, underline** {#478afe9a7d4a4061bbc8f1bd8341e3ac}


&lt;b&gt;, &lt;i&gt;, &lt;u&gt; 요소들은 CSS가 형편없이 지원되거나 완전히 지원되지 않는 경우에 사용되도록 고안되었다. 


<u>표현에만 영향을 주는 이 같은 요소를 현재적 요소라 한다. 의미론은 접근성, SEO에 매우 중요하므로 더이상 이렇게 사용되어서는 안된다.</u>


HTML5에서는 `<b>`, `<i>,` `<u>` 를 새로운 의미론적 역할로 재정립하였다.


가장 좋은 경험법칙: 적합한 요소가 더 없다면, 과거로부터 줄곧 굵거나 이탤릭체를 쓰거나 밑줄을 치는 방법으로 표현했던 의미를 전달하기 위해 `<b>`, `<i>`, `<u>` 를 사용하는 것이 적절할 것 같다. 그러나 늘 접근성에 관해 염두하는 것은 항상 중요하다. 이탤릭체의 개념은 스크린리더를 사용하는 사람이나 라틴 문자체계 이외의 사용자에게는 별로 도움이 되지 않는다.

- [`<i>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/i) 요소는 **과거로부터 줄곧 기울임꼴로 전달되는 의미를 전달**하기 위해 사용된다. **외래어, 분류학 명칭, 전문 용어, 생각**...
- [`<b>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/b) 요소는 **과거로부터 줄곧 굵은 글씨로 전달되는 의미를 전달**할 때 사용한다. **주요 단어, 제품 이름, 주요 문장**...
- [`<u>`](https://developer.mozilla.org/ko/docs/Web/HTML/Element/u) 요소는 **과거로부터 줄곧 밑줄을 치는 것으로 전달되는 의미**를 전달할 떄 사용한다. **적절한 이름, 잘못된 철자**...

:::info

밑줄에 대한 위험성 중 하나: **사람들은** <u>**밑줄을 하이퍼링크와 강하게 연관시킨다.**</u> <u>따라서 웹에서는 링크에만 밑줄을 긋는 것이 가장 좋다.</u> 의미론적으로 적합한 경우 `<u>` 요소를 사용하되, CSS를 사용하여 기본 밑줄을 웹에서 더 적합하게 변경할 수 있는지 고려한다. 그것이 어떻게 이루어질 수 있는지는 아래의 예에서 확인할 수 있다.

:::



