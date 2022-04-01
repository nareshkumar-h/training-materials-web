# Training Notes (HTML/JS/CSS)

# HTML5

#### HTML Structure
* DOCTYPE, html, head,  meta, title, body

#### HTML Layout

* **A semantic element clearly describes its meaning to both the browser and the developer.**
* Examples of non-semantic elements: div and span - **Tells nothing about its content**.
* Examples of semantic elements: form, table, and article - **Clearly defines its content**.

* header, nav, aside, main, section, article,footer

![image](https://user-images.githubusercontent.com/2763774/161204275-8bbb836c-8518-41c3-9a6f-f44afbb49ff6.png)


#### Forms
* Forms - method (GET/POST), action
* Input Types - text, number,email, date, password, checkbox, radio, select, option, textarea, url, textarea
* Buttons - submit, reset, button
* Attributes : required,placeholder, min,max,id, class, style

#### Table
* table, thead, tbody, tfoot, tr, th, td

#### Link
* a
* target = blank/self/parent

#### Images
* img 

#### Media 
* audio
* video

#### IFrame
* iframe

#### List ( Unordered List / Ordered List  )
* ol, ul, li
  
#### JavaScript ( internal/external )
* script 

#### Stylesheets ( inline / internal/ external )
* link
* style 


# JavaScript

#### Variables/ DataTypes/ Scopes
* Datatypes - string, number, date, boolean, null, undefined
* var vs let vs const

#### Scope 
* Global Scope
* Function Scope
* Block Scope

#### Constructor
* constructor
* this

#### String
* String - toUpperCase, toLowerCase, trim, length, substr, split

#### Arrays
* Arrays => push,pop,splice,length etc. 
* for of loop
* Map
* Set

#### Objects/JSON
* Object 
* Access using dot notation

#### Functions
* Define Function / Call Function / Return Value
* Assigning Function to a variable
* Self invoking function ( IIFE )  - **An Immediately-invoked Function Expression (IIFE ) is a way to execute functions immediately, as soon as they are created. The self-invoking function only runs once.**
* Callback Functions - **A callback is a function passed as an argument to another function.**
* Closure
* Promise
* async / await

#### Ajax
* XMLHttpRequest
* fetch
* axios

#### Events
* Events - onclick, onchange, onsubmit etc..
* EvenListener - addEventListener, removeEventListener
* Event Bubbling / Event Capturing - https://javascript.info/bubbling-and-capturing
  * **Event Bubbling** - When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors. 
* Event Stop Propogation ( event.stopImmediatePropagation() )

#### DOM 
* document.querySelector
* document.querySelectorAll
* document.getElementById

# CSS ( Cascading Style Sheets )

#### Syntax
* selector { property: value; }

#### Different Selectors
* Element Selector ( e.g: body )
* Id Selector ( e.g: #email ) 
* Class Selector (e.g: .spinner )
* Universal Selector ( e.g: * )

#### Internal/External/Inline
* style => internal css 
* link => external css ( e.g: bootstrap )
* inline css

##### Style Display
* block
* inline
* none

