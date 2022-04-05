# CSS ( Cascading Style Sheets ) 

* Latest Version: **CSS3**
* **Separation of content from presentation** 
* CSS provides a way to present the same content in multiple presentation formats in mobile or desktop or laptop.
* CSS, built effectively can be used to change the look and feel. 
* To make a global change, simply change the style, and all elements in all the web pages will be updated automatically.


#### Different ways to include CSS in a webpage ( External / Internal / Inline ) ?

* Three different ways to include css .

#### External CSS
```html
<link rel="stylesheet" type="text/css" href="styles.css" />
```

#### Internal CSS 
```js
<style>
p {
  background-color: yellow;
}

</style>
```

#### Inline CSS
```html
<p style="background-color:yellow">
```

##### Selectors

* A CSS **selector** is the part of a CSS ruleset that actually **selects the content you want to style**.

```html
<p> Welcome </p>
```

```html
<style>
p {
  background-color: red;
}
</style>
```

Note: **p** is the selector 

#### Different Types of Selector

* Universal Selector
* Element Type Selector
* Id Selector
* Class Selector

#### Universal Selector

* Universal Selector: The universal selector works like a wildcard character, **selecting all elements on a page**. 
* In the given example, the provided styles will get applied to all the elements on the page.
```js
* {
  font-size:20px;
}
```

#### Element Type Selector
* This selector matches **one or more HTML elements of the same name*.
```html
<p> News </p>
<p> Headlines </p>
```

```css
p {
  background-color: yellow;
}
```

#### ID Selector:

* This selector matches **any HTML element that has an ID attribute with the same value** as that of the selector. 

```css
#news {
  background-color: yellow;
}
```

```html
<p id="news"> News </p>
<p id="headlines"> Headlines </p>
```

#### Class Selector

* The class selector also matches **all elements on the page that have their class attribute** set to the same value as the class.

```css
.page-title {
   background-color: yellow;
}
```

```html 
<h1 class="page-title"> Course Details </h1>

<h1 class="page-title"> Latest Movies </h1>
```


##### What is Cascading ?

* **Cascading** refers to the process of going through the style declarations and defining weight or importance to the styling rules that help the browser to select what rules have to be applied in times of conflict. 
* The conflict here refers to multiple rules that are applicable to a particular HTML element. 
* In such cases, we need to let the browser know what style needs to be applied to the element. 
* This is done by cascading down the list of style declarations elements.

* styles.css
```
p{
    color:white;
}
```
* index.html ( which includes style.css)
```
p{
    color:black;
}
```

* We have a conflict in color property here for the paragraph elements. 
* Here, the browser just cascades down to identify what is the most recent and most specific style and applies that. 
* Since we have the **color:black;** as the most specific declaration, the color black is applied to the paragraph elements.

```
p{
    color:white !important;
}
```
* **!important** ensures that the property has the **maximum weight in presence of other conflicting properties**.


#### Specificity

* **A process of determining which CSS rule will be applied to an element.**
* It actually determines which rules will take **precedence**. 
* Inline style usually wins then ID then the class value (or pseudo-class or attribute selector), the universal selector (*) has no specificity. 
* ID selectors have a higher specificity than attribute selectors
```
