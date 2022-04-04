## DOM 

* When a web page is loaded, the browser creates a **Document Object Model** of the page.

The HTML DOM model is constructed as a tree of Objects:

![image](https://user-images.githubusercontent.com/2763774/161524535-9c6b40e2-9e34-4c77-82f6-1b1e827e8f2f.png)

#### DOM - HTML

The HTML DOM is a standard object model and programming interface for HTML. It defines:

* The HTML elements as **objects**
* The **properties** of all HTML elements
* The **methods** to access all HTML elements
* The **events** for all HTML elements

#### DOM - JS

With the object model, JavaScript gets all the power it needs to create dynamic HTML:

* JavaScript can change all the HTML elements in the page
* JavaScript can change all the HTML attributes in the page
* JavaScript can change all the CSS styles in the page
* JavaScript can remove existing HTML elements and attributes
* JavaScript can add new HTML elements and attributes
* JavaScript can react to all existing HTML events in the page
* JavaScript can create new HTML events in the page

#### Task 1: Change the content of an element
* The **innerHTML** property is useful for getting or replacing the content of HTML elements.
```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = "Hello World!";
</script>

```

#### Finding Element

| Method  | Description  | 
|---|---|
| document.getElementById(id)	  | **Find an element by element id** | 
| document.getElementsByTagName(name)  |  **Find elements by tag name** | 
|  document.getElementsByClassName(name) |  **Find elements by class name** | 

#### Changing HTML Elements

| Property  | Description  | 
|---|---|
| element.innerHTML =  new html content	  | **Change the inner HTML of an element**  | 
| element.attribute = new value	  | **Change the attribute value of an HTML element** | 
| element.style.property = new style	  | **Change the style of an HTML element**  | 


| Method  | Description  | 
|---|---|
| element.setAttribute(attribute, value)	  | **Change the attribute value of an HTML element**  | 

##### Adding and Deleting Elements

| Method  | Description  | 
|---|---|
| document.createElement(element)	  | **Create an HTML element**  | 
| document.removeChild(element)	  | **Remove an HTML element**  | 
| document.appendChild(element)	  | **Add an HTML element**  | 
| document.replaceChild(new, old)	  | **Replace an HTML element**  | 
| document.write(text)	  | **Write into the HTML output stream**  | 


##### Task 1 : Create a div tag dynamically using JS 

* Using HTML
```html
<body>
   <div>Success</div>
</body>
```

* Using JS
```js
const div = document.createElement("div");
div.textContent = "Success";
document.body.appendChild(div);
```

## Event Listeners

* The addEventListener() method allows you to add event listeners on any HTML DOM object.

##### Task 1.1: Add an event listener that fires when a user resizes the window:

```js
window.addEventListener("resize", function(){
  alert("Resize event called');
});
```

##### Task 1.2: Add an event listener for a button element
* html
```html
<button type="button" id="btn" > Click Me </button>
```
* js 

```js
const btn = document.querySelector("#btn");
document.addEventListener('click', function(){
   alert("Button clicked");
});
```
