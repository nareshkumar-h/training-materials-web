## JavaScript Object Oriented Programming - Inheritance

* Using **```__proto__```** we can able to extend inheritance.

##### Parent - Animal
```js
let animal = {
  eats: true,
  walk() {
    console.log("Animal walk");
  }
};
```

#### Test - Animal Object
```js
console.log(animal.eats ); //true
animal.walk(); //prints "Animal walk" 
```

##### Child - rabbit

```js
let rabbit = {
  jumps: true,
  __proto__: animal	// sets animal to be a prototype of rabbit.
};
```

#### Test - Rabbit Object

```js
console.log(rabbit.jumps ); //true
```

* **Inherited Behaviours**

```js
console.log(rabbit.eats); // true
rabbit.walk(); //prints "Animal walk" 
```

