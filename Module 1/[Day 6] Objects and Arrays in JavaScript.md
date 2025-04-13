
# 📘 [Day 6] Objects and Arrays in JavaScript

---

## 🧱 Objects in JavaScript

### 🔍 What is an Object?
An object is a collection of related data and functionality, like a profile that holds all relevant details together.

#### 💑 Husband/Wife Analogy:
Think of describing your partner:
- **Properties**: Name, age, hobbies.
- **Methods**: Cooking, driving, shopping (actions they perform).

```js
const partner = {
  name: "Alex",
  age: 28,
  hobbies: ["cooking", "reading", "traveling"],
  cook: function () {
    console.log(`${this.name} is cooking dinner!`);
  }
};

// Access properties
console.log(partner.name);         // Alex
console.log(partner.hobbies[1]);   // reading

// Call method
partner.cook();                    // Alex is cooking dinner!
```

---

### 🧭 Accessing Object Properties

#### Dot Notation:
```js
objectName.propertyName
```
- Preferred when property names are known.

#### Bracket Notation:
```js
objectName["propertyName"]
```
- Useful for dynamic keys or when property names have special characters.

#### 🧑‍🤝‍🧑 Friend Analogy:
- Dot notation = calling a friend by **nickname**.
- Bracket notation = calling them by their **full name**.

```js
const friend = { nickname: "Buddy", fullName: "John Doe" };
console.log(friend.nickname);       // Buddy
console.log(friend["fullName"]);    // John Doe
```

---

### ✏️ Adding, Updating, and Deleting Properties

```js
const crush = { name: "Taylor", likes: "movies" };

// Add
crush.phoneNumber = "123-456-7890";

// Update
crush.likes = "music";

// Delete
delete crush.phoneNumber;

console.log(crush);  // { name: "Taylor", likes: "music" }
```

---

## 📦 Arrays in JavaScript

### 🔍 What is an Array?
An array is a collection of values stored in a single variable.

#### 🧑‍🤝‍🧑 Friends Analogy:
A list of your friends, each with an index number for quick reference.

```js
const friends = ["John", "Mike", "Sara"];
console.log(friends[0]);        // John
console.log(friends.length);    // 3
```

---

### 🔧 Common Array Methods

#### Push & Pop — Add/Remove at End
```js
friends.push("Emma"); 
console.log(friends);  // ["John", "Mike", "Sara", "Emma"]

friends.pop();         
console.log(friends);  // ["John", "Mike", "Sara"]
```

#### Unshift & Shift — Add/Remove at Start
```js
friends.unshift("Liam"); 
console.log(friends);  // ["Liam", "John", "Mike", "Sara"]

friends.shift();       
console.log(friends);  // ["John", "Mike", "Sara"]
```

#### Slice & Splice — Select/Modify
```js
const partyFriends = friends.slice(1, 3); 
console.log(partyFriends);  // ["Mike", "Sara"]

friends.splice(1, 1, "Nick"); 
console.log(friends);       // ["John", "Nick", "Sara"]
```

---

## 🌐 Real-World Web Development Examples

### 👤 User Profile as an Object
```js
const userProfile = {
  id: 101,
  username: "john_doe",
  email: "john@example.com",
  isPremium: true,
  preferences: {
    theme: "dark",
    notifications: true,
  },
  login: function () {
    console.log(`${this.username} has logged in.`);
  }
};

// Access nested property and method
console.log(userProfile.username);             // john_doe
console.log(userProfile.preferences.theme);    // dark
userProfile.login();                           // john_doe has logged in.
```

---

### ✅ Todo List as an Array of Objects
```js
const todos = [
  { id: 1, task: "Learn JavaScript", completed: false },
  { id: 2, task: "Build a project", completed: false },
  { id: 3, task: "Deploy to the web", completed: true },
];

// Filter incomplete tasks
const pendingTasks = todos.filter(todo => !todo.completed);
console.log(pendingTasks);
// Output:
// [
//   { id: 1, task: "Learn JavaScript", completed: false },
//   { id: 2, task: "Build a project", completed: false }
// ]
```

---

## 🧠 Key Takeaways

### 🧱 Objects
1. **Data Representation**: Ideal for modeling users, settings, or product info using key-value pairs.
2. **Nested Structures**: Can hold other objects/arrays.
3. **Dynamic Behavior**: Easily update/add/delete properties.
4. **Encapsulated Behavior**: Use methods to bundle behavior with data.
5. **Use Cases**:
   - API responses
   - Database records
   - App configuration

### 📦 Arrays
1. **Data Collection**: Best for ordered lists like users or tasks.
2. **Iteration Tools**: Use `map`, `filter`, `forEach`, `reduce`.
3. **Flexible Size**: Add/remove items easily.
4. **Efficient Manipulation**: Methods like `push`, `splice`, etc.
5. **Use Cases**:
   - Rendering UI lists
   - Dropdown menus
   - Parsing API data

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
