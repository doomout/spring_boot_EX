도서명 - 자바 웹 개발 워크북  
IDE - IntelliJ IDEA 2023.1 (Ultimate Edition) 라이센스 만료시 vsCode로 변경 예정   
자바 버전 - JDK 11, JAVA EE 8  
웹 서버 - 톰캣 9.0.73  
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