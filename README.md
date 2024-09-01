# :fire: Post Service Project :fire:

Spring, MyBatis 그리고 Thymeleaf 조합으로 블로그 서비스를 구현해본다.

<img width="1470" alt="스크린샷 2024-09-01 오후 11 20 42" src="https://github.com/user-attachments/assets/8be2b6ea-5f74-4e6b-ab1b-bb7560d08dd7">

## :clipboard: 프로젝트 설명

### 1. 주제 선정 의도
게시판 서비스라는 가장 기본적인 아이템을 통해, CRUD나 로그인 기능과 같이 실무에서 필수적으로 사용되는 기능들을 보다 쉽게 구현해보려 한다. 또한 다양하게 활용될 수 있는 게시판의 특성상 이후에 기능을 추가하기가 수월하다.

### 2. 얻고자 하는 바
실무에서 필수적으로 사용되는 기술들을 A부터 Z까지 혼자 직접 개발하여 봄으로써, 앞으로 다른 본격적인 프로젝트에 참여하거나 복잡한 기능을 구현해 볼 기반을 쌓고,  그 과정에서 이전에 머리로만 이해했던 지식들을 체화시킨다. 또한 웹 서비스 개발의 전체 사이클을 경험해봄으로써, 부족한 부분이나 공부가 더 필요한 부분을 파악한다.

### 3. 구체적인 목표
1. 도메인 설계 (회원과 게시글에 대한 도메인 개발)
2. 기능 명세서 작성 (회원과 게시글 도메인에 대한 각각의 기능 명세서 작성)
3. DB 설계 (회원 DB와 게시글 DB에 대한 E-R 다이어그램 및 릴레이션 스키마 작성)
4. 회원에 대한 기본적인 CRUD 기능 구현 (회원 등록, 로그인, 회원 업데이트, 회원 삭제)
5. 게시판에 대한 기본적인 CRUD 기능 구현 (게시글 등록, 게시글 리스트, 게시글 업데이트, 게시글 삭제)
6. 회원 로그인 기능을 세션 기능을 통해 구현
7. 페이지네이션 기능 (게시글 리스트에 대해 페이징 기능 구현)

### 4. 프로젝트 진행 기간
2024.08.01 ~ 2024.08.31

### 5. 적용해보자 하는 스프링 기술

- MyBatis를 통한 DB 접근 기술 -  SQL Mapper을 이용하여 개발하기 위해
- Session을 통한 로그인 기능 - 인증 기능 중 구현하기에 가장 간편하기 때문
- BasicErrorController를 통한 예외 처리 - RESTful API가 아닌 일반적인 웹 서버로 구현하기 때문
- SLF4J를 통한 Logging
- Bean Validation을 통한 유효성 검사
- MessageSource를 통한 message 기능
- 순수 자바 코드를 이용한 Pagination 기능

### 6. 기술 스택

- Back End
    - Java 17
    - Sprintboot
    - gradle
    - Thymeleaf
    - MyBatis
    - H2 Database - 관계형 DBMS 중에서 사용하기 간편해서 체택함
- Front End (이후 수정)
    - HTML
    - CSS
- Common
    - Git - VCS(버전 관리 시스템)
    - GitHub - Git 리포지토리 호스팅 서비스
    - Notion - 프로젝트 전반 관리

## 개발

### 1. 도메인 개발

#### Member (회원)

- id (Long) - DB에서 자동 생성
- name (String)
- loginId (String)
- password (String)

#### Post (게시물)

- id (Long) - DB에서 자동 생성
- title (String)
- content (String)
- ModifiedDate (LocalDateTime)
- memberId (Long)

### ERD 설계
![Board_Project](https://github.com/user-attachments/assets/7e096a02-5ebd-45b6-9c95-715909f304ef)

