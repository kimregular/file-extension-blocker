# File Extension Blocker

파일 확장자에 따라 특정 형식의 파일을 첨부하거나 전송하지 못하도록 제한

<!-- TOC -->
* [File Extension Blocker](#file-extension-blocker)
  * [사용 방법](#사용-방법)
  * [실행 방법](#실행-방법)
    * [Docker Compose 실행](#docker-compose-실행)
    * [Docker Compose 중지](#docker-compose-중지)
  * [화면](#화면)
    * [1. 홈 화면](#1-홈-화면)
    * [2. 설정 화면](#2-설정-화면)
  * [프로젝트 구조](#프로젝트-구조)
    * [1. file tree](#1-file-tree)
    * [structure](#structure)
<!-- TOC -->

## 사용 방법

1. 파일 확장자 제한 설정: 설정 파일에서 원하는 파일 확장자를 추가하거나 제거하여 제한을 설정합니다.
2. 파일 첨부/전송 제한: 파일을 첨부하거나 전송할 때 파일 확장자를 확인하여 제한된 파일 형식인지 확인합니다.

## 실행 방법

### Docker Compose 실행

```shell
docker compose -f compose-prod.yml up
```

### Docker Compose 중지

```shell
docker compose -f compose-prod.yml down
```

## 화면

### 1. 홈 화면

![홈 화면](./images/home.png)

### 2. 설정 화면

![설정 화면](./images/main.png)

## 프로젝트 구조

### 1. file tree
```text
.
├── Dockerfile
├── build.gradle
├── compose-infra.yml
├── compose-prod.yml
├── gradlew
├── settings.gradle
└── src/
    ├── main/
    │   ├── java/com/regular/fileextensionblocker/
    │   │   ├── aop/                 # AOP 관련 (로깅 등)
    │   │   ├── controller/          # API 및 페이지 컨트롤러
    │   │   ├── domain/              # 엔티티 및 공통 타입
    │   │   ├── dto/                 # 데이터 전송 객체
    │   │   ├── exception/           # 커스텀 예외 및 예외 핸들러
    │   │   ├── filter/              # 서블릿 필터 (MDC 등)
    │   │   ├── repository/          # 데이터 액세스 계층
    │   │   └── service/             # 비즈니스 로직 계층
    │   ├── resources/
    │   │   ├── application.yml      # 기본 설정
    │   │   └── logback-spring.xml   # 로그 설정
    │   └── webapp/WEB-INF/views/    # JSP 뷰 파일
    └── test/
        └── java/com/regular/fileextensionblocker/ # 테스트 코드
```
### structure

![structure](./images/structure.png)

## 프로젝트 특징