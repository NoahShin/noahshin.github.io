---
title: "TIL Social Login (kakao)"
date: 2020-12-02
categories: wecode TIL python django projectClnass_101 social_login
toc: true
toc_sticky: true
---
  
# 소셜로그인  
  
![](https://images.velog.io/images/noahshin__11/post/24b3b992-1a67-428e-ac69-08d0002c6c4b/Screen%20Shot%202020-12-02%20at%207.22.27%20PM.png)  
  
  
1. 카카오 로그인 버튼을 누르면 ‘카카오 로그인’ 화면을 부르는 화면을 누르면 2번 화면을 불러오는데 이걸  
~~a: 백엔드가 저 창을 불러오는 코드를 짠다~~  
b: 프론트엔드가 해결한다! <<프론트가 해결  
  
2. 2번창에 내 카카오 id/pw를 입력하고 로그인 버튼을 누른다.  
  
3. 카카오 서버에서 내 카카오 id/pw를 인증authentication (개이득?) 내패스워드도 필요없음  
  
4. Client에게 access token을 준다.  
  
5. Client는 보통 그걸 로컬이나 세션에 저장하지만 이건 백엔드(서버)로 넘겨준다.  
6. 백엔드는 그걸 고이 받아서 다시 카카오서버에 나인척 하고 들어가서  
  
7. 내정보를 빼온다.  
8. 그 정보들을 DB(mysql)에 저장한다.  
  
이게 회원가입  
그니까 이게 말이 회원가입이지  
웹사이트에 맨~ 처음 와서 소셜로그인 했을 때는 내 DB에 그 유저 정보가 없기 때문에 회원가입이라고 한것이다.  
  
  
자 그럼 로그인은...???  
![](https://images.velog.io/images/noahshin__11/post/24b3b992-1a67-428e-ac69-08d0002c6c4b/Screen%20Shot%202020-12-02%20at%207.22.27%20PM.png)  
  
1. 로그인 창을 누른다.  
2. 카카오 id/pw를 입력한다  
3. 카카오 서버에서 인증?authentication 인가를 한다  
4. 카카오 서버에서 클라이언트(프론트)한테 access token을 준다  
5. 클라이언트 서버에서 백엔드(장고서버)한테 그 토큰을 준다  
6. 그 토큰을 가지고 유저인척하고 카카오 서버에 가서  
7. 내게 필요한 정보를 가져온다.  
8. 그걸 이미 저장해놨던 mysql DB와 비교한다  
근데 뭘 비교하죠? 해시된 비밀번호가 없는데 ???  
이제까지는 회원가입때 저장된 해쉬된 비밀번호와 받은 비밀번호를 비교해서 맞으면 토큰을 줬는데???? 이번엔 비밀번호 카카오가 받지 않는가??  
  
정답은 바로:  
애초에 회원가입(첫방문) 때 내 DB에 넣은 정보가 카카오 DB 내 그 유저의email이나 PK이다(which is unique).그래서  
7번의 정보와 내 DB안의 그유저의 카카오 PK or email을 비교해서 맞으면  
  
클라이언트한테 내가 젠한(소금친) 토큰을 준다!!!!  
그리고 클라이언트는 그 토큰으로 웹사이트를 돌아다닌다.  
  
?. 내가 젠한 소금친 토큰을 프론트한테 주고 프론트는 그 토큰으로 웹사이트를 돌아다닌다  

