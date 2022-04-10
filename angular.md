# Angular Directives

#### What are directives ?

* Directives change the behavior of HTML DOM.
* Angular syntax inside the html

```html
<div [hidden]="isLoggedIn"> ...</div>
```

#### What are three types of directives ?

* Components
* Attribute Directive
* Structural Directive

#### What is Component Directive ?
* Directives with template.

#### What is Structural Directives ?
* Change the DOM layout by adding and removing elements.

```html
<ul>
  <li *ngFor="let dept of departments"> {{dept}} </li> 
```
Note: If the departments array contains 3 departments ( CSE,IT, MECH), then 3 ```<li>``` tags are added.
  
#### What is Attribute Directives ?
* Change the appearance and behaviour of HTML elements, component or 
* Does not change the structure.

```html
<div [hidden]="isLoggedIn"> ...</div>
```

#### List inbuilt directives?

* NgClass—adds and removes a set of CSS classes.
* NgStyle—adds and removes a set of HTML styles.
* NgModel—adds two-way data binding to an HTML form element.

#### NgClass
* To add or remove a single class, use class binding rather than NgClass.

```html
<div [ngClass]="currentClasses">Hello</div>
```

#### NgStyle
* Use NgStyle to set multiple inline styles simultaneously, based on the state of the component.

```html
<div [ngStyle]="currentStyles">
  This div is initially italic, normal weight, and extra large (24px).
</div>
```

##### NgModel
* Use the NgModel directive to display a data property and update that property when the user makes changes.

```html
<input [(ngModel)]="email" type="email" id="email" name="email" required placeholder="Enter email" />
```

##### Built in Structural Directives

* Structural directives are responsible for HTML layout. 
* They shape or reshape the DOM's structure, typically by adding, removing, and manipulating the host elements to which they are attached.


* **NgIf**—conditionally creates or disposes of subviews from the template.
* **NgFor**—repeat a node for each item in a list.
* **NgSwitch** —a set of directives that switch among alternative views.

#### NgIf

* Add or remove an element by applying an NgIf directive to a host element.
* When NgIf is false, Angular removes an element and its descendants from the DOM. 
* Angular then disposes of their components, which frees up memory and resources.

```html
<div *ngIf="isLoggedIn"> Content </div>
```

##### NgFor

```html
<div *ngFor="let item of items; let i=index">
  {{i + 1}} - {{item.name}}
</div>
```

##### Create New Directive

```
ng generate directive highlight
```

```
import { Directive, ElementRef } from '@angular/core';

@Directive({
  selector: '[appHighlight]'
})
export class HighlightDirective {
    constructor(private el: ElementRef) {
       this.el.nativeElement.style.backgroundColor = 'yellow';
    }
}
```

```html
<p appHighlight>Highlight me!</p>
```
