# tips-&-tricks

## Resynch WSL with windows clock after laptop standby
```bash
sudo ntpdate pool.ntp.org 
```
or 
```bash
sudo hwclock -s
```
## Change log level at runtime with spring boot actuator
```bash
curl -i -X POST -H "Content-Type: application/json" -d '{"configuredLevel":"trace"}' http://localhost:8083/actuator/loggers/org.springframework.jms
```
## Enable remote debug with JVM and spring boot
```bash
java -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=8000 -jar myapp.jar
```
with maven
```bash
mvn spring-boot:run -Dspring-boot.run.jvmArguments="-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=8000"
```
more info [here](https://www.baeldung.com/spring-debugging)
