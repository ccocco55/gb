## 🎨 UI/UX 설계 및 클론코딩

### 벤치마킹 대상: 오늘의집

-   ‘오늘의집’을 참고하여 **화면 구현 능력단위**에서 배운 **HTML, CSS, JavaScript**로 주요 페이지를 직접 구현했습니다.
-   **CSS 전환 효과(Transition)** 와 **JavaScript 이벤트 처리**를 통해 자연스러운 애니메이션을 구현했습니다.
-   실사용자 입장에서의 편의성과 시각적 완성도를 고려해 UI/UX 역량을 강화했습니다.

#### 예시 이미지

<img width="1920" height="1551" alt="ohou" src="https://github.com/user-attachments/assets/472875b1-f960-4e07-b64f-30a1596de4b9" />


#### 실제 클론 코딩 이미지

<img width="1253" height="669" alt="readme" src="https://github.com/user-attachments/assets/e0eec238-2f65-47b7-89bc-82a14d923833" />

---

## 🗂 ERD (Entity Relationship Diagram)

-   **데이터베이스 구현 능력단위**에서 배운 테이블 설계 및 제약조건 설정 방법을 적용하여
    테이블 간의 관계를 체계적으로 구성했습니다.
-   관계 구성 시 정규화를 통해 데이터 중복을 최소화하였고,
    **SQL 활용 능력단위**에서 배운 **DML(INSERT, UPDATE, DELETE, SELECT)** 문법을 사용하여
    더미 데이터를 추가·수정·삭제·조회하며 동작을 검증했습니다.
-   이를 통해 데이터 구조 설계부터 실제 조작까지의 전 과정을 경험했습니다.
<img width="5002" height="6322" alt="erd" src="https://github.com/user-attachments/assets/ef4ad67d-22e8-4954-94a4-bdc1991c1ef3" />

---

## 👩‍💻 담당 업무

-   **화면 구현 능력단위**에서 학습한 JavaScript 이벤트 처리를 활용하여 마이페이지, 상세페이지 등 주요 화면의 사용자 인터페이스를 제작했습니다.
-   **서버 프로그램 구현 능력단위**에서 배운 구조를 바탕으로 **Spring Security**와 **JWT** 를 적용한 로그인 및 인증/인가 기능을 개발했습니다.

### [Back]



<img width="1035" height="293" alt="back" src="https://github.com/user-attachments/assets/5a32eeac-ae29-41a3-8783-760a67754378" />

<br>

▶ **로그인 페이지(웹)**

-   일반 회원 로그인
-   게스트 로그인
-   소셜 로그인

▶ **로그인 페이지(모바일)**

-   일반 회원 로그인
-   게스트 로그인
-   소셜 로그인

▶ **비밀번호 찾기 페이지(웹)**

-   이메일 인증
-   비밀번호 변경

▶ **비밀번호 찾기 페이지(모바일)**

-   이메일 인증
-   비밀번호 변경

▶ **회원가입 페이지(웹)**

-   일반 회원 회원가입
-   소셜 회원 회원가입

▶ **회원가입 페이지(모바일)**

-   일반 회원 회원가입
-   소셜 회원 회원가입
    <br>

### [Front]


<img width="1198" height="469" alt="front" src="https://github.com/user-attachments/assets/79890867-abcc-4d0a-abba-6768780a88b4" />

<br>

▶ **나의 다이어리**

-   다이어리 목록
-   다이어리 작성/수정
-   다이어리 상세

▶ **나의 동행**

-   동행 목록
-   롱크루 목록
-   숏크루 목록

▶ **나의 활동**

-   댓글 목록
-   좋아요 한 게시물 목록

▶ **나의 문의**

-   문의 목록

▶ **나의 구매**

-   구매 목록
-   구매 상세

▶ **나의 판매**

-   판매 목록
-   판매 상세

▶ **내 정보 수정**

▶ **나의 크루**

-   크루 목록
-   크루 상세

<br>

---

## 🚨 Trouble Shooting


#### **( 1 )** 회원과 같은 서비스가 되어버리는 게스트

🌩문제 상황🌩  
<img width="1918" height="992" alt="게스트 글 작성" src="https://github.com/user-attachments/assets/91abdbe0-90cd-4004-92ee-4f68d21a7f2f" />

게스트 로그인 시에도 게시글 작성 페이지에 접근이 가능했습니다.
(게스트 계정은 작성 기능을 사용할 수 없어야 함)

🚨문제 원인🚨  
게스트의 access token이 일반 회원으로 잘못 인식되어
작성 페이지 접근이 허용되었습니다.

