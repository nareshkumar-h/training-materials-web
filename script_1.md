## JavaScript Examples

##### Task 1: Get Text Box Value

```html
<input type="text" name="firstName" id="firstName" />
```

```js
const name = document.querySelector("#firstName").value;
console.log("Name:" + name );
```

#### Task 2: Form  + Submit Button 
* Create a function
* Call a function

```html
<form onsubmit="register()">
  <button type="submit" > Submit </button>
</form>
```

```js
function register(){
   event.preventDefault();
   alert("Register btn clicked");
}
```

#### Task 3: Button => onclick
```html
<button type="button" onclick="display()">Click </button>
```

```js
function display(){
  alert("Button clicked");
}
```

#### Task 4: Validation

```js
const name = "Naresh";
//const name = "";
//const name = null;

if(name == null || name.trim() == ""){
   console.log("Name cannot be empty");
}
```

#### Task 5: Append content to html

```html
<div id="message">
</div>
```

```js
document.querySelector("message").innerHTML = "Successfully Registered";
```

#### Task 6: Show/Hide a message
```html
<div id="spinner">
    Processing
</div>
```

```js
//document.querySelector("#spinner").style.display="none";
document.querySelector("#spinner").style.display="block";
```

#### Task 7: Arrays
```js
const departments = [ "CSE", "IT","EEE" ];
for(const dept of departments) {
  console.log(dept);
}
```

#### Task 8 : JSON
```js
const obj = { id: 1, name:"Naresh", department:"CSE" };
console.log("Name:" + obj.name ) ;
```

#### Task 9:  LocalStorage
```js
const name = "naresh";
localStorage.setItem("NAME", name );

const firstName = localStorage.getItem("NAME");
console.log("Name:" + firstName );

localStorage.removeItem("NAME");
localStorage.clear();
```
