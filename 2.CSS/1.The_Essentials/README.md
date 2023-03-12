# **CSS?**

## *check!*
1. Conceptual Overview of CSS ⭐⭐⭐⭐⭐
2. Basic CSS Syntax ⭐⭐⭐⭐⭐
3. Including Styles Correctly ⭐⭐⭐⭐⭐
4. Color Systems: RGB, Hex, etc. ⭐⭐⭐⭐⭐
5. font-family property ⭐⭐⭐⭐⭐
6. Common Text Properties ⭐⭐⭐

- CSS Rules
    - (almost) everything you do in CSS follows this basic pattern:
        -> selector {
            property: value;
        }
        -> ex1: h1 {
            color: purple;
        }
        -> ex2: img {
            width: 100px;
            height: 200px;
        }
        -> ex3: input[type="text"]:nth-of-type(2n){
            border:2px solid red;
        }
    - 세미콜론 (;)
        - 특정 선언을 마치고 다음 특성으로 넘어간다는 뜻
        - 필수요건

- Including Styles (스타일 적용하는 방법)
    1. Inline styles
        - HTML 요소에 직접 스타일 작성하기
        - 좋은 생각 아님
        - ex: <h1 style="color: purple;">Hello World</h1>
    2. The 'style' element
        - 요소와 중첩되거나 포함되지 않는 스타일 요소를 사용해 문서 대신 CSS를 직접 작성하는 방법
    3. External stylesheet
        - 외부 스타일 시트에서 스타일 작성하는 방법
            -> CSS 작성을 위해 완전히 별개인 새 파일 만들어야 함 (파일 확장자는 .css로 끝나야 함)
        - 연결하기 :
            <head>
                <title>Forms Demo</title>
                <link rel="stylesheet" href="styles.css">
            </head>

- 색 및 배경색 속성
    - background가 background-color보다 더 많은 옵션을 가지고 있음
    - RGB color model
        - red, green, blue channels
        - each channel ranges from 0-255
        - ex1: rgb(255,0,0) -> red
        - ex2: rgb(0,0,255) -> blue
        - ex3: rgb(0,0,0) -> black
        - ex4: rgb(0,255,0) -> green
        - ex5: rgb(255,255,255) -> white
    - 참고 웹사이트 : [Color Picker](https://htmlcolorcodes.com/color-picker/, "Color Picker")
    - Hex
        - still red, green, blue channels
        - each ranges from 0-255 but, represented with hexadecimal
        - 0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F
        - ff = 255
        - #FF/red/ff/green/00/blue
        - RGB보다 Hex가 더 많이 쓰임
        - 중복되는 숫자나 표기가 있을 경우, 하나로 줄여서 쓸 수 있음
            - ex1: #000000 = #000
            - ex2: #cc55ee = #c5e
    - HSL -> 추후 찾아서 공부할 것

- CSS Text Properties
    - 종류
        1. text-align
            - 문단 정렬
        2. font-weight
            - 폰트 굵기
        3. text-decoration
            - 텍스트 꾸미는 선을 조정
            - ex: underline, overline, line-through (취소선)
            - ex: blue underline double
            - <a> 앵커태그 사용하는 경우, 파란색 글씨에 밑줄이 쳐져 있는데, 이때 밑줄을 지우고 싶은 경우?
                -> .css 파일에서
                a {
                    text-decoration: none;
                }
        4. line-height (줄 간격)
        5. letter-spacing (텍스트 글자 사이 간격 조절)
        6. font size (텍스트 일부분의 크기 바꾸기)
            - 종류
                1. Relative : em, rem, vh, vw, %
                2. Absolute : px, pt, cm, in, mm
            - px이 가장 흔히 사용됨
    - Font Family
        - 요소의 폰트를 변경할 때 사용됨
        - 항상 제네릭 대체 폰트로 타입을 지정해서 백업을 넣는 것이 좋음