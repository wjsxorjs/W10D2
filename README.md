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
> > ### VSCODE에서 MAVEN Project 패키지 가져오기
> > > 1. Maven 태그에서 해당하는 프로젝트 선택 후 우클릭
> > > 2. clean -> install -> package
> > > 3. JAR 파일 경로 확인 후 해당 경로에서 JAR 확인
> > >
> > ### JAR 파일 실행
> > > 1. JAR 파일을 실행하고자 하는 경로에 위치시킴
> > > 2. service tomcat stop : 이미 실행 중인 tomcat 중지
> > > 3. (nohup) java -jar *.jar : jar파일 실행
