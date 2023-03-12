# **The Box Model**

## *check!*
1. Width & Height ⭐⭐⭐⭐⭐
2. Border ⭐⭐⭐⭐⭐
3. Padding ⭐⭐⭐⭐⭐
4. Margin ⭐⭐⭐⭐⭐
5. Display Property ⭐⭐⭐⭐⭐
6. Units - Percentages, EMS & REMS ⭐⭐⭐⭐⭐
7. Border Radius ⭐

- 웹페이지 제작 전부터 전체 여백을 0으로 만들고 시작함
    - 형태
        body {
            margin: 0;
        }
        -> 추후, 필요한 경우 여백을 만들어 나가면서 제작함

- Width & Height
    1. Width : 가로
    2. Height : 높이

- Border (테두리)
    - 요소를 둘러싸고 있는 박스 모델의 테두리
    - 테두리와 연관된 특성이 다양하게 있음
    - Border Properties (테두리 주요 특성)
        1. Border-width (테두리 두께)
            - controls the thickness of the border
            - border-left-width: 8px;
                - border의 왼쪽 두께만 8px로 변경
        2. Border-color (테두리 색상)
            - controls the color of the border
            - border-left-color
                - border의 왼쪽 색상만 변경
        3. Border-style (테두리 스타일)
            - contorls the line style - dashed, solid, etc.
        * box-sizing: border-box;
            - border-width를 적용했을 때 테두리의 선이 기존의 선보다 바깥쪽으로 튀어나왔을 때, 테두리 선에 맞추어 박스 사이즈를 조정하는 방법
    - 속기법 (border의 속성을 보다 한번에 빠르게 적용시키는 방법)
        - 순서 : 두께 -> 스타일 -> 색상
        - 형태
            border: 4px solid white;
    - Border-radius (테두리 모깎기)
        - 형태
            border-radius: 30px;
            or
            border-radius: 25%;
        - 50%는 보통 원형 모양의 이미지를 만들 때 사용

- Padding
    - 컨텐츠 박스와 요소를 둘러싼 테두리 사이에 남은 공간
    - px, mm 등 여러가지 단위 적용 가능
    - Padding Properties (패딩 주요 특성)
        1. Individual Properties
            1. Padding-left
            2. Padding-right
            3. Padding-bottom
            4. Padding-top
        2. Shorthand Property (Set all four sides at once) => 속기법
            1. Apply to all four sides
                - padding: 10px;
            2. vertical -> horizontal
                - 첫 번째 값 : 상하
                - 두 번째 값 : 좌우
                - padding: 5px 10px;
            3. top -> horizontal -> bottom
                - 첫 번째 값 : 상단
                - 두 번째 값 : 좌우
                - 세 번째 값 : 하단
                - padding: 1px 2px 2px;               
            4. top -> right -> bottom -> left
                - padding: 5px 1px 0 2px;

- Margin (여백)
    - 요소와 요소 사이, 두 요소에 둘린 각 테두리 간의 간격
        * Padding : 테두리 안 쪽의 공간
        * Margin : 바깥 공간
    - Margin Properties (Margin 주요 특성)
        1. Individual Properties
            1. Margin-left
            2. Margin-right
            3. Margin-bottom
            4. Margin-top
        2. Shorthand Property
            - Padding의 속기법과 같은 원리

- Display Property (디스플레이 특성)
    1. Inline
        - Width & Height are ignored. Maring & Padding push elements away horizontally but not verically.
        - h1은 Block 요소이지만, inline display 속성을 부여해 줌으로써 Inline 요소로 변경 가능
        - ex:
            h1 {
                background-color: tan;
                border: 1px solid red;
                display: inline;
            }
    2. Block
        - Block elements break the flow of a document. Width, Height, Margin & Padding are respected.
        - span은 Inline 요소이지만, block display 속성을 부여해 줌으로써 Block 요소로 변경 가능
        - ex:
            span {
                background-color: hotpink;
                border: 1px solid black;
                display: block;
            }
    3. Inline-Block
        - Behaved like an inline element except Width, Height, Margin & Padding are respected.
        - inline-block 요소를 적용하면 block 요소가 인라인 요소처럼 작동함
        - ex:
            div {
                height: 200px;
                width: 200px;
                background-color: aqua;
                border: 5px solid red;
                display: inline-block;
            }
                -> 세 개의 블록이 공간을 공유하면서 같은 줄에 나란히 있음
    * display: none;
        => 존재하지만 공간을 차지하지 않게 됨 (다만 디스플레이에 보이지 않는 것일 뿐)

- CSS Units (CSS 단위)
    1. Relative
        - EM
            - with font-size, 1em equals the font-size of the parent. 2em's is twice the font-size f the parent, etc.
            - with other properties, 1em is equal to the computed font-size of the element itself.
            - REM처럼 상대적 단위이며 특성에 따라 다른 값에 영향을 받음
            - 2em은 부모 요소보다 2배 큰 것임
            - 장점 : 간단한 component나 재사용할 수 있는 항목을 만들어서 해당 글꼴 크기에 맞춰서 달라지게 해야 하는 경우에 em이 더 수월
            - 단점 : 중첩된 ul 요소와 같은 경우, em의 문제가 여실히 드러남
                -> 단계별로 누적되어 가장 안쪽의 글꼴이 가장 크게 보여짐
        - REM (ROOT EMS)
            - relative to the root html element's font-size. often easier to work with.
            - if the root font-size is 20px, 1rem is always 20px, 2rem is always 40px, etc.
                => 문서 전체에서 하나의 글꼴 크기에 비례하여 바뀜
            - rem이 em에 비해 작업하기 쉬워짐
        - VH
        - VW
        - %
            - 항상 다른 값과 상대적
                1. 부모 요소의 절반 너비로 설정
                    - ex:
                        width: 50%
                            => half the width of the parent
                2. 요소 자체의 다른 값에 기반 
                    - ex:
                        line-height: 50%
                            => half the font-size of the element itself
    2. Absolute
        - PX
        - PT
        - CM
        - IN
        - MM