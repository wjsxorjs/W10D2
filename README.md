# W10D2
> Day 2 of Docker
## 패키징 파일
> 서버에 배포하기 위한 파일(JAR, WAR) <br>
> > JAR : 
> > > 1. 내장 TOMCAT을 그대로 사용 <br>
> > > 2. 위치에 상관없이 사용 가능 <br>
> >
> > WAR : 
> > > 1. 외부 TOMCAT을 사용 <br>
> > > 2. 지정한 외부 TOMCAT의 webapp에 위치해야 사용 가능. <br>

### VSCODE에서 MAVEN Project 패키지 가져오기
> JAR
> > 1. Maven 태그에서 해당하는 프로젝트 선택 후 우클릭
> > 2. clean -> install -> package
> > 3. JAR 파일 경로 확인 후 해당 경로에서 JAR 확인
>
> WAR
> > 1. pom.xml에서 <parent> 내부에 `<packaging>war</packaging>` 추가
> > 2. dependcy : `spring-boot-starter-tomcat` 추가
> > 3. 메인Application.java에서 `SpringBootServletInitializer` 상속
> > 4. configure() 함수 재정의
> > 5. Maven 태그에서 해당하는 프로젝트 선택 후 우클릭
> > 2. clean -> install -> package
> > 3. WAR 파일 경로 확인 후 해당 경로에서 WAR 확인
> > 6. `/var/lib/tomcat[ver]/webapps`에 이동
> > 7. `service tomcat[ver] (re)start`
 


### JAR 파일 실행
> 1. JAR 파일을 실행하고자 하는 경로에 위치시킴
> 2. service tomcat stop : 이미 실행 중인 tomcat 중지
> 3. (nohup) java -jar *.jar : jar파일 실행
>
> *** JAR는 JSP를 지원해주지않는다
> 
### WAR 파일 실행
> 1. JAR 파일을 실행하고자 하는 경로에 위치시킴
> 2. service tomcat stop : 이미 실행 중인 tomcat 중지
> 3. (nohup) java -jar *.jar : jar파일 실행

# Docker
> docker pull [이미지명] ; docker hub에서 해당 이미지를 다운로드 <hr>
> docker run --name [컨테이너명] -d [이미지명] : 이미지를 바탕으로 컨테이너 생성(백그라운드에서) <br>
> docker ps -a : 모든 컨테이너 목록 확인 ( 정지된 컨테이너 포함 ) <br>
> > 정지는 삭제와 같지않으며 삭제된 컨테이너는 해당 명령어에도 표시되지 않음 <br>
> 
> docker run --name [컨테이너명] -d -p [연결할 포트]:[연결시킬 포트] [이미지명] : <br>이미지를 바탕으로 컨테이너 생성(백그라운드에서, 해당 포트번호로)<br>
> docker attach [컨테이너 id] : 해당 컨테이너에 대한 프로세스의 표준 입출력(에러 포함)을 현재 터미널에 연결<br>
> docker exec [option] [컨테이너 id] [명령어] : 실행중인 컨테이너에 새로운 명령을 실행시킴<br>(-dit: 백그라운드에서 상호작용을 계속하며 터미널에 표시한다.) `exit`로 탈출<br>

## Docker 초기화 하는 법
> docker stop $(docker ps -q) : 모든 컨테이너 정지<br>
> -> docker rm $(docker ps -a -q) : 모든 컨테이너 삭제<br>
> -> docker rmi -f $(docker images -q) : 모든 이미지 삭제
