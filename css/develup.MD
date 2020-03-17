브라우저 호환성
http://caniuse.com
컬러
www.colorzilla.com
폰트
fonts.google.com

css하기전에 user-agent(기본 css)를 다 지워주고 시작해라
body, ul, h1 {
    margin:0;
    padding:0;
}
li {
    list-style-type:none;
}

display
    display:block;  //블록요소
    display:inline; //인라인요소
    display:inline-block; 인라인이면서 블록인 요소

위치이동 float
float를 하게되면 부모의 크기가 없어진다 그래서
float되면 위로뜬다., 안쪽 레이아웃은 그대로지만 컨텐츠는 어울리게된다 (같은 선상에있다) 하지만
레이아웃까지 옆으로 붙게하고싶으면 
display:flow-root 해주면된다.(독립적으로 나눠진다)

부모에게 oveflow:hidden을 주던
부모:after 로 
content 주고 displat:block; clear:both; 모드로주면된다

뜨게되는 float는  부모입장에서 크기를 잃어버리기때문에  부모쪽에서 자식 float의 컨텐츠내용을 인식하려면 아래처럼 해줘야한다.
.container:after {
    content:' '
    display:block;
    clear:both; 
}처리하여 컨텐츠 크기로 감싼다

패딩값을주게되면 컨텐츠 사이즈 + 가 되는데 그걸 포함시키게하고싶으면
box-sizing: border-box; 하면된다.

margin: 0 auto 하게되면 위아래는 0px 양옆은 남은 거 나눠서
중간 정렬된다;
마진을 -값으로 줘서 네거티브로 할수도있다.

글씨 높이 줄간견
line-height: 1.5

transition: all .5s
하여 애니메이션을 줄수있다
transition-delay: .5s

그림자
box-shadow: 0 0 40px rgba(0,0,0,0.2);


width
 auto 하면  margin padding을 고려한뒤  오토로 처리한다.

width를  max-width하여  최대width값으로 할수도있다.
반응형 하기 좋다.

미디어
720px보다작으면 100% 해라
@media (max-width:720px) {
    .col {
        width:100%
    }
}


position
 absolute: 절대 위로뜨고 크기가 컨텐츠 사이즈만큼켜진다.    부모의 상대적인부분에서 절대적
 relative: 상대; 위로 뜬다.
 fixed: 전체스크롤에 영향받지않음

transform
 transform: scale(2)
 transform: translateX(100px) rotate(3600deg)
 transform: skew(30deg)  //기울기
 transform: translate(0,0) // 튀게도;ㄴ다면  부모에게
 transform-origin: center bottom;  //기준점
transition: transform 100ms;

위치
 left: 왼쪽에서..
 top: 위에서..
 transform: translate(-50%, -50%) : 자기 몸의 크기에서 얼만큼 이동한다.

.card {
    position: absolute;
    left:50%;
    top:50%;
    transform: translate(-50%, -50%);
}

배경
background-image: url(...)
background-position:center top;
background-position: right 20px center;
background-size: auto 30px;
background-attachment: fixed 백그라운드를 전체 픽스로.
background-repeat: no-repeat;
background-size: cover;

/* 특별 키워드 값 */
background-color: currentcolor;
background-color: transparent;

/* 전역 값 */
background-color: inherit;
background-color: initial;
background-color: unset;


overflow
overflow: scroll 하게되면 부모의 크기만큼 보여준다. 넘어가는거 안보임. 그외는 스크롤
overflow: hidden 하게되면 float당할때 그대로레이아웃을 유지한다.(시작점이 앞 요소의 끝점에서 시작)
넘처흐르는 것을 짤라 버린다


border: 5px solid blue
boarder-radius: 50%  보더 동그랗게된다.
boarder-radius: 20px
boarder-radius: 50% / 25%  가로 50% 세로 25%
boarder-left: 3px solid #ddd;
boarder-left-color: orange;
boarder-bottom:none;
boarder-width: 30px 30px 0 30px;
boarder-style solid;


clear
- float clear 한다
clear:left

text
text-indent: -999px  들여쓰기  하고 overflow:hidden 해주면 안보인다.
text-decoration: none | line-through | overline | underline | initial | inherit
none : 선을 만들지 않습니다.
line-through : 글자 중간에 선을 만듭니다.
overline : 글자 위에 선을 만듭니다.
underline : 글자 아래에 선을 만듭니다.
initial : 기본값으로 설정합니다.
inherit : 부모 요소의 속성값을 상속받습니다.


자간 (em 폰트사이즈에 비례)
letter-spacing: 0.2em;

마진겹침. 
블럭과 블록의 상하마진은 서로 겹치겠금 설계가되어있다.
이걸 해결하기위해 boarder:1px를 주던가   padding:1px를 주던가 하면된다 하지만 좋은 방법이 아니니
overflow:hidden 하면된다.

전체 확대시키기
.pos {
    position:absolute;
    left:0;
    right:0;
    top:0;
    bottom:0;
    margin: -20px;
}

증가시키기
counter-increment: rank  <-변수명
하위에서 사용할때
.album:before{
    content: counter(rank);
}

애니메이션
@keyframes spin {
    100% {
        transform: rotate(360deg)
    }
}
시용할때
animation-name: spin;
animation-duration: .5s;
animation-iteration-count:5;   // infinite   몇번
animation-timing-function: linear; //가속도
animation-direction: alternate;   방향 애니메이션


align
 vertical-align: bottom;  수직정렬 -> 아래 기준으로 정렬 




z-index

:hover //호버됐을때
:after //자식의 마지막 요소
:before // 자식의 첫번째 요소
:active  //엑티브됐을때

:nth-child(even){}  // 짝수만.