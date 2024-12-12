# 1. session and cookie [link](https://www.geeksforgeeks.org/difference-between-session-and-cookies/)

## Session

- A session is like a temporary "conversation" between your browser and a website.
- It starts when you visit a website and ends when you close the browser or log out.
- It stores information about you (e.g., your login status or items in your shopping cart) on the server.
- Sessions are usually tracked using a session ID, which is sent to your browser and stored temporarily.

## 2. Cookie

- A cookie is a small piece of data stored directly on your browser by the website.
- It remembers information about you, like your preferences, login details, or activity.
- Cookies can persist even after you close your browser, depending on their expiration date.
- They help websites "remember" you between visits, like keeping you logged in or personalizing content.

# pass by value and pass by reference

## pass by value

```js
let a = 10;
let b = a;

a = 20;

console.log(a); // Outputs: 20
console.log(b); // Outputs: 10
```

## pass by reference

```js
let obj1 = { value: 10 };
let obj2 = obj1;

obj1.value = 20;

console.log(obj1.value); // Outputs: 20
console.log(obj2.value); // Outputs: 20
```