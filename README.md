# DockerStudy
## 서버 생성
1. npm init -y
2. package.json 자동 생선된다
   - 라이브러리에 무엇을 설치했는지 기록하는 용도의 파일(라이브러리 기록용 파일)
3. npm install express
  - 서버를 쉽게 만들어주는 라이브러리
4. node server.js
  - 서버 실행 
5. DockerFile 생성
  - dockerImage를 만들기 위한 용도

## Dockerfile 문법
1. FROM 이미지명
  - 이미지를 불러올 수 있다
2. RUN ~~~
  - 실행해주는 명령어 
      1. RUN npm install
      2. RUN ["npm", "install"] (일반적으로 사용한다.)
3. COPY 경로 경로
  - 하나 하나 라이브러리를 설치하기에는 버젼문제등이 생길 수 있기 때문에 packge.json를 이미지로 만들어 복사하는게 좋다.
4. WORKDIR 경로
  - 폴더 이동 명령어 
  - 없으면 생성한다.
5. CMD, ENTRYPOINT
  - 마지막 터미널 명령어를 적을때 사용한다.
6. EXPOSE 포트번호
  - 어떤 포트를 사용하는지를 적는 용도
  - 메모 용도 기능적으론 없다.

## 이미지 만들기 docker build
  1. 터미널을 연다
  2. docker build -t 이미지이름:태그 . 

## 터미널에서 이미지 실행 명렁어
  1. docker run 이미지명:태그명
  2. docker run -d(백그라운드에서 실행하는 명령어)
  3. docker run -p 내컴퓨터포트:컨테이너 포트

결론 : docker run -d -p 내컴퓨터포트:컨테이너포트 이미지명:태그명


## Tip
1. nodemon
  - 코드를 실시간 반영해주는 라이브러리 
  - npm install -g nodemon 설치
  - nodemon server.js 실행
2. pm2
  - 서버가 에러 때문에 죽었을때 알아서 실행되도록 해주는 라이브러리