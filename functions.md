##### Functions

#### Create a Function 

* user.js
```js
function User(name,email,password) {
  this.name = name;
  this.email = email;  
  this.password = password;
}
```

```js
const user = new User("Naresh","n@gmail.com", "pass123");
console.log(user);
```

##### Using Prototype

```js
User.prototype.role="USER";
```

