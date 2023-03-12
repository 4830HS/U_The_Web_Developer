# **Othe Assorted Useful CSS Properties**

## *check!*
1. Transitions ⭐⭐⭐⭐⭐
2. Position Property ⭐⭐⭐⭐⭐
3. Opacity & Alpha Channel ⭐⭐⭐
4. Google Fonts ⭐⭐⭐
5. The full story on the background property ⭐⭐⭐
6. Transforms ⭐

- Opacity + Alpha Channel
    - 두 가지 모두 투명도와 관련 되었지만 서로 다른 특성
    - 두 가지의 큰 차이점
        - Opacity를 사용할 때 버튼이나 다른 컨텐츠가 있으면 해당 컨텐츠도 쉽게 영향을 받음
            => 전체 요소 즉 전체 div가 모두 투명해짐
        - 하지만 Alpha Channel에서는 한 요소만 영향을 받음
            => 다른 요소가 있어도 특정 요소의 배경을 투명하게 하지 않으면 영향이 없음
    1. Alpha Channel
        - 색상이 비치는 정도, 즉 투명도를 결정함
        - 텍스트 색상에도 영향을 줌
        - 범위 : 0 (전혀 투명하지 않음) ~ 1 (완전 투명)
        - 형태1 (rgba) => 더 많이 쓰임
            rgba(0, 209, 112, 0.5)
                -> 순서대로 red green blue alpha
        - 형태2 (hex)
            #0000ff + 00 (완전 투명) or FF (완전 불투명)
                => #0000ff5c
    2. Opacity
        - 불투명도
        - 범위 : 0 (완전 투명) ~ 1 (전혀 투명하지 않음)
        - 형태
            opacity(0.5)

- Position Property (위치 속성)
    - 많이 헷갈리는 개념
    - 문서 내에서 요소의 위치를 설정함
    - 이 특성이 설정한 위치에 따라서 네 개의 다른 특성인 top, right, bottom, 그리고 left 등이 결정됨
    - 종류
        1. static
            - default
            - static이므로 top, right, bottom, left에 어떤 값을 줘도 변화 없음
        2. relative
            - 문서의 일반적인 흐름에 따라 위치가 정해지지만, top, right, bottom, left 등으로 현 위치와의 상대적 위치로 offset을 줄 수 있음
        3. absolute
            - 문서의 일반적인 흐름에서 요소가 제거되고 공간도 배정되지 않음
                -> 다만, 문서 흐름에서 제거되어서 다른 공간에 겹쳐짐
            - 가장 가까이 위치한 조상이 있다면 해당 조상을 기준으로 하거나 조상이 가까이 없다면 초기 컨테이닝 블록, 즉 body를 기준으로 상대적인 위치에 배치됨
        4. fixed
            - 일반 문서 흐름에서 제거되고 공간도 차지하지 않으며 초기 컨테이닝 블록의 상대적임
            - fixed로 지정되면 그 자리에 계속 유지됨
            - 배치되는 위치는 항상 컨테이닝 블록에 상대적
            - absolute와 비슷하지만, 부모 요소 같은 것과는 상관 없음
            - 움직이지 않는 네비게이션 바를 만들 때 유용함
        5. sticky
            - 시작할 때는 위쪽에 고정되지 않은 상태로 일단 스크롤을 따라가지만 위쪽에 도달하면 그 위치에 머뭄
            - 스티커처럼 유용하게 쓸 수 있음
                -> 처음에는 고정하지 않았다가 나중에 고정되게 할 수 있음

- Transitions (전환)
    - 한 특성값에서 다른 값으로 변화할 때 전환으로 애니메이션 효과를 주는 것
    - 시간을 설정하여, 정해진 그 시간 내에 전환하게 만듦
    - 주로 hover와 함께 쓰임
    - 주의!!! 한 줄에 한꺼번에 transition을 적용하지 말 것 (추후 일부분만 변경해야 하는 경우가 있음)
    - 특성
        1. Property name
        2. Duration
        3. Timing function
            - 참고 웹사이트 1 : [transition-timing-function](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function/, "transition-timing-function")
            - 참고 웹사이트 2 : [Easing Functions Cheat Sheet](https://easings.net/, "timing functions")
            - transition-timing-function 다양한 종류
                1. ease-in
                    - 천천히 시작됐다가 속도가 점점 빨라짐
                2. steps
                    - 설정한 단계에 걸쳐 변화
                3. etc.
        4. Delay
    - 형태 1
        transition: 1s;
            -> 1초에 걸쳐 서서히 전환
    - 형태 2
        transition: background-color 3s;
            -> 테두리 반경은 바로 바뀌지만 배경색의 경우엔 3초에 걸쳐 transition이 이루어짐
    - 형태 3
        transition: background-color 3s 1s;
            -> 테두리 반경은 바로 바뀜
            -> 배경색의 경우 1초 delay 후 3초에 걸쳐 transition 이루어짐
            -> 이후에도 1초 delay 후 3초에 걸쳐 transition
    - 형태 4
        transition: all 1s 1s;
            -> 모든 특성이 1초에 걸쳐 transition
    - 형태 5 (각각의 특성에 따른 전환 지정)
        transition: background-color 1s, border-radius 2s;
            -> 먼저 1초간 색이 변하고, 테두리가 다 변하기 전에 색 변화 끝

- Transform (변환)
    - 사물을 회전시키고 원근 왜곡, 확대, 축소, 늘리기, 기울이기, 페이지를 가로질러 위아래로 이동, 회전, 크기 조정을 가능하게 함
    - 컨텐츠나 요소에 상관없이 적용 가능
    - 종류
        1. rotate()
            - 회전에는 여러 단위가 필요함
            - 형태
                transform-origin: bottom right;
                transform: rotate(45deg);
                    -> 오른쪽 아래를 핀으로 꽂고 오른쪽 시계방향 45도 각도로 회전
        2. scale()
            - 요소의 크기를 변화시킬 때 사용 가능
            - 값을 하나 이상 넣기도 함
            - 형태 1
                transform: scale(0.5);
                    -> x,y축에서 모두 크기가 50% 줄어듬
            - 형태 2
                transform: scale(2,1);
                    -> 높이는 동일하지만, 너비가 두 배
                        *transform: scaleY(2) -> 반대의 효과
        3. translate(moving)
            - 요소를 움직이는 기능
            - 오른쪽, 위, 아래, 혹은 두 방향으로 동시에 움직일 수 있음
            - 형태 1
                transform: translateY(-200px);
                    -> 위로 200px만큼 이동
            - 형태 2
                transform: translate(-200px, 50px);
                    -> 왼쪽으로 200px만큼, 아래로 50px만큼 이동
        4. skew()
            - 요소를 2차원 평면상에서 기울이는 기능
            - 형태
                transform: skew(10deg, 5deg);
                    -> x 방향 10도, y 방향 5도로 기울임
        * 여러 요소를 조합하여 transform 할 수 있음
            - ex:
                transform: rotate(90deg) scale(1.3);

- Hover effect
    - box shadow (그림자 효과)
        - 형태
            box-shadow: 2px 2px 2px 1px rgba(0,0,0,0.2);
                -> offset-x / offset-y / blur-radius / spread-radius / color */
        - 참고 웹사이트 : [box-shadow](https://developer.mozilla.org/ko/docs/Web/CSS/box-shadow/, "box-shadow")
    
- Background
    - 










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