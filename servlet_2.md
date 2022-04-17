# Servlet - Class/Methods


#### HttpServletRequest

* **Task 1: Get Request Parameter Value**

```java
String name = request.getParameter("name");
```

* **Task 2: Store Data in request Scope**
```java
String email = "n@gmail.com";
request.setAttribute("LOGGED_IN_USER", email);
```


* **Task 3: Create Session and Store data in session scope**
```java
String email = "n@gmail.com";
HttpSession session = request.getSession();
session.setAttribute("LOGGED_IN_USER", email);
```

* **Task 4: RequestDispatcher - forward/include**
```java
String email = "n@gmail.com";
request.setAttribute("LOGGED_IN_USER", email);

RequestDispatcher dispatcher = request.getRequestDispatcher("next.jsp");

dispatcher.forward(request, response);
//dispatcher.include(request, response);
```



#### HttpServletResponse

* **PrintWriter** 
```java
PrintWriter out = response.getWriter();
```

* **Set Content Type**
```java
response.setContentType("text/html");
```

```java
response.setContentType("application/json");
response.setCharacterEncoding("UTF-8");
```        

* **Write content as Response**
```java
out.write("success");
out.flush();
out.close();
```

* **Write json content as Response**
```java
User user = new User("Naresh", "n@gmail.com");
Gson gson = new Gson();
String userJson = gson.toJson(user);
```
```java
out.write(userJson);
out.flush();
out.close();
```

* **Redirect to another page**
```java
response.sendRedirect("next.jsp");
```


#####  Session Methods

* **Create New Session**
```
HttpSession session = request.getSession(); (or)
HttpSession session = request.getSession(true);
```

* **Get Existing Session**
```
HttpSession session = request.getSession(false);
if(session==null){
   System.out.println("No existing session");
}
```

* **Add Data in Session**

```java
String email = "naresh@gmail.com";
session.setAttribute("LOGGED_IN_USER", email );
```


* **Get Data from Session**

```java
String email = (String)session.getAttribute("LOGGED_IN_USER");
```



* **Remove Data from Session **

```java
session.removeAttribute("LOGGED_IN_USER");
```


* **Remove All Data from Session (e.g:Logout) **

```java
session.invalidate();
```

* **Create Session Timeout**
  * Two ways to set session timeout
  * **Approach #1: XML Configuration (web.xml)**
```xml
 <session-config>
    <session-timeout>5</session-timeout>
  </session-config>
```
* **Approach #2: Java** 
```java
session.setMaxInactiveInterval(300); // session timeout in seconds ( 300 seconds = 5 mins)
```
