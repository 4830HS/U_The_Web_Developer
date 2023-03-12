# **HTML_Forms&Tables**

## *check!*
1. Table Basics : table, tr, td, and th ⭐⭐⭐⭐⭐
2. Table Sections : thead, tfoot, tbody ⭐⭐⭐
3. Table Colspan and Rowspan ⭐
4. Form Element Basics ⭐⭐⭐⭐⭐
5. Button Elements ⭐⭐⭐⭐⭐
6. Labels ⭐⭐⭐⭐⭐
7. Range & Text Areas ⭐⭐⭐
8. Common Input Types ⭐⭐⭐⭐⭐
9. Form Validations ⭐⭐⭐

- HTML Tables : tr, td, th
    1. td : The Table Data Cell element
        - 데이터를 포함한 표 안에 있는 단일 셀
    2. tr : The Table Row element
        - 표 안에 있는 셀들이 모인 행 (그룹 요소나 그룹 셀들을 한 행으로 모은 것)
    3. th
        - 헤더를 정의. 헤더를 행 안에 삽입
            => 열이 3개? 헤더가 3개

- HTML Tables : thead, tbody, tfoot
    - 이 요소들은 표를 논리 섹션으로 분리하는 작업 외에는 하는 일이 거의 없음
        => 그 섹션을 통해 header or footer or body를 구분 가능 (표의 footer는 존재하지 않을 수 있음)

- HTML Tables : colspan & rowspan
    - 여러 열이나 행에 걸친 셀을 생성하는 방법

