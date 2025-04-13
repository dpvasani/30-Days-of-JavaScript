# 📅 [Day 4] The `this` Keyword in JavaScript

## 🧠 Understanding the `this` Keyword in JavaScript

> The value of `this` is **dynamic**—it changes based on where and how it's used.  
Think of it like different roles a person plays in different situations. 🎭

---

## 💞 GF/BF Analogy

In a conversation:
- Your **girlfriend (GF)** may refer to you as her **boyfriend (BF)**.
- You refer to **yourself** as her BF.
- Similarly, in **JavaScript**, `this` refers to **who’s talking** and **in what context**.

Just like relationships, the context decides the label. ❤️

---

## 1️⃣ `this` Refers to the Calling Object → **GF is Present**

When you call a method on an object, `this` refers to **the object** the method is called on.

### 💡 Analogy:
You're out on a date with your GF. She says:
> “Let’s take a selfie!”  
She takes the photo and says:
> “This is **my** selfie!”  
👧📸

```js
const girlfriend = {
  name: "Emily",
  takeSelfie: function () {
    console.log("This is " + this.name + "'s selfie");
  }
};

girlfriend.takeSelfie(); // Output: This is Emily's selfie
```

---

## 2️⃣ `this` in the Global Context → **Your Crush** 😳

When you're not inside any object or method, `this` refers to the **global object** (like `window` in browsers). It’s like thinking about your crush when your GF isn’t around. 😅

```js
console.log(this); // In browsers: refers to window object
```

---

## 3️⃣ `this` in Regular Functions → **Talking to Your Crush Again**

When `this` is used inside a **regular function**, it again refers to the **global object** (if not in strict mode).

### 💡 Analogy:
You try calling your GF but she's busy, so you talk to your crush instead. 😬

```js
function greet() {
  console.log(this); // Refers to the global object
}

greet(); // Output: window (in browser)
```

---

## 🔍 Real-World Use Cases

### 🌀 Global Context

```js
let visits = 0;

function trackVisits() {
  visits++;
  console.log(this); // window
  console.log(`You have visited this page ${visits} times.`);
}

trackVisits();
```

---

### 🔁 Inside Regular Functions

```js
function showThis() {
  console.log(this); // global object (non-strict mode)
}

showThis();
```

---

### 🧍 Inside Object Methods

```js
const user = {
  name: 'John',
  greet: function () {
    console.log(this.name + ' says hello!');
  }
};

user.greet(); // Output: John says hello!
```

---

### 🧱 Inside Constructor Functions

```js
function Person(name, age) {
  this.name = name;
  this.age = age;
  this.greet = function () {
    console.log(`${this.name} is ${this.age} years old.`);
  };
}

const person1 = new Person('Alice', 25);
const person2 = new Person('Bob', 30);

person1.greet(); // Alice is 25 years old
person2.greet(); // Bob is 30 years old
```

---

### 🏹 Arrow Functions (Lexical `this`)

Arrow functions **don’t have their own `this`**. They inherit `this` from the **parent scope**.

```js
const user = {
  name: 'Sarah',
  greet: function () {
    setTimeout(() => {
      console.log(this.name + ' says hello after 2 seconds!');
    }, 2000);
  }
};

user.greet(); // Sarah says hello after 2 seconds!
```

---

### 🖱️ Event Handlers: `this` → DOM Element

```js
document.getElementById('myButton').addEventListener('click', function () {
  console.log(this); // Refers to the button (DOM element)
});
```

---

## ✋ Explicit Binding: `.bind()`, `.call()`, `.apply()`

### 🔗 `bind()` — Permanently binds `this` (creates new function)

```js
const person = {
  name: 'Alice',
  greet: function () {
    console.log('Hello, ' + this.name);
  }
};

const greetPerson = person.greet.bind(person);
greetPerson(); // Hello, Alice
```

---

### ☎️ `call()` — Invokes with custom `this` (args as normal)

```js
const person = {
  name: 'Charlie',
  greet: function (age) {
    console.log(`${this.name} is ${age} years old.`);
  }
};

const anotherPerson = { name: 'Dave' };
person.greet.call(anotherPerson, 25); // Dave is 25 years old
```

---

### 📞 `apply()` — Similar to `call()`, but args passed as array

```js
const person = {
  name: 'Eve',
  greet: function (greeting, punctuation) {
    console.log(`${greeting}, ${this.name}${punctuation}`);
  }
};

const anotherPerson = { name: 'Frank' };
person.greet.apply(anotherPerson, ['Hello', '!']); // Hello, Frank!
```

---

## 🚗 Class-Based `this`

```js
class Car {
  constructor(brand, model) {
    this.brand = brand;
    this.model = model;
  }

  displayInfo() {
    console.log(`This car is a ${this.brand} ${this.model}.`);
  }
}

const myCar = new Car('Tesla', 'Model 3');
myCar.displayInfo(); // This car is a Tesla Model 3.
```

---

## 🧾 Key Takeaways

✅ `this` is dynamic—its value depends on **how** and **where** it is used.  
✅ Use `.call()` or `.apply()` for **immediate function calls** with custom `this`.  
✅ Use `.bind()` to create **a new function** with permanently bound `this`.  
✅ Arrow functions inherit `this` from their **lexical scope**.  
✅ DOM event handlers set `this` to the **element** that triggered the event.

---
## 👨‍💻 Author  

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**    

### 🔗 Connect with me! 🌍  
🌐 **Portfolio:** [dpvasani56.vercel.app](https://dpvasani56.vercel.app/)  
🐙 **GitHub:** [github.com/dpvasani](https://github.com/dpvasani)  
💼 **LinkedIn:** [linkedin.com/in/dpvasani56](https://www.linkedin.com/in/dpvasani56/)  
🌳 **Linktree:** [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
🎓 **Credly:** [credly.com/users/dpvasani57](https://www.credly.com/users/dpvasani57/)  
🐦 **Twitter:** [x.com/vasanidarshan56](https://x.com/vasanidarshan56)  
📢 **Topmate:** [topmate.io/dpvasani56](https://topmate.io/dpvasani56)  

---
