프로젝트이름: Web Cafe 시안의 일부분인 (관련 사이트)

# Mission-05

Web Cafe 시안의 일부분인 관련 사이트 부분을
sprite를 이용하여 HTML/CSS로 구현해 보았습니다.

#이번에는 flex와 grid는 제외하고 position만 사용해서 완성해 보고싶었습니다.
조금 미완성이지만 flex와 grid가 없이도 비슷한 시안을 완성할 수 있었습니다.

html 마크업

main class="mainbox" --> 콘텐츠를 포함하고 있는 가장 큰 메인박스
└── section class="favorite" --> 섹션으로 묶기
├── h2 class="favorite-title" --> 제목
│ └─span class="accentFavorite" --> 관련 사이트 중 사이트 부분
│  
├── ol class="favorite**list" --> ol태그로 묶인 리스트들입니다.
│ └─li class="favorite**item sprite spriteup"
│ │ └─a class="favorite**link" href="/"
│ └─li class="favorite**item sprite spritedown"
│ │ └─a class="favorite**link" href="/"
│ └─li class="favorite**item sprite spritedash"
│ │ └─a class="favorite**link" href="/"
│ └─li class="favorite**item sprite spriteup"
│ └─a class="favorite\_\_link" href="/" --> spriteup, spritedown, spritedash sprite로 이미지를
│ 맞춰주기 위해 클래스를 이렇게 묶었습니다.  
└─ a href="/" class="favorite-more" --> 더보기

CSS
@import url(/css/normalize.css);
@import url(/css/reset.css);
@import url(/css/a11y.css);
@import url(/css/theme.css);
@import url(/css/base.css);

.mainbox{
width: 800px;
height: 800px;
margin: 50px;
}
=> 가장 큰박스로 모든 콘텐츠를 담을 수 있게 넉넉하게 크기와 마진을 잡았습니다.

.favorite{
width: 190px;
height: 170px;
background: linear-gradient(180deg, #CCCCCC 0%, #EEEEEE 100%);
border: 1px solid #A3A3A3;
border-radius: 5px;
padding: var(--spacing-sm);
position: relative;
}
=>관련 사이트 부분의 상자콘텐츠 부분입니다. position: relative를 준 이유는 .favorite-more에 (더보기)
position: absolute;를 이용하여 더보기의 위치를 수정하기 위해 주었습니다.

.favorite-title{
font-size: 15px;
font-weight: 700;
line-height: 150%;
color: #181818;
margin-bottom: var(--spacing-xs);
}
=>제목부분입니다.

.accentFavorite{
color: #ED552F;
}
=> 관련 사이트 중 "사이트" 부분이 색이 다르기 때문에 따로 마크업하고 css를 주었습니다.

.favorite\_\_list {
list-style: none;
padding-left: 0;
}
=> ol태그로 에이전트 스타일로 padding이 있어 padding 을 줄였습니다.

.favorite\_\_item {
counter-increment: number;
margin-bottom: var(--spacing-xs);
}
=> counter-increment: number; 뒤의 css에서 카운터 함수를 사용하기 위해 작성하였습니다.

.favorite\_\_item::before {
content: counter(number);
display: inline-block;
text-align: center;
color: #fff;
line-height: 120%;
width: 20px;
height: 20px;
background: #A3A3A3;
border-radius: 5px;
}
=> 가상요소소 before를 사용하여 콘텐트부분에 카운터 함수를 사용하였습니다.

.sprite {
background: url(./../images/rank.png) no-repeat;
}
=>sprite 이미지를 background이미지로 주었습니다.

.spriteup{
background-position: 155px 7px;
}
=> up이미지가 들어갈 부분

.spritedash{
background-position: 155px -15px;
}
=>dash이미지가 들어갈 부분

.spritedown{
background-position: 155px -35px;
}
=>down이미지가 들어갈 부분

========> 각자 이미지의 위치에 맞기 y축을 움직였습니다.

.favorite-more{
position: absolute;
top: 0;
right: 0;
padding-top: var(--spacing-sm);
padding-right: var(--spacing-sm);
font-size: 14px;

}
=> 위에서 말했던 것과 같이 position: absolute를 사용하여 더보기 의 위치를 수정하였습니다.
