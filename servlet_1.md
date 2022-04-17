## Servlets 4.0


##### Create Dynamic Web Project

* File => New => Other => Dynamic Web Project => choose web.xml

|  |  |
---|--|
|![image](https://user-images.githubusercontent.com/2763774/163707867-d7f4219e-2837-4ea1-8aa9-86d1442b3734.png) |![image](https://user-images.githubusercontent.com/2763774/163707873-8c06fa01-0f65-4995-9133-758be432e157.png) |


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


#### Components of Servlet

![image](https://user-images.githubusercontent.com/2763774/163710556-9e674c08-1114-4570-93e9-00c0268bfd23.png)

* **Client**:
    * The web browser acts as a Client. Client or user connected with a web browser. The client is responsible for sending requests or HttpRequest to the web server and processing the Web server’s responses. 
        * 
* **Web Server**
    * Web server controls how web user access hosted files, and it's responsible for processing user request and responses. 
    * Here server is software it understands URLs and HTTP protocol. 
    * Whenever a browser needs to host a file on the webserver, process client request using an HTTP request; if it finds the requested file sends it back to the browser through HTTP Response. 
    * There are two types of web servers **Static** and **Dynamic** webservers. 
    * In a **static web server**, it sends the file as it is, but in a **dynamic web server**, the server-hosted file is updated before it is sent to the browser.

* **Web Container**
    * A web container is a component in the webserver it interacts with Java servlets. 
    * A web container is responsible for managing the lifecycle of servlets, and it also performs the URL mapping task. 
    * Web container handles the requests of servlets, JSP and other files at the server-side. 
    * The important tasks performed by servlets are loading and unloading servlets, creating and managing requests and response objects, and performing servlet management’s overall task.  

#### Servlet Flow ( How servlet request has been processed ) :
* The client sends a request.
* Web Server accepts the request and forwards it to the web container.
* Web container searches web.xml file for request URL pattern and gets the address of the servlet.
* If the servlet is not yet instantiated, it will be instantiated and initialized by calling the init() method.
* The container calls public service() by passing ServletRequest and ServletResponse objects.
* Public service() method typecast ServletRequest and ServletResponse object to HttpServletRequest and HttpServletResponse objects respectively.
* Public service() method calls protected service().
* Protected service() method checks the client request & corresponding do___() method is called.
* The request is handled by sending the result generated by do___() to the client.


#### Session Management ( 4 techniques)

* Cookies
* Hidden form fields
* URL Rewriting
* HttpSession API
