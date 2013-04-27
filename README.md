http://www.codejava.net/frameworks/spring/upload-files-with-spring-mvc-eclipse-based-tutorial
This tutorial is about how to implement file upload functionality with Spring MVC framework. To handle file uploads, Spring provides a MultipartResolver bean which is responsible for resolving multipart request. This resolver is working with two file upload libraries:

 

Apache Commons File Upload: The bean class is org.springframework.web.multipart.commons.CommonsMultipartResolver
COS (com.oreilly.servlet): The bean class is org.springframework.web.multipart.cos.CosMultipartResolver
 

We need to declare the MultipartResolver bean in Spring’s context file as follows:

 

For CommonsMultipartResolver:

 
 
<bean id="multipartResolver"
    class="org.springframework.web.multipart.commons.CommonsMultipartResolver">
    <!-- max file size in bytes -->
    <property name="maxUploadSize" value="2000000" />
    <!-- other properties... -->
</bean>
 

 And for CosMultipartResolver:
 
<bean id="multipartResolver"
    class="org.springframework.web.multipart.cos.CosMultipartResolver">
    <!-- max file size in bytes -->
    <property name="maxUploadSize" value="2000000" />
    <!-- other properties... -->
</bean>
Also we need to add to classpath jar files of the file upload library employed:

For Apache Commons File Upload: commons-fileupload-VERSION.jar and commons-io-VERSION.jar (Commons File Upload depends on Commons IO).
For COS: cos.jar
As Apache Commons File Upload is popular and preferred over COS, this tutorial will use it. We will build a Spring MVC application which has an upload form looks like in the following screenshot:




This tutorial requires the following pieces of software installed on your computer (click on a link to download the corresponding software):

JDK 7
Spring framework 3.2 GA
Tomcat 7.0
Apache Commons File Upload
Apache Commons IO
Apache Commons Logging (required by Spring)
Eclipse IDE for Java EE Developers (Eclipse Juno 4.2)
 

 Attachments:
FileUploadSpringMVC.war  [Deployable WAR file]  3540 Kb
http://www.codejava.net/attachments/article/205/FileUploadSpringMVC.war
FileUploadSpringMVC.zip	[Eclipse project]	3542 Kb
http://www.codejava.net/attachments/article/205/FileUploadSpringMVC.zip

 
