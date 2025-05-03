# 🎯 JavaScript Event Handling & Interactive Elements Assignment

Welcome to the **ultimate JavaScript playground**! 🎉 This assignment is where we turn boring web pages into dynamic, responsive, *alive* experiences. Get ready to master **event handling**, build **interactive components**, and validate forms like a pro! 💪

## 📁 Assignment Structure

```
📂 js-event-assignment/
├── index.html         # Your playground – where it all comes together
├── style.css          # Keep it cute (optional but encouraged)
└── script.js          # The JavaScript wizardry happens here
```

---

## 🧪 What to Build

Here’s what your interactive bundle of joy should include:

### 1. Event Handling 🎈  
- Button click ✅  
- Hover effects ✅  
- Keypress detection ✅  
- Bonus: A secret action for a *double-click* or *long press* 🤫

### 2. Interactive Elements 🎮  
- A button that changes text or color  
- An image gallery or slideshow  
- Tabs or accordion-style content  
- Bonus: Add some animation using JS or CSS ✨

### 3. Form Validation 📋✅  
- Required field checks  
- Email format validation  
- Password rules (e.g., min 8 characters)  
- Bonus: Real-time feedback while typing

---

## 🧙‍♂️ Pro Tips

- Keep your code clean and commented – your future self will thank you!
- Think about **user experience** – what makes your site more *fun* to use?
- Don’t be afraid to **Google and experiment** – that’s how real developers roll!

---

## 🎉 Now Go Make It Fun!

Remember – this isn't just code. It's your **first step toward creating magical user experiences**. So play around, break stuff (then fix it), and most of all, have FUN! 😄

Happy Coding! 💻✨  

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>JavaScript Concepts with Animation</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      background: #f4f4f4;
    }
    .form-group {
      margin-bottom: 15px;
    }
    input {
      padding: 8px;
      width: 100%;
      box-sizing: border-box;
      transition: box-shadow 0.3s ease;
    }
    input:focus {
      box-shadow: 0 0 8px rgba(0, 123, 255, 0.6);
      outline: none;
    }
    .error {
      color: red;
      font-size: 0.9em;
    }
    #colorButton {
      padding: 10px 20px;
      background-color: steelblue;
      color: white;
      border: none;
      cursor: pointer;
      border-radius: 5px;
      transition: background-color 0.5s ease;
    }
    #successMessage {
      margin-top: 20px;
      padding: 15px;
      background-color: #d4edda;
      border: 1px solid #c3e6cb;
      color: #155724;
      border-radius: 5px;
      opacity: 0;
      transform: translateY(-10px);
      transition: opacity 0.5s ease, transform 0.5s ease;
    }
    #successMessage.show {
      opacity: 1;
      transform: translateY(0);
    }
  </style>
</head>
<body>
  <h2>Interactive Form</h2>
  <form id="userForm">
    <div class="form-group">
      <label for="name">Name:</label><br/>
      <input type="text" id="name" name="name" />
      <div class="error" id="nameError"></div>
    </div>
    <div class="form-group">
      <label for="email">Email:</label><br/>
      <input type="text" id="email" name="email" />
      <div class="error" id="emailError"></div>
    </div>
    <button type="submit">Submit</button>
  </form>

  <div id="successMessage">Form submitted successfully!</div>

  <h3>Interactive Button</h3>
  <button id="colorButton">Click Me to Change Color</button>

  <script>
    // Form validation
    document.getElementById("userForm").addEventListener("submit", function(event) {
      event.preventDefault();

      let name = document.getElementById("name").value.trim();
      let email = document.getElementById("email").value.trim();
      let nameError = document.getElementById("nameError");
      let emailError = document.getElementById("emailError");
      let successMessage = document.getElementById("successMessage");

      let isValid = true;

      nameError.textContent = "";
      emailError.textContent = "";
      successMessage.classList.remove("show");

      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

      if (name === "") {
        nameError.textContent = "Name is required.";
        isValid = false;
      }
      if (email === "") {
        emailError.textContent = "Email is required.";
        isValid = false;
      } else if (!emailRegex.test(email)) {
        emailError.textContent = "Invalid email format.";
        isValid = false;
      }

      if (isValid) {
        successMessage.classList.add("show");
      }
    });

    // Interactive button
    document.getElementById("colorButton").addEventListener("click", function() {
      this.style.backgroundColor = this.style.backgroundColor === "tomato" ? "steelblue" : "tomato";
    });
  </script>
</body>
</html>
