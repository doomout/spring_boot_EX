도서명 - 자바 웹 개발 워크북  
IDE - IntelliJ IDEA 2023.1 (Ultimate Edition) 라이센스 만료시 vsCode로 변경 예정   
자바 버전 - JDK 11, JAVA EE 8  
웹 서버 - 자체 내장 WAS   
DB - MariaDB 10.5(x64)  
SQL 툴 - HeidiSQL 11.3.0.6295  
스프링 프레임워크 버전 - 5.3.19  
부트스트랩 버전 - 5.1.3  

1. application.properties 설정
```
//DB 관련
spring.datasource.driver-class-name=org.mariadb.jdbc.Driver
spring.datasource.url=jdbc:mariadb://localhost:3306/webdb
spring.datasource.username=doom
spring.datasource.password=ska123
server.port=8081

//Log4j2 관련
logging.level.org.springframework=info
logging.level.org.zerock=debug

//JPA 관련
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.format_sql=true
spring.jpa.show-sql=true
```
2. build.gradle 설정
```
dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-data-jpa'
	implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'
	implementation 'org.springframework.boot:spring-boot-starter-web'
	compileOnly 'org.projectlombok:lombok'
	developmentOnly 'org.springframework.boot:spring-boot-devtools'
	runtimeOnly 'org.mariadb.jdbc:mariadb-java-client'
	annotationProcessor 'org.projectlombok:lombok'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
	testCompileOnly 'org.projectlombok:lombok'
	testAnnotationProcessor 'org.projectlombok:lombok'
}
```
3. JSON 데이터 란?
  * JavaScript Object Notation 의 약자로 구조를 가진 데이터를 자바스크립트의 객체 표시법으로 표현한 순수 문자열 
  * 순수 문자열이기에 데이터 교환시에 프로그램 언어에 독립적이다.
  * 스프링은 jackson-databind 라는 별도의 라이브러리를 추가 후 개발해야 한다.
  * 스프링 부트는 web 항목 추가할 때 자동으로 포함되어 별도의 설정 없이 바로 개발 가능하다.
  * 화면은 Thymeleaf를 이용하고 데이터는 json으로 전송하는 방식으로 개발한다.