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

<img alt="Image" src="https://github.com/user-attachments/assets/6e275336-0946-4425-aae2-ccca73d4c320" />

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

## 🚨 오류 상황들

### **📌 1. 회원과 같은 서비스가 되어버리는 게스트**

#### **💥문제 상황**

<img width="1918" height="992" alt="게스트 글 작성" src="https://github.com/user-attachments/assets/771759f1-0bae-4387-8a3b-8a37c2608435" />


-   게스트 로그인 시에도 게시글 작성 페이지에 접근이 가능했습니다.
    (게스트 계정은 작성 기능을 사용할 수 없어야 함)

#### **🔍문제 원인**

-   게스트의 access token이 회원으로 인식되어 작성 페이지 접근이 허용되었습니다.

#### **🛠️해결 방안**

<img width="1026" height="535" alt="guestInterceptor2" src="https://github.com/user-attachments/assets/2847676f-2afb-4174-86e7-72305119a165" />
<img width="1022" height="865" alt="guestInterceptor1" src="https://github.com/user-attachments/assets/3860fc4a-1ce4-4214-914a-fec3b13550f7" />

-   GuestInterceptor를 만들어 게스트 계정이 회원 전용 페이지에 접근하려고 하면 로그아웃 처리 후 로그인 페이지로 리다이렉트 하였습니다.
<img width="638" height="896" alt="web1" src="https://github.com/user-attachments/assets/20b4b94c-7a9f-4d3f-b6d9-d1f3c78b6425" />
<img width="626" height="542" alt="web2" src="https://github.com/user-attachments/assets/52630385-4a69-42a2-adfc-ba25cdcd6d41" />


✅ 결과: 게스트 계정은 회원 전용 기능에 접근할 수 없도록 안전하게 제한되었습니다.

### **📌 2. 소셜 로그인 후 일반 회원 로그인 불가**

#### **💥문제 상황**


<img width="1793" height="176" alt="회원가입후로그인" src="https://github.com/user-attachments/assets/4f1d23b6-787c-44c5-9278-da97bcb7e6ed" />
<img width="581" height="149" alt="문제2" src="https://github.com/user-attachments/assets/abbb9219-f72b-4777-bb1f-f9340cadf599" />

-   소셜 로그인(카카오, 네이버, 구글 등) 이후 로그인 페이지에서 일반 로그인 시도 시 정상적인 계정 정보 입력에도 로그인이 되지 않았습니다.

#### **🔍문제 원인**

-   소셜 로그인 시 생성된 쿠키(name, provider)가 브라우저에 남아있어 일반 로그인 시 기존 소셜 세션 정보와 충돌이 발생했습니다.

#### **🛠️해결 방안**

<img width="850" height="705" alt="쿠키 삭제 메소드" src="https://github.com/user-attachments/assets/aa705c33-6741-4e50-851f-205fa0adff27" />

1. resetCookies 메서드 추가

-   모든 쿠키 및 Redis에 저장된 refreshToken을 삭제하는 메서드 생성.


<img width="723" height="237" alt="쿠키_서비스" src="https://github.com/user-attachments/assets/d5cca0a8-fe19-4be2-b356-60a6806f79e4" />


2. service.js 수정

-   로그인 요청 전 resetCookies를 비동기(async)로 실행하도록 수정.

<img width="277" height="54" alt="쿠키 삭제 사용" src="https://github.com/user-attachments/assets/1a1142c0-3544-4a5c-813c-dfe1559a77b7" />


3. event.js 수정

-   로그인 페이지 로드 시점에 `memberService.resetCookies();` 호출하여
    기존 쿠키 및 세션 데이터 초기화.

---

## 📊 QA 테스트

-   **애플리케이션 테스트 수행 능력단위**에서 배운 테스트 케이스 설계 및 실행 절차를 기반으로
    QA 테스트 문서를 작성하고 기능별 검증을 수행했습니다.
-   **JUnit5를 활용한 단위 테스트 및 통합 테스트**를 통해
    애플리케이션의 안정성과 기능 완성도를 검증했습니다.


<img width="944" height="436" alt="qa" src="https://github.com/user-attachments/assets/abb036b6-7f7a-427d-bdcb-1e9e1080b00e" />

---

## 📱 앱 전환 (React Query + WebView)

-   **통합 구현 능력단위**에서 배운 API 통합 및 데이터 관리 기법을 활용하여
    React Query 기반의 WebView 환경을 구현했습니다.

-   WebView를 통해 모바일 앱 환경 구현

<img width="1170" height="2532" alt="IMG_3122" src="https://github.com/user-attachments/assets/09e5d316-3847-499b-a579-3e7d049b4a56" />

---

## 인프라 구축구분(추가 예정)

---

📌 **작성자:** 임채민 &nbsp;&nbsp;&nbsp;&nbsp; **TEAM:** Crew Station <br>
📅 **기간:** 2025.09.24 ~ 2025.10.19 (**총 프로젝트 기간:** 2025.09.24 ~ 2025.10.24)
