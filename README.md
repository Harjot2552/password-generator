# 🔒 Random Password Generator

A simple random password generator built using HTML, CSS, and JavaScript. It generates a secure, random password with a mix of uppercase, lowercase, numbers, and symbols. The generated password can be easily copied to the clipboard. 🧑‍💻✨

## Features

- 🔑 Generates a random 12-character password with a mix of:
  - 🅰️ Uppercase letters
  - 🔡 Lowercase letters
  - 🔢 Numbers
  - ✨ Symbols
- 🖱️ Simple and user-friendly interface
- 📋 Copy the generated password to clipboard with a single click

## Technologies Used

- 🌐 HTML
- 🎨 CSS
- 🧑‍💻 JavaScript

## How to Use

1. Open the `index.html` file in your browser. 🌍
2. Click the "Generate Password" button to create a random password. 🎰
3. The password will be displayed in the input field. 👀
4. Click the copy icon to copy the password to your clipboard. 📑➡️📋

## Installation

1. 🚧 Clone the repository or download the files.
2. 🌐 Open the `index.html` file in any modern browser to use the password generator.

## Code Overview

### HTML

The `index.html` contains a simple structure with an input field to display the generated password and a button to trigger the password creation process. There is also an image icon for copying the password to the clipboard.

### JavaScript

The JavaScript generates the password by selecting random characters from predefined strings for uppercase letters, lowercase letters, numbers, and symbols. The `createPassword()` function generates the password and assigns it to the input field. The `copyPassword()` function allows the user to copy the password to the clipboard.

```javascript
function createPassword() {
    let password = "";
    password += upperCase[Math.floor(Math.random() * upperCase.length)];
    password += lowerCase[Math.floor(Math.random() * lowerCase.length)];
    password += number[Math.floor(Math.random() * number.length)];
    password += symbol[Math.floor(Math.random() * symbol.length)];

    while (length > password.length) {
        password += allChars[Math.floor(Math.random() * allChars.length)];
    }
    passwordBox.value = password;
}

function copyPassword() {
    passwordBox.select();
    document.execCommand("copy");
}
