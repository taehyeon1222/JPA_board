# JPA_BOARD_service

스프링 부트 JPA 게시판 개인 프로젝트 입니다.

# 💻프로젝트 소개
한달이라는 기간을 미리 정해두고 여러 게시판 사이트를 참고 하여 제작하게된 회원 전용 게시판 사이트 입니다.
css는 부트스트랩을 이용하여 직접 여러 사이트를 방문하여 커스터마이징 하였습니다.
* #### 개발기간 : 2023.05.18 ~ 2023.06.18
* #### 개발 인원 : 1명(노태현)
* #### 개발 언어: JAVA 19.02
* #### 백엔드 개발 환경: SpringBoot 3.0.5, IntelliJ IDEA, jpa(Spring Data JPA), Spring Security ,oracle(22.3.3)
* #### 프론트 개발환경 : html5,thymeleaf, bootstrap template
* #### 데이터 베이스: oracle(22.3.3)
* #### 형상관리 : GitHub


### ⚙ 주요기능
* #### 회원 가입 페이지
 유효성 검사
 @NotEmpty 로 간단한 유효성 검사

* #### 중복확인

데이터베이스에 존재하는 아이디를 입력한 채 회원가입 버튼을 누른 경우 "이미 사용중인 아이디입니다."의 메시지를 보여주기
<br>이메일,닉네임은 중복가능 모든 검사가 통과되었다면 메인페이지로 이동시키기

* #### 로그인 페이지

로그인을 하지 않은 경우 아래 페이지만 이용가능
회원가입 페이지
로그인 페이지
게시글 목록 조회 페이지
게시글 상세보기 페이지
게시글 검색 페이지
그 외 로그인을 하지 않거나 올바르지 않은 경로로 접속한 사용자가 로그인이 필요한 경로에 접속한 경우 로그인 페이지로 이동
@PreAuthorize("isAuthenticated()") 어노테이션을 사용


* #### 로그인 검사

아이디와 비밀번호가 일치하지 않을 시 "아이디 또는 비밀번호가 일치하지 않습니다. "의 메시지를 보여주기


* #### 게시글부분

게시글 작성, 수정 시 제목과 내용은 공백 혹은 빈칸으로 작성불가능
내가 작성한 글만 수정, 삭제 가능하게 하며 버튼을 노출시키지 않음 로그인을 하지 않고 글 작성 버튼을 누른 경우 로그인 페이지로 이동
그 외 일반적인 방법이 아닌 직접 링크로 접속하는것 또한 방지, 및 공지사항은 관리자 계정만 작성가능
홈화면에서 공지사항 과 추천수가 많은 인기글 순으로 확인가능

* #### 댓글 검사

댓글은 로그인한 사용자만 작성 가능하게 하기
댓글 작성 및 수정시 빈칸 혹은 공백으로 된 경우 “공백 또는 입력하지 않은 부분이 있습니다”의 메시지 보여주기

* #### 추천 기능
추천은로그인 유저만 가능하며 set 으로 입력받아 중복되지 않도록 한번만 추천가능

   


# 🧰 DB 설계

+ ## ERD
![ERD](https://github.com/taehyeon1222/JPA_board/assets/129807676/96443dff-d496-45b7-86ae-19e7f07538a5)

# 🧹 화면설계



![main](https://github.com/taehyeon1222/JPA_board/assets/129807676/90966bcd-0a1f-44d1-bbd3-2d53df4a0015)

메인화면에서는 최근 공지사항과 인기글을 순위별로 모아서 볼 수 있도록 하였다.

![free](https://github.com/taehyeon1222/JPA_board/assets/129807676/f677cd48-8997-4a73-83ae-c5d227b31765)

![3](https://github.com/taehyeon1222/JPA_board/assets/129807676/f1fd3595-fbbe-4d45-ac7c-9a360988c637)

![2](https://github.com/taehyeon1222/JPA_board/assets/129807676/c6037467-af0d-4192-ac69-eff54884f34c)

# 🔨 기능



+ ## 💭프로젝트후기

> 전체적인 부분
+ 간단한 게시판을 통해서 스프링MVC의 흐름에 대해서 경험해 볼 수 있었으며 JPA를 사용하여 CRUD의 대략적인 흐름을 알 수 있었습니다.
  또한 생각했던 부분 보다 많은 부분에서 예외처리 뿐만 아니라 여러 방향에서 생각해야할 것들이 많음을 느꼈습니다.

  
 > 시간과 관련된 부분 
+ 프로젝트와 아르바이트를 병행하면서 작업을 하다보니 생각보다 시간이 많이 빠듯하다고 생각이들었습니다.
또한 개발 초기단계에서 설계의 중요성을 느끼게되었습니다.
초반 한달 이라는 정해진 시간내에서 내가 구현해 내지 못할 기능 까지 미리 틀을 만들어 두고 개발하다보니,
원하던 기능의 60% 밖에 구현 하지 못했으며 나머지 기능들 또한 원하던 부분까지는 구현하였지만 아쉬운 부분이 많았습니다.

> 기능적인 부분
+ 간단한 프로젝트였음에도 많은 부분에서 생각해야했음을 느꼈습니다.
  게시글을 수정하더라도 프론트에서 유저를 검증했어도 백엔드에서 다시 한번 검증을 해야했습니다.
  예를 들면 프론트에서 수정버튼이 나타나지 않더라도 링크를 타고 직접 접근시에는 접근이 가능했던 문제도 있었으며
  쿼리를 잘못작성할 경우 N+1 문제가 발생하기도 하는 문제도 있었습니다.  
  