🚀해결 방법🚀

1. GuestInterceptor 생성

<img width="1022" height="865" alt="guestInterceptor1" src="https://github.com/user-attachments/assets/5e4d56bd-4a12-42cb-8ed3-9f3a1dd893a1" />   
<img width="1026" height="535" alt="guestInterceptor2" src="https://github.com/user-attachments/assets/73a67c7c-2aeb-4bcf-80b5-b168766ad8bc" />

-   로그인한 사용자의 username이 이메일 형식인지 확인 후
-   이메일 형식이 아니면 게스트 계정으로 분류 했습니다.

2. 게스트 계정이 회원 전용 페이지에 접근하려고 하면
<img width="638" height="896" alt="web1" src="https://github.com/user-attachments/assets/a5899062-7507-42ae-8e74-7d9e140854d6" />     
<img width="626" height="542" alt="web2" src="https://github.com/user-attachments/assets/6d8669ba-a15e-495d-b5cc-64cc9710c000" />



-   로그아웃 처리 후
-   로그인 페이지로 리다이렉트 하였습니다.

✅ 결과: 게스트 계정은 회원 전용 기능에 접근할 수 없도록 안전하게 제한되었습니다.

---

#### **( 2 )** 소셜 로그인 후 일반 회원 로그인 불가

🌩문제 상황🌩  
<img width="581" height="149" alt="문제2" src="https://github.com/user-attachments/assets/c2798326-76a4-4b53-b2cd-75d44793780e" /><img width="1793" height="176" alt="회원가입후로그인" src="https://github.com/user-attachments/assets/7edd24df-2ccd-4b8f-a6ca-3ae64fc355d0" />



소셜 로그인(카카오, 네이버, 구글 등) 이후 로그인 페이지에서 일반 로그인 시도 시 정상적인 계정 정보 입력에도 로그인이 되지 않았습니다.

🚨문제 원인🚨  
소셜 로그인 시 생성된 쿠키(name, provider)가 브라우저에 남아있어 일반 로그인 시 기존 소셜 세션 정보와 충돌이 발생했습니다.

🚀해결 방법🚀

1. resetCookies 메서드 추가

<img width="850" height="705" alt="쿠키 삭제 메소드" src="https://github.com/user-attachments/assets/14c5650b-8adb-4b8f-a0bb-46f7f339a890" />


-   모든 쿠키 및 Redis에 저장된 refreshToken을 삭제하는 메서드 생성했습니다.

2. service.js 수정

<img width="723" height="237" alt="쿠키_서비스" src="https://github.com/user-attachments/assets/cb55ff79-74f7-43b5-8d86-f4a8475db27a" />

-   로그인 요청 전 resetCookies를 비동기(async)로 실행하도록 수정했습니다.

3. event.js 수정

<img width="277" height="54" alt="쿠키 삭제 사용" src="https://github.com/user-attachments/assets/7434780c-b4a7-4335-aa6d-d0450fcd3920" />

-   로그인 페이지 로드 시점에 `memberService.resetCookies();` 호출하여 기존 쿠키 및 세션 데이터 초기화했습니다.

✅ 결과: 로그인 페이지 진입 시 모든 쿠키와 Redis refreshToken이 삭제되어 소셜 로그인 후에도 일반 로그인이 정상적으로 동작하게 되었습니다.

#### **( 3 )** 소셜 로그인 같은 이메일 사용시 같은 회원으로 인식

🌩문제 상황🌩  
<img width="1231" height="682" alt="기존코드" src="https://github.com/user-attachments/assets/cf16c7bf-970a-435a-838a-ce7f21dbee20" />

서로 다른 소셜 로그인이 하나의 이메일을 사용하는 경우, 신규 회원 가입 창이 아닌 기존 회원으로 인식되어 바로 로그인이 되는 문제가 발생했습니다.

🚨문제 원인🚨  
회원 조회 시 이메일만을 기준으로 판단했기 때문에, 소셜 제공자가 다르더라도 이메일이 같으면 동일 회원으로 처리되는 로직이었습니다.

🚀해결 방법🚀

1. MemberMapper.xml 수정

<img width="1435" height="648" alt="제목 없음" src="https://github.com/user-attachments/assets/b77d92f1-a8b1-4bfe-8f29-3d3f72547e1b" />


-   provider 조건을 추가하여 이메일과 소셜 제공자를 함께 조회하도록 수정했습니다.

2. MemberMapper.java 수정

