Two ways to display the SQL requests used by JPA.

compile & execute :<br/>
mvn spring-boot:run<br/>
<br/>
compile into fat jar then execute :<br/>
mvn clean package<br/>
java -jar target/displayUnderlyingSQLRequest-0.0.1-SNAPSHOT.jar<br/>
<br/>

During the first execution, the console shows : <br/>
Hibernate:<br/>
&nbsp;&nbsp;select<br/>
&nbsp;&nbsp;&nbsp;&nbsp;customer0_.id as id1_0_,<br/>
&nbsp;&nbsp;&nbsp;&nbsp;customer0_.first_name as first_na2_0_,<br/>
&nbsp;&nbsp;&nbsp;&nbsp;customer0_.last_name as last_nam3_0_<br/>
&nbsp;&nbsp;from<br/>
&nbsp;&nbsp;&nbsp;&nbsp;customer customer0_<br/>
&nbsp;&nbsp;where<br/>
&nbsp;&nbsp;&nbsp;&nbsp;customer0_.last_name=?<br/>

--application.properties<br/>
 #first way to display SQL request<br/>
 #logging.level.org.hibernate.SQL=DEBUG<br/>
 #logging.level.org.hibernate.type.descriptor.sql.BasicBinder=TRACE<br/>
<br/>
 #second way to display SQL request (with nicer indentation)<br/>
spring.jpa.properties.hibernate.show_sql=true<br/>
spring.jpa.properties.hibernate.format_sql=true<br/>
<br/>