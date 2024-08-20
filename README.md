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
> > 5. 
 


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
> docker run --name [컨테이너명] -d [이미지명] : 이미지를 바탕으로 컨테이너 생성(백그라운드에서)
> docker ps -a : 모든 컨테이너 목록 확인 ( 정지된 컨테이너 포함 )
> > 정지는 삭제와 같지않으며 삭제된 컨테이너는 해당 명령어에도 표시되지 않음
> docker run --name [컨테이너명] -d -p 80:80 [이미지명] : 이미지를 바탕으로 컨테이너 생성(백그라운드에서, 해당 포트번호로)
> 
