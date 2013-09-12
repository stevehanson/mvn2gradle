# Maven to Gradle

Very basic web page that converts Maven dependencies to Gradle. Currently only parses groupId, artifactId and version. Scope is ignored. If using a variable for version, it will keep that, but you will still need to define the variable in your build.gradle file

Example:

This -

	<dependency>
		<groupId>org.springframework</groupId>
		<artifactId>spring-websocket</artifactId>
		<version>${org.springframework-version}</version>
	</dependency>

	<dependency>
		<groupId>javax.servlet</groupId>
		<artifactId>javax.servlet-api</artifactId>
		<version>3.1.0</version>
		<scope>anything-this-field-is-completely-ignored-for-now</scope>
	</dependency>

Becomes this -

	compile "org.springframework:spring-websocket:$org.springframework-version"
	compile "javax.servlet:javax.servlet-api:3.1.0"

See it in action [here](http://mvn2gradle.codetutr.com)