- HTML Forms
    - The 'form' element itself is a shell or container that doesn't have any visual impact
    - We then fill the form with a collecftion of inputs, checkboxes, buttons, etc.
        -> ex: 이메일 입력란, 텍스트 입력란 등
    - form
        - The form element "represents a document section containing interactive controls for submitting information"
        - The action attribute specifies WHERE the form data should be sent
        - The method attribute specifies which HTTP method should be used
        - Emmet으로 불러오기 : form -> Tab
        - 형태 : <form action=""></form>
        - action 속성 ⭐⭐⭐⭐⭐ : 폼이 제출되었을 때, 데이터를 보낼 위치와 시간은 이 속성이 지정
            => form을 제출하면 HTTP 요청이 전송되며, action이라는 속성을 사용하여 해당 요청이 어디로 가는지 제어함
            => 또한, method라는 속성을 이용하여 어떤 유형의 HTTP method를 사용할 지 제어함
    - 종류
        1. input
            - 닫는 태그 없음
            - 형태 : input id="textInput" class="custom" size="32"
            - placeholder : 입력란의 임시 텍스트를 지정하는 속성 (창에 뭔가를 입력하기 전, 비어 있을 경우 보이는 텍스트)
                - ex: input type="text" placeholder="username"
            - 매우 다양하게 활용됨
            - 20개 이상의 각기 다른 입력란을 만들 수 있음
            - ex: 체크박스, 색상 선택기, 날짜 선택기, 비밀번호 입력란, 일반 텍스트 입력란
            - But, type란 속성이 input의 작동 방식을 크게 바꿈 (The "type" attribute is where the magic happens. Changing type dramatically alters the input's behavior and appearance)
                -> type="submit"인 input
                    - ex: input type="submit" value="Click me"
        2. label ⭐⭐⭐⭐⭐
            - inline element
            - 접근성과 폼을 쓰기 편하게 해준다는 점에서 매우 중요
            - 체크박스와도 연관됨
            - 두 요소를 연결할 때 레이블 자체를 클릭할 수 있게 함
            - label과 입력값 간의 연결은 두 가지 속성을 이용
                1. id
                    - input 태그 안에 id 입력
                    - 한 페이지에는 한 개의 요소만 지정된 id를 지정 가능 (똑같은 id를 다시 사용해서는 안 됨)
                        => 이렇게 해야 정확히 하나의 입력값에만 레이블 지정 가능
                2. for
                    - for 다음에 지정된 id 레이블을 넣으면 서로 연결됨
            - label 요소를 사용해 입력값에 레이블을 지정하는 다른 방법도 있음
                - input을 label 안에 중첩
                - 이 경우, for과 id는 필요 없음
                - but, 중첩은 대부분 사용하지 않는 것이 표준
        3. button ⭐⭐⭐⭐⭐
            - 여는 태그 + 닫는 태그
            - HTML에서 버튼 스타일이 정해져도 나중에 CSS에서 변경 가능
            - 버튼이 form 안에 있을 때 기본값은 submit
            - but, button의 type을 "button"으로 지정하면 그저 클릭만 가능하고 양식을 제출하지 않는 버튼으로 존재
        4. name ⭐⭐⭐⭐⭐ X 2
            - input 내 하나의 속성으로 존재
            - 보통 input의 내용을 name으로 지정
            - ex: 
            <label for="username">Enter a Username:</label>
            <input id="username" type="text" placeholder="username" name="username">
            - 웹페이지의 input 항목에 값을 넣고 버튼을 클릭하여 에러가 나면?
                -> file:///C:/tacos?username=alex&password=1234&color=%23a47474&number=33
        5. checkboxes
            - input 속성에 속함
            - checkbox는 반드시 label 처리해야 함
                -> 그렇지 않으면 복잡해져서 무엇과 관련되어 있는지 알아보기 힘듦
            - 형태 :
            <input type="checkbox" id="scales" name="scales">
            <label for="scales">Scales</label>
                * 만약, 체크박스가 처음부터 체크되어 있도록 만들려면?
                    -> <input type="checkbox" id="scales" name="scales" checked>
                       <label for="scales">Scales</label>
        6. radio button
            - input 속성에 속함
            - checkbox와 거의 비슷하지만, 하나의 차이점은? radio button에서는 한가지만 선택 가능
            - 형태 : 
            <input type="radio" id="huey" name="drone" value="huey">
            <label for="huey">Huey</label>

            <input type="radio" id="dewey" name="drone" value="dewey">
            <label for="dewey">Dewey</label>

            <input type="radio" id="kewey" name="drone" value="kewey">
            <label for="kewey">Kewey</label>
            - 형태에서 value 값이 있어야, 어떤 값을 선택하여 전송했는지 확인 가능
                -> ex: file:///C:/birds?agree_tos=on&size=m
            - 또한, 라디오 박스들의 요소들을 하나의 그룹으로 묶으려면 같은 name으로 정의해야 함
        7. select
            - 드롭다운 메뉴
            - select 요소와 option 요소가 함께 기능하여 나오는 결과물
            - select는 상위 요소. 여러 option을 한 그룹으로 묶음
            - option
                - 여는 태그 + 닫는 태그
                - 두 태그 사이에 텍스트 존재
                - value 속성 있음
            - label 하려면 select에 name과 id를 넣어야 함
            - 형태 :
            <label for="pet-select">Choose a pet:</label>

            <select name="pets" id="pet-select">
                <option value="">--Please choose an option--</option>
                <option value="dog">Dog</option>
                <option value="cat">Cat</option>
                <option value="hamster">Hamster</option>
                <option value="parrot">Parrot</option>
                <option value="spider">Spider</option>
                <option value="goldfish">Goldfish</option>
            </select>
                * 만약, 미리 선택되어 있게 하려면?
                    => option 내에 selected 추가
        8. range
            - input 속성에 속함
            - 슬라이더를 만들어서 사용자가 그 범위 내에서 값을 선택하게 함 (최소값과 최대값 조정 가능)
            - 형태 :
            <input type="range" id="volume" name="volume" min="0" max="11" step="7" value="75">
            <label for="volume">Volume</label>
            - name값을 넣어야 어떤 range (숫자)를 선택했는지 알 수 있음
            - step값을 넣으면 range 선택값이 7 단위로 변함
            - value값을 넣으면 기초값이 value값으로 정해짐
            - number 속성도 같은 원리 (min, max, step...)
        9. textarea
            - input 속성이 아닌, 독립적인 속성
            - 형태 :
            <label for="story">Tell us your story:</label>

            <textarea id="story" name="story" rows="5" cols="33">
            It was a dark and stormy night...
            </textarea>
    - Validations (유효성 검사)
        - 일반적으로 제한을 추가하거나, 사용자 입력 또는 데이터의 유효성을 확인하는 것
        - ex: 어떤 필드는 절대 비어있으면 안 됨 or 비밀번호는 7-12자리여야 함
        - 빌트인 유효성 검사의 기초
            - required 속성
                - 모든 입력을 필수 입력으로 만듦
    - Pattern
        - 패턴 속성을 이용하여 정규 표현식 만들 수 있음 (추후에 배움)
        - 정의된 규칙
        - 이미 패턴 매칭이 되어 있는 요소
            - ex: <input type="email" required>
                -> 진짜 이메일인지 확인하지는 않지만, 이메일의 형식을 띄고 있는지는 확인
            - ex: <input type="url">