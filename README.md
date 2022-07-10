# NestJS

NestJS 를 학습 하면서 필요한 내용들을 기록할 예정이다. 이번 학습을 통해 React, Nodejs, Express, MongoDB 를 사용하여 Sever/Client 프로그램을 개발할 예정이다.

## 기본구조 및 설치하기

Nestjs 는 node 를 기반으로 하는 모듈이기 때문에, npm 을 이용하여 -g 옵션과 함께 설치를 해야한다. 모듈이 설치되면 New 옵션을 이용하여 프로젝트를 생성할 수 있다.

```sh
# 모듈 설치
npm i -g @nestjs/cli
# 현재 경로에 프로젝트 생성
nest new .
```

Nestjs 는 TypeScript 기반으로 구성되어 있으며, 문법 체크(.eslintrc.js) 및 코딩 스타일(.prettierrc)과 관련하여 체크하는 옵션이 내장되어 있다.

프로젝트 구조는 엔트리 파일인 main.ts 을 시작으로 Root 모듈(AppModule) 필요한 하나 이상의 모듈을 등록한 다음 Controller, Service 를 처리하도록 되어 있다. Express 와 마찬가지로 route 를 입력받아(request) Controller 에 의해 Service 를 수행하고, 수행된 결과를 Controller 가 Client 에게 전달(response) 한다.

## 모듈/컨트롤러/서비스 생성하기

nest cli 문법을 이용하여 모듈에 필요한 항목들을 추가할 수 있다. 추가된 항목들은 module 에 등록되며 여러 모듈간에 injection 을 통해 종속성을 가질 수 도 있다. 대표적으로 Controller 에서 Service 를 사용하기 위해서는 생성자(constructor) 에서 Property 를 등록해 주면 된다.

- nest : nestjs cli 문법
- g : generate
- module/controller : module 또는 controller 생성
- folderName : folder 이름
- --no-spec : test 를 위한 코드를 생성 안함

```sh
# module 생성하기
nest g module folderName
# controller 생성하기
nest g controller folderName --no-spec
# service 생성하기
nest g service folderName --no-spec
```

## 파이프 생성 및 사용하기

파이프를 이용하면 Client 로 부터 전달 받은 데이터의 유효성 및 변환 작업을 할 수 있다. 이러한 작업을 수행하기 위해서는 npm 을 이용하여 모듈을 추가해야 한다.

```sh
npm i class-validator
npm i class-transformer
```
