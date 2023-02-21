# **HTML?**

*Hypertext Markup Language*

- [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML, "Element Reference")

- h1은 한 페이지 당 하나만 존재해야 함 & 항상 최상위 제목이 되어야 함

- html과 /html 사이에는 head와 body가 들어가야 함
(- html의 기본요소를 담고 있는 문서를 생성하는 단축키 : ! → Tab)
    1. head
        - The Document Metadata (Header)
        - CSS (스타일 공간), JS, 폰트, 아이콘 등 들어갈 공간
        - head 내에 title element 있어야 함
            - title element
                - 브라우저 탭 상에 표시되는 정보
                - 타이틀은 페이지마다 있어야 하는 아주 중요한 요소
                - head 내에 존재
    2. body
        - 문서의 모든 내용을 담고 있는 요소

- 목록 만들기 (두 개 모두 중첩 요소로 이루어져 있음)
    1. 숫자 목록
        - ol 태그 → li 태그
    2. (순서 없이) 점으로 된 목록 
        - ul 태그 → li 태그

- 태그 만들기
    1. a 태그 : The Anchor element
        - 하이퍼링크 만드는 앵커 요소
        - 첫 a 태그 안에 a href="웹사이트 주소"의 형태로 삽입

    2. img 태그 : The Image Embed element
        - 열고 닫는 태그가 없는 instance => img라는 태그만 있고 사이에 아무 컨텐츠가 없음 (이미지가 있는 URL만 제공하면 됨)
        - 태그 안에 img src="웹사이트 주소/파일 경로"의 형태로 삽입
        - img의 사이즈 조절 : src 다음에 width="200px" 추가 (But, img의 사이즈 조절은 CSS 파트에서 하는 것이 더 안정적)
        - img에 대한 부가 설명 : src 다음에 alt="chatGPT_logo" 추가

- 주석 (Comments)
    - <!-- -->
    - 단축키 : Ctrl + /