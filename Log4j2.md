# Log4j2 with Spring Boot

<i>Examples of Log4j2 configuration with Spring Boot 2.4</i>

To run Log4j2 with spring boot:

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
			<exclusions>
				<exclusion>
					<groupId>org.springframework.boot</groupId>
					<artifactId>spring-boot-starter-logging</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-log4j2</artifactId>
		</dependency>

To change versions of log4j or slf4j (if used):

      <slf4j.version>1.7.25</slf4j.version>
	  <log4j2.version>2.11.0</log4j2.version>

If spring boot application is running on application server as web application, logging libraries might be provided by the server (i.e. Tomcat). Possibly libraries from spring boot should be excluded then:
  
          <dependency>
			<groupId>org.slf4j</groupId>
			<artifactId>slf4j-api</artifactId>
			<scope>provided</scope>
		</dependency>
		<dependency>
			<groupId>org.apache.logging.log4j</groupId>
			<artifactId>log4j-slf4j-impl</artifactId>
			<scope>provided</scope>
		</dependency>
		<dependency>
			<groupId>org.apache.logging.log4j</groupId>
			<artifactId>log4j-api</artifactId>
			<scope>provided</scope>
		</dependency>
		<dependency>
			<groupId>org.apache.logging.log4j</groupId>
			<artifactId>log4j-core</artifactId>
			<scope>provided</scope>
		</dependency>

To debug log4j2:
	
	java ... -Dlog4j2.debug=true
