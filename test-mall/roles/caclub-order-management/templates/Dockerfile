FROM anapsix/alpine-java:8_server-jre_unlimited
VOLUME ["/tmp","/logs/dev-stable-caclub/{{git_project_name}}"]
ADD *.jar myapp.jar
COPY logback-spring.xml /logback-spring.xml
ENV JAVA_OPTS="-Xms300m -Xmx300m -Djava.security.egd=file:/dev/./urandom -Dspring.profiles.active=dev-stable -Dspring.cloud.config.uri={{config_host}} -Dspring.application.name=caclub-{{git_project_name}} -Dspring.cloud.config.username={{config_username}} -Dspring.cloud.config.password={{config_password}}"
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -jar myapp.jar" ]
EXPOSE {{web_port}} {{dubbo_port}}