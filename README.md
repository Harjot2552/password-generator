# Random Password Generator 🔐

This is a simple, client-side random password generator built with HTML, CSS, and JavaScript. It allows users to generate secure random passwords that include uppercase letters, lowercase letters, numbers, and special symbols. The generated password can also be copied to the clipboard for easy use. 

## Features ✨

- Generate a random password of 12 characters.
- Password includes a mix of uppercase, lowercase, numbers, and symbols.
- Copy the generated password to the clipboard with a click.

## Technologies Used ⚙️

- HTML
- CSS
- JavaScript

## How to Use 🧑‍💻

1. Open the `index.html` file in your browser.
2. Click the "Generate Password" button to create a new random password.
3. The generated password will appear in the input box.
4. Click the copy icon next to the password to copy it to your clipboard.

## Project Structure 📂

/Random-Password-Generator │ ├── index.html # Main HTML file ├── style.css # Styling for the password generator ├── images/ # Folder containing images (e.g., copy icon, generate icon) │ ├── copy.png │ └── generate.png └── README.md # Project documentation

csharp
Copy
Edit

## How It Works 🔍

### 1. Password Generation Code

```javascript
const upperCase = "ABCDEFGHIJKLMNOPQRSTUVXYZ";  // Uppercase letters
const lowerCase = "abcdefghijklmnopqrstuvxyz";  // Lowercase letters
const number = "0123456789";  // Numbers
const symbol = "!@#$%^&*()+-?[]{}";  // Special symbols
const allChars = upperCase + lowerCase + number + symbol;  // All characters combined
Here, we define the characters available for password generation:

upperCase contains uppercase letters (A-Z).
lowerCase contains lowercase letters (a-z).
number contains digits (0-9).
symbol contains special characters.
We then combine them into allChars, which will be used to select random characters when creating the password.

2. Password Creation Logic 🛠️
javascript
Copy
Edit
function createPassword() {
    let password = "";
    password += upperCase[Math.floor(Math.random() * upperCase.length)];  // Random uppercase letter
    password += lowerCase[Math.floor(Math.random() * lowerCase.length)];  // Random lowercase letter
    password += number[Math.floor(Math.random() * number.length)];  // Random number
    password += symbol[Math.floor(Math.random() * symbol.length)];  // Random special symbol
In the createPassword function, we:

Add one random character from each category (uppercase, lowercase, number, symbol) to ensure variety in the password.
The Math.random() function generates a random index, and Math.floor() is used to round it down to an integer.
3. Fill Remaining Password Length 🔢
javascript
Copy
Edit
    while (length > password.length) {
        password += allChars[Math.floor(Math.random() * allChars.length)]  // Random character from allChars
    }
    passwordBox.value = password;  // Display the generated password in the input field
}
We then fill the remaining length of the password (up to 12 characters) by randomly selecting characters from the allChars pool.
Finally, the password is displayed in the input box for the user.
4. Copying the Password 📋
javascript
Copy
Edit
function copyPassword() {
    passwordBox.select();  // Select the text in the password field
    document.execCommand("copy");  // Copy the selected text to the clipboard
}
The copyPassword function selects the generated password and copies it to the clipboard.
When the user clicks the copy icon, the password is automatically copied for easy pasting.
