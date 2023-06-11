프로젝트이름: Web Cafe 시안의 일부분인 (관련 사이트)

# Mission-03

Web Cafe 시안의 일부분인 관련사이트 부분을
Transition을 이용하여 HTML/CSS로 구현해 보았습니다.

html 마크업
newEvent --> 모든 요소들을 담을 가장 큰 박스
│
└transitionBox --> 박스안의 내용들을 채워넣을 메인박스
├── transitionBox**title --> "관련 사이트" 제목부분의 글상자
└── color-title --> ""관련 사이트" 부분에서 "사이트" 부분의 색을 칠하기 위해 따로 클래스를 지정
│
└─ul transition**list --> 관련사이트들의 리스트
├── li
│ └── a[href="제로베이스"]
├── li
│ └── a[href="MDN"]
├── li
│ └── a[href="웹접근성 연구소"]
├── li
│ └── a[href="Web Standards"]
└── li
└── a[href="W3C"]

CSS
\*{
box-sizing: border-box;
}

-->모든 박스사이즈를 보더박스 사이즈로 지정

.transitionBox{
width: 190px;
height: auto;
padding: 12px;
background: linear-gradient(180deg, #cccccc 0%, #eeeeee 100%);
border-radius: 5px;
border: 1px solid #a3a3a3;
}

--> 메인박스의 css
이부분에서 처음에 height: auto; 로 주지 않아서 많이 어려움을 느꼈었다.

.transitionBox\_\_title{
width: 84px;
height: 23px;
font-weight: 700;
font-size: 15px;
line-height: 150%;
color: #181818;
margin: 0;
}

.color-title{
display: inline;
color: #ED552F;
}

--> "관련 사이트" 제목부분 css <h1>

.transition\_\_list{
background: #ffffff;
border: 1px solid #a3a3a3;
border-radius: 5px;
margin-top: 8px;
height: 29px;
overflow: hidden;
padding-left: 35px;
transition: height 0.4s ease-out 0.2s,
padding-top 0.2s ease-out 0.4s,
padding-bottom 0.2s ease-out 0.4s;

}

--> ul태그로 마우스 hover시 위아래로 몇초동안 어떻게 움직일것인지 transition을 이용하였다.
시안과 가장 비슷했던건 ease-out라 생각되어 선택하게 되었다.
이부분에서도 많이 어려웠다.

.transition\_\_list:hover{
height: 160px;
padding-top: 8px;
padding-bottom: 8px;
}

li{
list-style: none;
width: 100%;
height: 29px;
font-size: 14px;
font-weight: 400;
line-height: 150%;
text-decoration: none;
padding-top: 4px;
}

a{
display: block;
text-decoration: none;
color: #181818;
padding-left: 0px;
}

--> 처음에 padding을 준적이 없는데 40px씩이나 주어져 있어서 당황했었다.
하지만 padding-left: 0px;를 통해 해결하였다.
