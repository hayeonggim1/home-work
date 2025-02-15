# 마크다운 문법

## 마크다운 Markdown

: 마크업 언어의 일종. 웹 작가를 위한 텍스트-HTML 변환 도구

- 존 그루버(John Gruber)와 아론 스워츠(Aaron Swartz)가 개발
- 읽기도 쓰기도 쉬운 문서 양식을 지향 (↔ HTML)
- 흔히 볼 수 있는 문서(파일명)은 'README.md', 파일의 [확장자](https://namu.wiki/w/%ED%99%95%EC%9E%A5%EC%9E%90)는 .md 또는 .markdown을 쓴다.
- 읽기 쉽고 쓰기 쉬운 일반 텍스트 형식으로 작성한 다음 구조적으로 유효한 XHTML(또는 HTML)로 변환할 수 있다.

## 종류

(1) 일반 텍스트 서식 구문

(2) 일반 텍스트 서식을 HTML로 변환하는 Perl로 작성된 소프트웨어 도구

## 특징

- 디자인 목표 : 가능한 한 읽기 쉽게 만드는 것
- 태그나 서식 지정 지침으로 마크업된 것처럼 보이지 않고 그대로 일반 텍스트로 게시
- 여러 기존 텍스트-HTML 필터의 영향을 받았지만 일반 텍스트 이메일 형식이 가장 큰 원천이다.

## Markdown Syntax

- 블록 요소 : **한 줄 전체를 차지하며, 줄바꿈이 포함되는 요소**
- 스팬 요소 : **문장 안에서 특정 부분만 스타일을 변경하는 요소**

## 01 블록 요소 Block Elements

### (1) **문단과 줄 바꿈**

- 문단 : 단순히 하나 이상의 연속된 텍스트 줄이며, 하나 이상의 빈 줄로 구분
- 두 개이상의 공백 후 줄 마침
- <br /> 줄바꿈 태그 : 줄 끝에 두 개 이상의 공백

### (2) 헤더 **Headers**

- Setext-style header : ‘=’와 ‘-’ 로 밑줄이 그어지는 형태

```jsx
This is an H1
=============

This is an H2
-------------
```

- 아무리 많아도 상관없음

- Atx-style header : 줄의 시작 부분에 1-6개의 해시 문자를 사용

```jsx
# This is an H1

## This is an H2

###### This is an H6
```

```jsx
# This is an H1 #

## This is an H2 ##

### This is an H3 ######
```

- 선택적으로 atx 헤더를 닫을 수 있음. (미용적인 이유)
- 닫는 해시 : 여는 해시 수와 일치할 필요 X
- 1-6까지만 지원 : H7부터는 X

### (3) 인용구 **Blockquotes**

: 이메일 스타일 `>` 문자 사용

- 텍스트 하드래핑하고 모든 줄 앞에 > 추가

```jsx
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.
```

- 문안 맨 앞에만 > 추가

```jsx
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.
```

- > 추가 : 중첩 가능

```jsx
> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.
```

- 헤더, 목록, 코드 블록을 포함한 다른 마크다운 요소 포함 가능

```jsx
> ## This is a header.
>
> 1.   This is the first list item.
> 2.   This is the second list item.
>
> Here's some example code:
>
>     return shell_exec("echo $input | $markdown_script");
```

### (4) 목록 Lists

```jsx
*   Red
*   Green
*   Blue
```

- 순서 없는 목록 : 별표(\*), 더하기 기호(+), 하이픈(-)을 목록 표시자로 사용
- 첫번째 칸을 띄어쓰기 않아도 됨
- 기호를 혼합해서 사용 가능

```jsx
1.  Bird
2.  McHale
3.  Parish
```

- 순서 있는 목록
- 숫자 뒤에 마침표를 사용
- 숫자를 1. 로 통일해도 상관 X
- 숫자는 모두 1로 시작

- 목록을 표시하는 데 사용하는 실제 숫자는 HTML 출력에 영향을 미치지 않음
- 각 행이 HTML의 <li> 태그로 변환될 뿐임 (번호정보가 사라짐)

### (5) 코드 블록 Code Blocks

: 사전 포맷된 코드 블록은 프로그래밍이나 마크업 소스 코드에 대한 글을 쓰는 데 사용

- 일반적인 문단을 구성하는 대신 코드 블록의 줄은 문자 그대로 해석
- 마크다운은 코드 블록을 태그 `<pre>`와 `<code>`태그로 모두 감쌈

- 코드 블록 생성 : 블록의 모든 줄을 최소 4개의 공백이나 1개의 탭으로 들여쓰기

```jsx
This is a normal paragraph:

    This is a code block.
```

```jsx
<p>This is a normal paragraph:</p>

<pre><code>This is a code block.
</code></pre>
```

### (6) 수평선

: 세 개 이상의 하이픈, 별표, 밑줄을 한 줄에 각각 배치하여 가로줄 태그( `<hr />`)를 생성

- 페이지 나누기 용도로 많이 사용

```jsx
* * *

***

*****

- - -

---------------------------------------
```

## 02 스팬 요소 Span Elements

### (1) 링크 Links

- 인라인 / 참조 두 가지 스타일의 링크 지원
- 링크 텍스트 : 두 스타일 모두 대괄호([])로 구분됨

- **인라인** Inline 링크 : 링크 텍스트의 닫는 대괄호 바로 뒤에 일반 괄호 세트를 사용
- 괄호 안에 링크가 가리키기를 원하는 URL과 링크의 제목을 따옴표로 묶음

```jsx
This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.
```

- **참조** Reference 링크 : 두 번째 대괄호 세트를 사용, 그 안에 링크를 식별하기 위해 선택한 레이블 입력
- 선택적으로 공백 사용 : 괄호 세트 구분 가능
- 문서 소스 더 읽기 쉬움.

```jsx
This is [an example][id] reference-style link.
```

- 그런 다음 문서의 어느 곳에서나 다음과 같이 한 줄에 링크 레이블을 정의 (링크 정의)
- 링크 정의는 마크다운 처리 중 링크를 만드는 데만 사용, HTML 출력에서는 문서에서 제거됨
- 링크 정의는 마크다운 문서의 어디에나 배치 가능

```jsx
[id]: http://example.com/  "Optional Title Here"
```

ex)

```jsx
I get 10 times more traffic from [Google] [1] than from
[Yahoo] [2] or [MSN] [3].

  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"
```

### (2) 강조 Emphasis

: 별표( `*`)와 밑줄( `_`)을 강조 표시로 취급

```jsx
*single asterisks*

_single underscores_

**double asterisks**

__double underscores__
```

### (3) 코드 Code

: 코드 범위를 나타내려면 백틱 따옴표( ```)로 묶음

- 일반 문단 내의 코드 (↔ 코드 블록)

```jsx
Use the `printf()` function.
```

- 여러 줄의 코드는 다음과 같이 줄 첫 부분을 공백 4칸 이상 띄어서 씀

```jsx
다음은 Clojure의 예시 코드다.
clojure
    #!/usr/bin/env clojure
    (println "Hello, World!")
```

### (4) 이미지 Images

- 링크 구문과 유사한 이미지 구문 사용
- 인라인 / 참조 스타일 이용

- 인라인 이미지 구문 : ‘!’ + [] + ()

```jsx
![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg "Optional title")
```

- 참조 이미지 구문 : 이미지 참조는 링크 참조와 동일한 구문을 사용하여 정의
