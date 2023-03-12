# **CSS Selectors**

## *check!*
1. Element Selector ⭐⭐⭐⭐⭐
2. Class Selector ⭐⭐⭐⭐⭐
3. ID Selector ⭐⭐⭐⭐⭐
4. Descendent Selector ⭐⭐⭐⭐⭐
5. Adjacent Selector ⭐⭐⭐
6. Direct Descendent Selector ⭐⭐⭐
7. Atrribute Selector ⭐⭐⭐
8. Pseudo Elements ⭐⭐⭐
9. Pseudo Classes ⭐⭐⭐
10. CSS Specificity (CSS 우선순위) : 스타일이 상충할 경우, CSS가 적용할 스타일을 선택하는 방법 (두 개의 선택자의 타깃이 동일한 하나의 요소라면 둘 중 어떤 것을 선택해야 하는 것인지) ⭐⭐⭐⭐⭐

- CSS Selectors (CSS 선택자)
    - 형태 :
        selector {
            property: value;
        }
    - 종류
        1. Universal Selector (전체 선택자)
            - 문서의 모든 요소를 다 선택
            - 크기가 큰 문서에서는 다소 비효율적
            - 형태 :
                * {
                    color: black;
                }
        2. Element Selector
            - 지정된 타입의 모든 항목을 선택
            - 형태 :
                img {
                    width: 100px;
                    height: 200px;
                }
        3. Selector List
            - 쉼표를 사용해서 목록에 있는 선택자 여러 개를 합치는 방법
            - 형태 :
                h1, h2 {
                    color: magenta;
                }
        4. ID Selector
            - 흔히 쓰임
                -> but, 너무 과용해선 안됨
            - 반드시 #를 써야 하며 빈칸은 없어야 함
            - id를 훅으로 사용
            - 하나의 id는 페이지 내에 한 번만 나와야 함 (중복 X)
                ∵ <- id는 고유한 식별자여야 함
            - 형태 :
                #logout {
                    color: orange;
                    height: 200px;
                }
        5. Class Selector
            - 클래스는 ID와 비슷한 개념으로 마크업에 무언가를 추가한 뒤, 훅을 걸어 CSS로 연결
            - 단, 클래스는 여러 요소에 적용됨
            - 클래스가 요소를 묶어주기 때문에 몇 개의 그룹을 만들어 비슷한 스타일을 적용할 수 있음 (일반적인 웹사이트)
            - 형태 :
                .complete {
                    color: green;
                }
            * ID Selector (#)와 Class Selector (.)를 혼동하지 않도록 주의할 것!
        6. Descendant Selector (자손 선택자)
            - 띄어쓰기 이용 (공백이 중요)
            - 형태 :
                li a {
                    color: teal;
                }
                    -> li 태그에 중첩된 모든 자손 요소를 선택하라는 뜻 (li 태그 안의 앵커 태그)
                        => li 태그는 선택하지 않는 것
        7. Adjacent Selector (인접 선택자 = 결합자)
            - 형태 : 
                h1 + p {
                    color: red;
                }
                -> 요소 선택자 : h1, p
                -> 인접 선택자 (결합자) : + (전체 선택의 명령을 바꿈)
                => +는 h1 태그 바로 다음에 오는 p 태그를 모두 선택하게 함
        8. Direct Child Selector (직계 자손 선택자)
            - 형태 :
                div > li {
                    color: white;
                }
                -> > : div 태그 바로 아래에 있는 li 태그를 선택함
                => 다른 일반 자손과는 달리 div의 직계 자손
        9. Attribute Selector (속성 선택자) => MDN 참고할 것
            - 특정 속성을 가진 요소를 선택할 수 있음
            - 형태1 :
                input[type="text"] {
                    width: 300px;
                    color: yellow;
                }
                -> input 내 type="text"인 모든 것들은 다음의 width와 color를 적용한다는 뜻
            - 형태2 :
                a[href*="google"] {
                    color: red;
                }
            - 형태3 :
                a[href$=".org"] {
                    font-style: italic;
                }
                -> .org로 끝나는 href에 대해 다음의 스타일 적용
                -> 단순히 href 뿐만 아니라, 다른 속성에 대해서도 적용 가능
        10. Pseudo Classes (가상 클래스)
            - modifier의 역할을 함
            - 가상 클래스는 선택자 끝에 붙여 상태를 특정하는 키워드
            - 종류
                1. :active
                    - 무언가가 현재 활성화되어 있다는 뜻
                    - 버튼 클릭에 상당히 많이 사용됨
                    - 활성화되었을 때 다른 색이나 상태를 부여
                2. :checked
                    - 체크된 라디오 버튼이나 체크박스를 선택할 수 있음
                3. :first
                4. :first-child
                5. :hover
                    - 자주 쓰임
                    - 형태 :
                        a:hover {
                            color: orange;
                        }
                        -> selects any <a> element when hovered
                    - ex: tag라는 클래스 안의 버튼에만 hover를 적용하고 싶을 경우?
                        -> .tag button:hover {
                            color: orange;
                        }
                6. :not()
                7. :nth-child()
                8. :nth-of-type()
                    - 형제 그룹 내 위치에 따라 선택할 수 있게 하는 것
                    - 형태 :
                        .post:nth-of-type(3) {background-color: cadetblue;}   
        11. Pseudo Elements (가상 요소)
            - 가상 요소도 modifier나 선택자처럼 덧붙일 수 있는 요소
                -> but, 선택된 요소의 특정 부분만 선택
            - 종류
                1. ::after
                2. ::before
                3. ::first-letter
                    - 특정 선택에서 첫 글자를 선택하는 방법
                    - ex: 모든 단락이나 모든 span의 첫 글자 선택 가능
                4. ::first-line
                    - first-letter와 비슷한 원리로 특정 선택에서 첫 줄을 선택하는 방법
                5. ::selection
                    - 선택한 뒤 드래그하면 원하는 상태로 적용되게 하는 요소
                    - 형태1 : 문서의 모든 것에 적용되게 하는 방법
                        ::selection {
                            background-color: cyan;
                        }
                    - 형태2 : 문서의 특정된 부분에 적용되게 하는 방법
                        p::selection {
                            color: red;
                        }
            - Pseudo Classes와 Pseudo Elements의 차이 잘 알아둘 것!
                -> Pseudo Elements의 경우, 어떤 대상이나 선택한 요소의 일부를 선택함
        12. The Cascade
            - The order your styles are declared in and linked to matters!
                -> 이 순서는 하나 이상의 스타일시트가 있을 경우에도 중요함
            - ex1:
                h1 {
                    color: red;
                }
                h1 {
                    color: purple;
                }
                => Purple wins
            - ex2:
                <link rel="stylesheet" href="app.css">
                <link rel="stylesheet" href="app1.css">
                -> app1.css 스타일시트의 적용을 받음
        13. What happens when conflicting styles target the same elements?
        => Specificity (특이도)
            - 특이도는 충돌이 생길 경우, 브라우저에서 규칙으 적용하는 방법
            - 하나 이상의 스타일이 동일한 요소에 적용되거나 적용될 수 있는 경우엔 충돌이 발생 
            - 이 경우, 브라우저는 더 구체적인 선택자를 우선적으로 적용함 (경쟁 선택자보다 우선시)
                -> ID > CLASS > ELEMENT
                * 참고 웹사이트 : [특이도 계산기 도구](https://specificity.keegan.st/, "Specificity")
        14. Inline Styles
            - ID, Class, Elements보다 더 명시적인 선택자
                -> INLINE STYLES > ID > CLASS > ELEMENT
            - but, 이것의 사용을 추천하거나 실제로 쓰는 사람은 거의 없음 (되도록 안 쓰는 것이 좋음)
            - ex:
                <button id="signup" style="color: olive">Sign up</button>
        15. The !important exception
            - 개별 스타일 지정에 사용할 수 있는 선택자
            - 이것도 되도록 안 쓰는 것이 좋음
            - 형태 :
                <div class="foo" style="color: red;">What color am I?</div>
                .foo[style*="color: red"] {
                    color: firebrick !important;
                }
                -> 특성 뒤에 입력
                -> 이 태그는 브라우저가 이것을 가장 명시적인 지시로 인식하게 함 (다른 어떤 지시보다 우선함)
                    => 특이도와는 상관없는 선택자이지만, 매우 명시적
        16. Inheritance (상속)
            - 구체적인 특성을 지정하지 않은 하위 요소에 상위 항목 특성이 적용되는 것
            - 상속이 모든 요소를 포함하는 것은 아님
                -> 상속받지 못했을 경우의 상속 방법
                    button, input {
                        color: inherit;
                    }
                    => 상속받지 못한 buttn과 input은 이제 해당 상위 요소의 상속을 받음