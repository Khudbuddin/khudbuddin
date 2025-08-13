git# JavaScript Concepts Guide

## 1️⃣ Authentication vs Authorisation

**Authentication** – Proving who you are  
- Confirms **your identity**.  
- Examples: Passwords, OTP, Fingerprint, Face Scan.

**Authorisation** – Checking what you can do  
- Decides **what permissions** you have after authentication.  
- Example: Admins can delete users; normal users can’t.

**Memory Trick:**  
> Authentication = "Who are you?"  
> Authorisation = "What can you do?"  

---

## 2️⃣ Fetch Method in Promise

**What is `fetch`?**
- A built-in JavaScript function for making HTTP requests.
- Returns a **Promise**.

**Example:**
```javascript
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then(response => response.json())
  .then(data => console.log("Data received:", data))
  .catch(error => console.error("Error:", error));
```

**Async/Await Example:**
```javascript
async function getPost() {
  try {
    let response = await fetch("https://jsonplaceholder.typicode.com/posts/1");
    let data = await response.json();
    console.log("Data received:", data);
  } catch (error) {
    console.error("Error:", error);
  }
}

getPost();
```

---

## 3️⃣ Fetch Explained Simply (8th STD level)

Imagine ordering a pizza:  
1. You order (`fetch()` call).  
2. Wait while it’s being made (Promise is pending).  
3. Pizza delivered (Promise resolved).  
4. Open box and eat (`.json()` to get data).  

**Example:**
```javascript
fetch("https://jsonplaceholder.typicode.com/users/1")
  .then(response => response.json())
  .then(data => console.log("User data:", data))
  .catch(error => console.log("Something went wrong:", error));
```

---

## 4️⃣ setTimeout & setInterval

**setTimeout** – Runs code **once** after a delay.  
```javascript
setTimeout(() => {
  console.log("Hello after 3 seconds!");
}, 3000);
```

**setInterval** – Runs code repeatedly at intervals.  
```javascript
let count = 1;
let timer = setInterval(() => {
  console.log("Runs every 2 seconds. Count:", count);
  count++;
  if (count > 5) clearInterval(timer);
}, 2000);
```

| Feature | setTimeout | setInterval |
|---------|------------|-------------|
| Runs how many times? | Once | Repeatedly |
| Stop method | clearTimeout() | clearInterval() |

---

## 5️⃣ Promises

A Promise represents a value that might be available now, later, or never.

**States:**
- Pending
- Fulfilled (resolved)
- Rejected

**Example:**
```javascript
let myPromise = new Promise((resolve, reject) => {
  let pizzaReady = true;
  if (pizzaReady) resolve("Pizza is here!");
  else reject("Sorry, shop closed.");
});

myPromise
  .then(message => console.log("Success:", message))
  .catch(error => console.log("Error:", error));
```

**Async/Await:**
```javascript
async function getPizza() {
  try {
    let message = await myPromise;
    console.log(message);
  } catch (error) {
    console.log(error);
  }
}

getPizza();
```

---

## 6️⃣ try and Is It Essential for async?

`try` is used for error handling.

**Structure:**
```javascript
try {
  // Code that may cause error
} catch (error) {
  // Runs if error happens
} finally {
  // Optional, runs always
}
```

**In async functions:**  
Not required, but useful to prevent crashes.

```javascript
async function getData() {
  try {
    let response = await fetch("https://wrongurl.com");
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.log("Something went wrong:", error);
  }
}

getData();
```

---

## 7️⃣ Web API in JavaScript

Web APIs are **browser-provided features** that JavaScript can use.

**Examples:**
- DOM API – change HTML & CSS
- Fetch API – get data from internet
- Geolocation API – get user’s location
- LocalStorage API – save data in browser

**Example DOM API:**
```javascript
document.getElementById("myButton").addEventListener("click", () => {
  alert("Button clicked!");
});
```

**Example Fetch API:**
```javascript
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));
```

---

## 8️⃣ Axios

**What is Axios?**
- JavaScript library for HTTP requests.
- Works in browsers & Node.js.

**Why Axios over fetch?**
| Feature | Axios | Fetch |
|---------|-------|-------|
| Auto JSON parsing | ✅ | ❌ |
| Better error handling | ✅ | ❌ |
| Cancel requests | ✅ | ⚠️ |
| Timeout support | ✅ | ❌ |

**Install:**
```bash
npm install axios
```
Or in browser:
```html
<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
```

**GET Example:**
```javascript
axios.get("https://jsonplaceholder.typicode.com/posts/1")
  .then(res => console.log("Data:", res.data))
  .catch(err => console.error("Error:", err));
```

**POST Example:**
```javascript
axios.post("https://jsonplaceholder.typicode.com/posts", {
  title: "Hello",
  body: "This is my first Axios post",
  userId: 1
})
.then(res => console.log("Post created:", res.data))
.catch(err => console.error("Error:", err));
```

**Async/Await Example:**
```javascript
async function getData() {
  try {
    let res = await axios.get("https://jsonplaceholder.typicode.com/posts/1");
    console.log(res.data);
  } catch (err) {
    console.error(err);
  }
}

getData();
```

---
