# springbootlearning---04---EurekaDiscoveryServer
When you run this project, you will get JAXB errors. To fix it, you should javax dependecies to pom.xml

			<dependency>
				<groupId>javax.xml.bind</groupId>
				<artifactId>jaxb-api</artifactId>
				<version>2.3.0</version>
			</dependency>
			<dependency>
				<groupId>com.sun.xml.bind</groupId>
				<artifactId>jaxb-impl</artifactId>
				<version>2.3.0</version>
			</dependency>
			<dependency>
				<groupId>org.glassfish.jaxb</groupId>
				<artifactId>jaxb-runtime</artifactId>
				<version>2.3.0</version>
			</dependency>
			<dependency>
				<groupId>javax.activation</groupId>
				<artifactId>activation</artifactId>
				<version>1.1.1</version>
			</dependency>

After adding the dependencies, you will still get a new error - Connection refused: connect stacktrace=com.sun.jersey.api.client.ClientHandlerException: java.net.ConnectException: Connection refused

To fix it, please add below lines to application.properties
server.port=8761
eureka.client.register-with-eureka=false
eureka.client.fetch-registry=false