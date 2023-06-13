프로젝트이름: Web Cafe 시안의 일부분인 (관련 사이트)

# Mission-04

Web Cafe 시안의 일부분인 새소식 부분을
grid를 이용하여 HTML/CSS로 구현해 보았습니다.

html 마크업

main
└── section.news --> contents를 담을 섹션 박스
├── news-title --> 제목
├── news-wrapper
│ └── news-more --> 더보기
│
├── divider[aria-label] --> 구분선
├── news-image --> 뉴스 이미지
│ ├── img
│ └── figcaption
└──news-contents
├── h3
├── date
└── last-contents

CSS

- {
  margin: 0;
  padding: 0;
  font-size: 100%;
  box-sizing: border-box;
  }

main {
background-color: #fff;
width: 500px;
height: 400px;
margin: 0 auto;
font-size: 14px;
line-height: 150%;
}

--> main박스 크기 설정

.news {
display: grid;
width: 380px;
height: 200px;
gap: 12px;
margin: 0 auto;
grid-template-columns: repeat(12, 1fr);
grid-template-rows: auto;
grid-template-areas:
"title title . . . . . . . . more more"
"divider divider divider divider divider divider divider divider divider . . ."
"image image image image imasge contents contents contents contents contents contents contents";
}

-->grid-template-areas를 통하여 grid만들기

.news-title {
color: #ed552f;
grid-area: title;
}

.news-wrapper {
width: 57px;
grid-area: more;
}

.news-wrapper a {
text-decoration: none;
display: flex;
justify-content: space-between;
align-items: center;
}

.divider {
width: 266px;
height: 1px;
background: linear-gradient(90deg, #a9a9a9 -1.32%, #ffffff 100%);
grid-area: divider;
}

.news-image {
grid-area: image;
text-align: center;
margin-top: 12px;
}

.news-image img {
display: block;
}

.news-contents {
margin-top: 12px;
grid-area: contents;
}

-->grid-template-areas를 만들기 위해 grid-area를 주었습니다.

.date {
margin-top: 4px;
}

.last-contents {
text-align: justify;
margin-top: 12px;
}

-->text-align: justify; 자주쓰는 것은 아니지만 텍스트를 정렬하기 위해 사용하였습니다.
