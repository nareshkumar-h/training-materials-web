## Servlets 4.0


##### Create Dynamic Web Project

* File => New => Other => Dynamic Web Project => choose web.xml


##### Create Maven Web Project

* File => New => Other => Maven Project => webapp

##### Servlet Jars :
* servlet-api.jar

##### Create Servlet
* RegisterServlet
```java
@WebServlet("/RegisterServlet")
public class RegisterServlet extends HttpServlet {

}
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


