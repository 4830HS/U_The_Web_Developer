# **HTML_Semantics**

## *check!*
1. Understanding what HTML5 Actually is
2. Block Vs. Inline Elements
3. span and div elements
4. Semantic Elements (요소들의 수가 많음)
5. sub, hr, sup, br elements
6. VSCode Tip : Emmet

- Inline Elements Vs. Block Elements (주어진 요소가 문서의 컨텐츠 흐름에 들어가게 하는 방법)
    - [Inline Elements Vs. Block Elements](https://res.cloudinary.com/practicaldev/image/fetch/s--y9knEwLf--/c_imagga_scale,f_auto,fl_progressive,h_500,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/i/t6vbjui1jm8q52osgfcj.png, "Elements comparison")
    - | Elements |              exp                 |            ex           |
      |----------|----------------------------------|-------------------------|
      |  Inline  | fit in alongside other elements  | anchor tag (a), span    |
      |  Block   | take up a whole "block" of space | h1, h2, paragraph, div  |

- div Vs. span
    1. div : The Content Division element
        - 요소를 그룹화하는 "제네릭 컨테이너"
        - block element
    2. span
        - 요소를 그룹화하는 "제네릭 컨테이너"
        - Inline element => 전체 블록을 차지하진 않음 (무언가를 그룹화해서 다른 스타일을 적용하는 방법)
            -> ex: span으로 그룹화 한 뒤, CSS에서 빨간색 색상 변경 통해 강조 표시

- 기타 요소 모음 (hr, br, sup, sub)
    1. hr
        - 닫는 태그 없음
        - 수평으로 가로지는 선
    2. br
        - 닫는 태그 없음
        - 줄바꿈 태그
        - 시 (poem)를 생각하면 쉽게 이해
    3. sup : The Superscript element (윗첨자)
        - 제곱이나 위키피디아의 작은 윗첨자 [2] 등의 표시할 때 사용
    4. sub : The Subscript element (아랫첨자)
        - 기준선보다 더 아래에 표시되는 텍스트 표현
        - 화학방정식 (ex: H₂O), 분수 (⅔)

- HTML Entities
    - HTML 대신 쓸 수 있는 특별한 코드 또는 시퀀스
    - 사용하는 이유 : 부등호 (<,>) 등은 HTML에서 태그의 열림과 닫힘에 혼선을 줄 수 있으므로 부등호 대신 Entities를 사용함
    - 형태 : & ... ;
    - ex: &#9824; = ♠

- Semantic Markup
    - 의미 있는 마크업 또는 그 요소의 내용의 의미에 관련된 마크업
    - header, footer, nav, section, article, main => 모두 div와 같은 기능이지만 각자 의미가 있음
    - 종류
        1. section : The Generic Section element
            - generic container
                => 웹사이트나 애플리케이션의 독립적인 부분을 나타낼 뿐, 딱히 다른 기능은 없지만 div보다 훨씬 유용함
            - 어디서든 쓸 수 있음
                => but, section은 내용의 한 부분, 즉 웹사이트의 독립적인 부분이어야 함
                => nav 대신 section도 사용 가능 (div가 모든 것을 대신할 수 있듯이)
            - ex: 글의 문단마다 section으로 구분 가능
        2. article
            - 문서 내의 독립적인 구성 (독립적으로 나뉠 수 있거나 다시 사용될 수 있으면 ok)
            - 내용을 그룹으로 묶을 때 쓰는 또 다른 요소
            - 여러 개의 sub article이 있는 것도 가능
                => 한 페이지에 하나 이상의 article이 있을 수도 있음
            - ex: 여러 사이트에서 사용 가능한 날씨 위젯
        3. nav
            - 페이지에서 네비게이션 링크를 제공하는 것을 의미 (ex: Wikipedia에서 같은 페이지의 다른 부분을 가리키는 링크)
                => 다른 사이트로 이동하는 링크 X (페이지 내에서 다른 곳으로 이동 or 전혀 다른 출처로 이동하는 링크)
            - nav를 꼭 쓸 필요는 없지만 사용시 편리함
            - 필수요소 : 링크
            - 위치 : 반드시 페이지의 맨 위에 있을 필요 X
                => 네비게이션 링크, 사이드 바
        4. main
            - 문서의 주요 내용 포함
            - 페이지의 주요 내용 의미
            - 페이지 전반에서 계속 반복되는 내용은 전부 제외하는 것이 원칙 (ex: sidebars, navigation links, copyright info, site logos, and search forms)
        5. header
            - 내용 소개 부분
            - 종종 네비게이션 관련 내용을 포함함
            - 다른 요소 안에 header를 넣을 수 있음
                -> ex: article 안에 header +
        6. footer
            - 링크, 네비게이션, 중첩된 nav 포함함
            - 다른 요소 안에 footer를 넣을 수 있음
                -> ex: article 안에 footer +
        7. aside
            - 문서의 일부는 아님 (일부가 될 수는 있겠지만, 필요조건은 아님. 간접적으로 연결됨.)
            - ex: 사이드 바, 말풍선
        8. summary
        9. details

- time element
    - inline element
    - 시간/날짜 양 옆에 존재

- figure element : The Figure with Optional Caption element
    - 보통 독립적인 내용 나타냄
    - 구체적인 의미가 부여됨
    - 캡션 (figcaption)이 달린 경우도 있음
    - ex: 일러스트, 다이어그램

- Emmet
    - HTML 작성을 돕는 도구 (이미 VScode에 내장됨)
    - [Emmet doc](https://docs.emmet.io/, "Emmet doc")