# 34 — Classes and OOP

## What Is This Lesson About?

ES6 classes provide a cleaner syntax for creating objects with shared behaviour. They are syntactic sugar over JavaScript's prototype-based inheritance.

---

## Class Basics

```javascript
class Animal {
  constructor(name, sound) {
    this.name = name;
    this.sound = sound;
  }

  speak() {
    return `${this.name} says ${this.sound}`;
  }

  toString() {
    return `Animal(${this.name})`;
  }
}

const dog = new Animal('Rex', 'Woof');
dog.speak(); // 'Rex says Woof'
```

---

## Inheritance

```javascript
class Dog extends Animal {
  constructor(name, breed) {
    super(name, 'Woof'); // call parent constructor
    this.breed = breed;
  }

  fetch(item) {
    return `${this.name} fetches the ${item}!`;
  }
}

const rex = new Dog('Rex', 'Labrador');
rex.speak();       // 'Rex says Woof' (inherited)
rex.fetch('ball'); // 'Rex fetches the ball!'
rex instanceof Dog;    // true
rex instanceof Animal; // true
```

---

## Static Methods and Properties

```javascript
class MathUtils {
  static PI = 3.14159;

  static add(a, b) { return a + b; }
  static multiply(a, b) { return a * b; }
}

MathUtils.add(2, 3);  // 5 — called on class, not instance
MathUtils.PI;         // 3.14159
```

---

## Private Fields (ES2022)

```javascript
class BankAccount {
  #balance = 0; // private field

  deposit(amount) { this.#balance += amount; }
  getBalance() { return this.#balance; }
}

const account = new BankAccount();
account.deposit(100);
account.getBalance(); // 100
account.#balance;     // SyntaxError — private!
```

---

## Getters and Setters

```javascript
class Temperature {
  #celsius;

  constructor(celsius) { this.#celsius = celsius; }

  get fahrenheit() { return this.#celsius * 9/5 + 32; }
  set fahrenheit(f) { this.#celsius = (f - 32) * 5/9; }
}

const temp = new Temperature(100);
temp.fahrenheit; // 212
temp.fahrenheit = 32;
```

---

## Common Mistakes

- Forgetting `new` when creating instances
- Forgetting `super()` in a subclass constructor
- Using arrow functions as methods (they don't have their own `this`)
- Overusing classes — functions and objects are often simpler
