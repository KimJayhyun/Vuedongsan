# vuedongsan

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

# 개발환경 세팅
## 1. node js 최신 버전 설치
## 2. vscode 설치
- 아래 Extension도 설치
    ```
    vetur
    html css support
    vue 3 snippets
    ```
## 3. Vue CLI 설치
- npm install -g @vue/cli

- npm 설치 안될 시
    1. yarn 1.22 설치
        - Windows
        
            구글에서 설치 후 윈도우 재시작
        - Mac

            ``` npm install -g yarn ```
    2. 아래 명령어 실행        
        ``` yarn global add @vue/cli ```

## 4. Vue Project 생성
- 터미널에 아래 명령어 실행

    ``` vue create {Project Name} ```


## 참고
    https://codingapple.com/unit/vue-3-installation-with-vue-cli/?id=139

# 설명
## Node Js 설치 이유
- Nodejs를 설치하면 npm이 설치됨
- npm은 웹 개발 라이브러리 설치 도우미
- @vue/cli를 간편하게 설치하기 위함
    - vue/cli를 이용해서 Project를 편하게 생성할 수 있음

## Project Diretory 구조
- App.vue가 메인 Work Space
- App.vue를 Html로 컴파일하여 main.js가 index.html에 적용
    - index.html이 메인 페이지
        
- node_modules
    - 프로젝트에 쓰는 라이브러리들
- scr
    - 소스코드
- public
    - html, 기타 파일 보관
- package.json
    - 라이브러리 버전, 프로젝트 설정 기록


# npm 원리
### 1. npm install 2 가지 유형
1. 패키지 명을 명시해서 특정 패키지를 설치
2. 패키지 명을 명시하지 않고 디렉토리의 ```package.json```을 참고하여 의존성 설치

### 2. 특정 패키지 설치
패키지를 설치할 때 크게 세 가지 옵션으로 구분됨
1. ```-P``` ```-save-prod```
    - 프로젝트의 ```node_modules```에 추가
    - ```package.json```의 ```dependencies``` 에 추가
1. ```-D``` ```-save-dev```
    - 프로젝트의 ```node_modules```에 추가
    - ```package.json```의 ```devDependencies``` 에 추가
1. ```-g```
    - **시스템**의 ```node_modules``` 폴더에 추가


# VueJS의 로컬서버가 움직이는 원리
 - package-lock.json 참고
 
### 1.vue cli 라이브러리가 webpack-dev-server라는 라이브러리를 의존하고있다
    
- ```"node_modules/@vue/cli-service"```에서 ```"dependencies"```를 확인하면 ```"webpack-dev-server"```를 사용
 
### 2.webpack-dev-server는 모듈 번들링후 배포 내용을 메모리에 저장 후 즉시 로컬서버에 반영하는 라이브러리다

### 3.webpack-dev-server의 라이브러리로 내부는 express라는 nodejs서버 라이브러리를 의존하고있다
 - ```"node_modules/webpack-dev-server"```에서 ```"dependencies"```를 확인하면 ```"express"```를 사용 중

### 4.즉 npm run serve해서 실행되는 로컬 서버  = nodejs의 express앱을 베이스로 실행되는 서버가 된다

### 5.실제로 webpack-dev-server는 express모듈에 의존하고있다