<img width="1449" height="748" alt="mapper-java" src="https://github.com/user-attachments/assets/a1dbcc8e-3db8-402d-bb26-cb4bdabab366" />

-   provider를 매개변수로 추가하여 DAO 계층에서 전달 가능하도록 변경했습니다.

3. MemberDAO.java 수정

<img width="1175" height="682" alt="dao" src="https://github.com/user-attachments/assets/d346d907-fe48-4da9-b650-01e9a4b2eb8a" />

-   이메일과 provider를 함께 조건으로 사용하여 정확한 회원 조회가 가능하도록 수정했습니다.

4. CustomOAuth2UserService 수정

<img width="1128" height="921" alt="스크린샷 2025-10-30 170219" src="https://github.com/user-attachments/assets/f9f95cad-8827-4dd5-8adf-dedce8597473" />

-   OAuth2 인증 과정에서 registrationId를 통해 소셜 제공자(Google, Naver, Kakao 등)를 식별하고, 사용자 정보에서 provider 값을 추출하여 회원 조회 시 이메일과 함께 비교하도록 개선했습니다.

#### **(3-1)** BadSqlGrammarException 오류 발생

🌩문제 상황🌩

<img width="1171" height="180" alt="6-2_오류" src="https://github.com/user-attachments/assets/f12c290d-960c-465a-b8f6-8fe987d84126" />



`BadSqlGrammarException` 예외가 발생했습니다.

🚨문제 원인🚨

<img width="1276" height="72" alt="6-2_기존코드" src="https://github.com/user-attachments/assets/18c476ec-15a4-43aa-9218-ffd12c5bf475" />
<img width="657" height="97" alt="6-2_기존코드2" src="https://github.com/user-attachments/assets/689a78f1-9846-445e-85d1-16e92b481129" />


PostgreSQL에서는 `ENUM`이 사용자 정의 타입(`TYPE`)으로 처리되는데, Java 코드에서 `provider` 값을 단순 `String`으로 전달하면서 타입 불일치가 발생했습니다. 이로 인해 SQL 문법 오류가 발생한 것입니다.

🚀해결 방법🚀

<img width="1154" height="922" alt="스크린샷 2025-10-30 170549" src="https://github.com/user-attachments/assets/164e016c-4539-4a1a-866b-340ceb18d4a8" />
<img width="1025" height="71" alt="변경코드2" src="https://github.com/user-attachments/assets/9bb4aca3-f5c8-4bdf-8355-c03e410ab3ee" />


`MemberProvider` Enum 클래스에서 `provider` 값을 매핑하여, 문자열이 아닌 Enum 객체로 변환한 후 DAO에 전달하도록 수정했습니다.  
이를 통해 PostgreSQL의 ENUM 타입과 정확히 일치하는 값으로 쿼리를 실행할 수 있게 되었고, 타입 불일치로 인한 오류를 해결했습니다.

## 7. 🧪QA 테스트

-   테스트 케이스 설계 및 실행 절차를 기반으로 QA 테스트 문서를 작성하고 기능별 검증을 수행했습니다.  
-   **JUnit5를 활용한 단위 테스트 및 통합 테스트**를 통해 애플리케이션의 안정성과 기능 완성도를 검증했습니다.

<img width="944" height="436" alt="qa" src="https://github.com/user-attachments/assets/e50349b6-da19-42e3-9a99-f74f5fda2f46" />

## 8. 📱앱 전환 - (React Native + WebView)

-    통합 구현 능력단위에서 배운 react-native 기술로 모바일 화면을 구축하였습니다.  
-    웹 화면을 앱에 통합하여 모바일 환경에서도 동일한 사용자 경험을 제공하도록 설계하였습니다.  

<img width="300" height="2556" alt="KakaoTalk_20251113_113604780" src="https://github.com/user-attachments/assets/d8601d5e-f2c3-423d-8bc7-c6288cb3777d" />
<img width="300" height="2556" alt="KakaoTalk_20251113_113604780_01" src="https://github.com/user-attachments/assets/41ae4fb6-9fbc-4969-a99e-cab94d502149" />

---


## 인프라 구축구분

![슬라이드3](https://github.com/user-attachments/assets/21373e41-a50a-4b46-9481-c2eef6b7c810)


---

📌 **작성자:** 임채민 &nbsp;&nbsp;&nbsp;&nbsp; **TEAM:** Crew Station <br>
📅 **기간:** 2025.09.24 ~ 2025.10.19 (**총 프로젝트 기간:** 2025.09.24 ~ 2025.10.24)
