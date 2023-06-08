프로젝트 이름:로그인 폼 만들기
HTML 마크업

<div class="mainbox"> 태그로 폼 전체를 묶었다.
<h1 class="login">로그인</h1> 디자인 시안의 로그인을 h1태그를 주어 제목처럼 보이게 했다.
<form action="https://formspree.io/f/xeqwwbwk"  method="POST" class="loginForm" aria-label="로그인 폼">
        <fieldset>
          <legend>로그인 폼</legend>
          <div class="loginForm__group">
            <div class="loginInput">
              <label for="text" class="idinInput__label">아이디</label>
              <input type="text" id="text" name="text" required class="idInput__input" placeholder="euid@euid.deei" />
            </div>
            !! aria-label="로그인 폼", 아이디 input텍스트 폼을 lable를 같이 묶어 웹 접근성을 높이려고 했다. 
            <div>
              <label for="text" class="pwinInput__label">비밀번호</label>
              <input type="text" id="text" name="text" required class="pwInput__input" placeholder="8자리 이상" />
            </div>
          </div>
          !! 비밀번호 input텍스트 폼과 lable을 같이 묶어 웹 접근성을 높이려고 했다.
              <button type="button" class="button">로그인</button>
          </fieldset>
        </form>

      <ul class="joinForm">
                <li>
                  <span class="join"><a href="/">회원가입</a></span>
                </li>
                <li>
                  <span class="find"><a href="/">아이디 비밀번호찾기</a></span>
                </li>
              </ul>
              마지막 회원가입 부분은 ul태그로 묶어 float배치 하였다.

CSS
\*{
box-sizing:border-box;
padding: 0;
}
전체 박스 사이즈를 보더박스로 주었다.

.mainbox{
width: 244px;
height: 161px;
background: linear-gradient(90deg, #ED552F 0%, #E8852E 100%);
box-shadow: 5px 5px 0px #AAAAAA;
border-radius: 5px;
display: flex;
flex-direction: column;
padding: 12px;
}
display: flex;를 이용하여 배치 하였다.

.login{
width: 39px;
height: 23px;
font-weight: 700;
font-size: 14px;
color: yellow;
top: var(--spacing-sm);
left: var(--spacing-sm);
}
로그인 위치,글씨 꾸미기

.loginForm\_\_Wrapper{
background-color: white;
border-radius: 5px;
padding: 4px;
}
form을 감싸는 태그의 css

.loginForm{
position: relative;
width: 210px;
height: 80px;
border-bottom: 1px solid lightgray;
}
form태그에 position: relative;를 주어 전체적인 디자인 배치하였다.

.idinInput\_\_label{
position: absolute;
width: 56px;
height: 21px;
top: 8px;
left: 8px;
}
position: absolute;를 사용하여 position: relative;(기준점)을 기준으로 배치

.pwinInput\_\_label{
position: absolute;
width: 56px;
height: 21px;
top: 37.5px;
left: 8px;
}
position: absolute;를 사용하여 position: relative;(기준점)을 기준으로 배치

.idInput\_\_input{
position: absolute;
top: 8px;
left: 64px;
width: 90px;
height: 24px;
}
position: absolute;를 사용하여 position: relative;(기준점)을 기준으로 배치

.pwInput\_\_input{
position: absolute;
top: 36px;
left: 64px;
width: 90px;
height: 24px;
}
position: absolute;를 사용하여 position: relative;(기준점)을 기준으로 배치

.button{
position: absolute;
top: 8px;
right: 2px;
width: 50px;
height: 53px;
background: #ED552F;
color: var(--white);
border-radius: 5px;
font-weight: 400;
font-size: 13px;
border: 0;
}
버튼 위치, 색, 폰트 사이즈, 폰트 색 등등

.joinForm{
display: block;
padding-top: 4px;
}
.join{
float: left;
font-size: 14px;
width: 60px;
height: 28px;
padding-left:10px;
}

.find{
float: right;
font-size: 14px;
width: 125px;
height: 28px;
padding-right: 4px;
padding-top: 0px;
}
마지막ul태그를 css로 꾸민것이다
join은 float: left;
find는 float: right; 배치하여 디자인 시안과 가깝게 만들었다.
