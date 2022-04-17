## Servlets 4.0


##### Create Dynamic Web Project

* File => New => Other => Dynamic Web Project => choose web.xml

![image](https://user-images.githubusercontent.com/2763774/163707867-d7f4219e-2837-4ea1-8aa9-86d1442b3734.png)
![image](https://user-images.githubusercontent.com/2763774/163707873-8c06fa01-0f65-4995-9133-758be432e157.png)


##### Create Maven Web Project

* File => New => Other => Maven Project => webapp

##### Servlet Jars :
* servlet-api.jar ( https://mvnrepository.com/artifact/javax.servlet/javax.servlet-api/4.0.1 )
* pom.xml
```xml
<dependency>
    <groupId>javax.servlet</groupId>
    <artifactId>javax.servlet-api</artifactId>
    <version>4.0.1</version>
    <scope>provided</scope>
</dependency>
```
#### Client/Server
![image](https://user-images.githubusercontent.com/2763774/163707483-adb0dfb9-f059-4bfa-a8cb-b4546c1d1953.png)

## Servlet

![image](https://user-images.githubusercontent.com/2763774/163707383-1de3573c-8260-44fe-8e7d-d46a2b99575f.png)


#### Advantages of Servlet

* The web container creates threads for handling the multiple requests to the Servlet. Threads have many benefits over the Processes such as they share a common memory area, lightweight, cost of communication between the threads are low. 

  * **Better performance**: because it creates a thread for each request, not process.
  * **Portability**: because it uses Java language.
  * **Robust**: JVM manages Servlets, so we don't need to worry about the memory leak, garbage collection, etc.
  * **Secure**: because it uses java language.

##### Create Servlet
* RegisterServlet
```java
@WebServlet("/RegisterServlet")
public class RegisterServlet extends HttpServlet {

}
```
* Using XML configuration (web.xml)

```xml
<servlet>
    <servlet-name>RegisterServlet</servlet-name>
    <servlet-class>com.naresh.RegisterServlet</servlet-class>
  </servlet>
  <servlet-mapping>
    <servlet-name>RegisterServlet</servlet-name>
    <url-pattern>/RegisterServlet</url-pattern>
  </servlet-mapping>
```

#### Load Servlet on Startup
* The load-on-startup element of web-app loads the servlet at the time of deployment or server start if value is positive. 
* It is also known as **pre initialization of servlet**.

```xml
 <servlet>  
   <servlet-name>RegisterServlet</servlet-name>  
   <servlet-class>com.naresh.RegisterServlet</servlet-class>  
   <load-on-startup>0</load-on-startup>  
  </servlet>  
  
  <servlet>  
   <servlet-name>LoginServlet</servlet-name>  
   <servlet-class>com.naresh.RegisterServlet</servlet-class>  
   <load-on-startup>1</load-on-startup>  
  </servlet>  
```


##### Servlet Methods

* doGet Method
```java
protected void doGet(HttpServletRequest request, HttpServletResponse response) {
}
```

* doPost Method
```java
protected void doPost(HttpServletRequest request, HttpServletResponse response) {
}
```

##### Servlet Lifecycle Method
* https://www.javatpoint.com/life-cycle-of-a-servlet
* The web container maintains the life cycle of a servlet instance. Let's see the life cycle of the servlet:

   * **Servlet class is loaded** 
      *  The classloader is responsible to load the servlet class. The servlet class is loaded when the first request for the servlet is received by the web container.
   * **Servlet instance is created** 
      *  The web container creates the instance of a servlet after loading the servlet class. The servlet instance is created **only once** in the servlet life cycle.
   * **init method is invoked** 
      * The web container calls the init method **only once** after creating the servlet instance. The init method is used to initialize the servlet
   * **service method is invoked** 
      * The web container calls the service method **each time** when request for the servlet is received.
   * **destroy method is invoked**
      * The web container calls the destroy method before removing the servlet instance from the service. It gives the servlet an opportunity to clean up any resource for example memory, thread etc.
```java
public void init(){
}

public void service(){
}

public void destroy(){
}
```


