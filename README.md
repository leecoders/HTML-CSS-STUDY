# 알게된 내용

## #1.2 태그
- 태그 : 의미에 맞는 적절한 태그를 사용하자.
  - 오류가 나지 않는다고 막 쓰면 안됨
  - [w3schools](https://www.w3schools.com/tags/)에서 태그 검색하자.
- `div` 태그는 Division의 약자로, 레이아웃을 나누는데 주로 쓰인다.
  - 다른 태그와 다르게 특별한 기능을 갖고 있지는 않고, 가상의 레이아웃을 설계하는데 쓰이며, 주로 CSS와 연동하여 쓰인다.

## #1.3 레이아웃을 위한 태그

`header`, `section`, `nav`, `footer`, `aside` 등이 있으며, 레이아웃에도 의미에 맞게 태그가 사용된다.

### 위의 레이아웃을 위한 태그들은 이름만 의미를 가질 뿐, `div`(block element)와 같은 기능을 한다.

### `ul>li*3` -> `엔터` 시 `ul`, `li` 태그 자동 완성

### `html5 layout tag`로 검색하면 의미 있는 태그의 사용 예를 볼 수 있다.

### 브라우저에 따라 HTML5 태그를 지원하지 않을 수 있어서(IE 예전 버전) 보통은 `div` 태그에 `class` 속성으로 지정하며 사용되는 경우가 많지만 모바일에서는 HTML5 태그가 많이 사용된다.

## #1.4 HTML 구조화 설계

### `html structure design`으로 검색한다.

## #1.5 id와 class

### class는 여러 항목들에 공통적으로 속성을 부여하기 위해 사용된다.

### id는 예를 들어, ul, ol의 각 li들 또는 그러한 ui들을 개별적으로 제어하기 위해 사용된다.

### 코딩 스타일 또는 룰을 정하는 것을 `코딩 컨벤션`이라고 한다.

## #2.1 html에 css 적용하기

### selector, property, value로 구성된다.

### inline, internal, external 방법이 있다.
- inline : html의 태그 안에 넣는 방법
- internal : style 태그 안에 정의하는 방법 -> 별도의 css 파일을 관리하지 않아도 되고, 서버에서 css 파일을 따로 불러 들이지 않아도 되는 장점이 있다.
- external : 외부 `.css` 파일로 지정하는 방법 -> 별도로 관리하는 것이 장점이 될 수 있다.
  - `<link rel="stylesheet" type="text/css" href="#" />`으로 css 파일을 `head`에 추가할 수 있다.

## #2.2 css 상속

#### 참고) `div>ul>li*3`으로 편하게 태그를 입력할 수 있다.

### 상위 태그에서 사용된 속성을 하위 태그들에도 똑같이 적용된다.
- 하지만 속성에 따라 상속되지 않고 해당 태그에만 적용되는 것들도 있다.
  - border, padding 등의 배치와 관련된 속성들은 상속되지 않는다.

## #2.3 cascading

### css는 여러 가지 스타일 정보를 기반으로 최종적으로 `경쟁`에 의해 적절한 스타일이 반영된다.
- 경쟁에 따라 css가 적용되는 우선순위 규칙을 `cascading`이라고 한다.

```css
span {
    color: red;
}
span {
    color: blue;
}
```
```css
body > span {
    color: red;
}
span {
    color: blue;
}
```

첫 번째와 같은 경우에는 `span`이 `blue` 색상으로 지정된다.
하지만 두 번째에서는 `red` 색상으로 지정된다. 

- 더 구체적으로 표현된 것이 우선순위가 높음

```html
<div id="a" class="b">
    text...
</div>
```
```css
#a {
    color: red;
}
.b {
    color: blue;
}
```

위와 같은 경우에는 `div`태그가 `red` 색상으로 지정된다.

- `class`보다 `id`가 더 높은 우선순위를 갖는다.
  - 공통으로 속성을 부여하기 위해서는 `class`를 사용하고 그 안에서 몇 가지 항목에만 개별 속성을 주기 위해 `id`를 사용할 수 있다.

- 우선순위 : id > class > element(div 등의 태그를 직접 selector로 사용하는 경우가 가장 우선순위가 낮다.)

### `css specificity`를 검색하면 각 selector 마다의 우선순위 점수를 비교할 수 있다.

## #2.4 css select

### `#id` : 아이디 선택

### `.classname` : 클래스 선택

### `element.classname` :  좀 더 구체적으로 class selector를 지정할 수 있다.

### `selector selector` : 공백으로 하위 요소를 선택할 수 있다. (첫 번째 selector 하위에 있는 모든 두 번째 selector)

### `selector > selector` : `>`으로 자식 요소를 선택할 수 있다. (바로 직계 자식)

### `selector:nth-child(값)` : 해당 selector 중 n번째 요소를 선택할 수 있다.
- n은 1부터 시작한다. (0이 아님)

## #3.1 font

### `em` : 기준값 대비 상대적인 크기 비율을 지정 (1.0을 기준으로 지정)
- `font-size`가 지정되지 않으면 `16px`이 `1.0` -> `2.0`은 `32px`이 된다.
- (상속에 의한)상위 태그의 `font-size`가 지정되면 해당 크기를 기준으로 `1.0`이 지정된다.

### `font-family` 속성을 통해 `서체`를 지정할 수 있다.

## #3.2 box model

### 크롬의 `개발자 도구` -> `element`에서 margin, border, padding 등의 크기를 확인할 수 있다.

### padding, margin의 4개의 크기 값은 시계 방향으로 `위 -> 오른쪽 -> 아래 -> 왼쪽` 순으로 지정된다.
- `margin: 0px 1px 2px 3px` : 위, 오른쪽, 아래, 왼쪽이 다를 때
- `margin: 10px` : 네 방향 모두 같을 때
- `margin: 10px 15px` : 위와 아래가 같고, 오른쪽과 왼쪽이 같을 때

### 인접한 두 개의 `block element`가 서로 다른 margin을 갖고 있다면 더 큰 값을 가진 margin 값이 공유되어 사용된다. (10px+20px=20px)
### 인접한 두 개의 `inline element`의 서로 다른 margin은 각각의 margin 값의 합으로 결정된다. (10px+20px=30px)

> 블록 요소는 모든 인라인 요소를 포함할 수 있고 다른 블록 요소도 일부 포함 할 수 있습니다. 그리고 기본적으로 가로폭 전체의 넓이를 가지는 직사각형 형태가 되며 width, height, margin, padding 등을 사용하여 형태를 변형하여 레이아웃을 수정할 수 있습니다. 그리고 블록 요소 다음에는 줄바꿈이 이루어 집니다.

> HTML5 블록 요소 종류 : address, article, aside, audio, blockquote, canvas, dd, div, dl, fieldset, figcaption, figure, footer, form, h1, h2, h3, h4, h5, h6, header, hgroup, hr, noscript, ol, output, p, pre, section, table, ul, video

> 인라인 요소는 항상 블록 요소안에 포함되어 있으며 인라인 요소안에 다른 인라인 요소가 포함될 수 있습니다. 그리고 기본적으로 컨텐츠가 끝나는 지점까지를 넓이로 가지게 됩니다. 그래서 임의로 width, height로 변형을 줄 수가 없습니다. 인라인 요소는 line-height로 줄의 높낮이를 조절할 수 있고 text-align으로 텍스트의 종앙, 좌,우측 정렬을 할 수 있습니다. 그리고 인라인 요소 다음에는 줄바꿈이 없고 우측으로 바로 이어서 표시가 됩니다. 

> HTML5 인라인 요소 종류 : a, abbr, acronym, b, bdo, big, br, button, cite, code, dfn, em, i, img, input, kbd, label, map, object, q, samp, small, script, select, span, strong, sub, sup, textarea, tt, var [참고](https://junistory.blogspot.com/2017/07/html5.html)

## #4.1 position 속성

### `position: relative` : `원래 위치`를 기준으로 `top`, `right`, `bottom`, `left` 만큼 추가 속성을 통해 상대적으로 위치를 지정할 수 있다.

### `position: absolute` : 상위 `block element` 중에 `position: static`이 아닌 요소의 위치를 기준으로 `top`, `right`, `bottom`, `left` 만큼 위치를 지정할 수 있다.
- 상위 태그의 `position` 상태를 변경하지 않으면 태그들은 전부 기본적으로 `position: static` 상태이기 때문에 `body`가 기준점이 된다.
- `relative`, `absolute`, `fixed`를 발견할 때까지 상위 태그를 탐색한다.

### `position: fixed` : `absolute` 상태와 위치 지정 방법은 비슷(static 아닌 상위 블록 요소를 찾음)하지만 스크롤 시 위치가 변하지 않고 고정된다.

**TIP : `top`, `right`, `bottom`, `left`를 지정하지 않으면 아무 일도 일어나지 않기 때문에 기준이 될 상위 블록 요소에 `position: relative`를 지정하고 `position: relative`를 지정한 태그의 위치를 제어할 수 있다.**

## #4.2 float 속성

### float 속성을 갖는 요소는 공간은 차지하되 다른 요소의 배치에 영향을 주지 않는 요소가 된다.
- 하위 내용(content) 만큼의 크기만 차지하고 상위 블록 요소 안에서 주위의 다른 요소(위, 아래, 오른쪽, 왼쪽)에 관계 없이 left 또는 right에 붙고 다른 요소를 방해하지 않게 된다.

### `left`, `right`, `none`의 속성값이 있다.