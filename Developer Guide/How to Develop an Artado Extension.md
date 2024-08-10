# How to Develop an Artado Extension

This guide will help you create extensions for [Artado Search](https://www.artadosearch.com). Extensions allow you to add custom functionality, enhance the user experience, or integrate third-party services directly into Artado Search.

## Getting Started

To develop an extension for Artado Search, you’ll need to have a basic understanding of HTML, CSS, and JavaScript.
JavaScript is a powerful language that runs in the browser, allowing you to manipulate the content of web pages, interact with APIs, and more.
To learn about basics of Javascript you can check out this documentation.

### Tools You'll Need

- **Text Editor or IDE (Optional)**: Use any code editor, such as [Visual Studio Code](https://code.visualstudio.com/), [Sublime Text](https://www.sublimetext.com/), or [Atom](https://atom.io/).
- **Web Browser**: For testing and debugging your extension.

## Basics

### Creating Your First Extension

1. **Create a New JavaScript File**:
   - Start by creating a new `.js` file in your text editor.
   - This file will contain the logic for your extension.

2. **Basic Structure**:
   - Here’s a simple template to get you started:
     ```javascript
     if (window.location.pathname === "/search") { // Runs the code if the user is in the 
     const urlParams = new URLSearchParams(window.location.search);
     const search = urlParams.get('i').replace("+", " ").trim()
        .replace(/[!"#\$%&'\(\)\*\+,-\.\/:;<=>\?@\[\\\]\^_`{\|}~]/g, "").replace(/ +/g, " "); // Gets the searched query

     const searches = [
        "whats my ip",
        "what is my ip",
        "what my ip",
        "my ip",
     ];

     if (searches.includes(search)) { //Checks if the query is about IP
        fetch('https://api.ipify.org?format=json')
            .then(response => response.json())
            .then(data => {
                var element = document.createElement("div"); //Creates an element in the search page
                element.className = "card";
                element.style = "border: 1px solid #bdbdbd; text-transform: none";
                element.innerHTML = `<p>Your IP address is: <code>${data.ip}</code></p>`;

                document.getElementById("web_results").insertBefore(element, document.getElementById("web_results").firstChild);
            });
      }
     }
     ```

3. **Load the Extension**:
   - To test your extension, load it into Artado Search. You can do this manually by pasting your code into the browser’s console or by creating a browser extension that injects your script into Artado Search.

4. **Testing**:
   - Open Artado Search in your browser.
   - Use the browser’s developer tools (`F12` or `Ctrl+Shift+I`) to inspect the page, run your extension, and debug any issues.

### Modifying the UI

You can also modify the Artado Search interface by injecting custom HTML or altering existing elements:

```javascript
(function() {
    // Add a custom button to the search bar
    let button = document.createElement("button");
    button.innerText = "Custom Action";
    button.onclick = function() {
        alert("Button clicked!");
    };
    document.querySelector("#searchbar").appendChild(button);
})();
```

3. **Upload Your Extension**: You can share your extension with the Artado community by uploading it to [Artado Devs](https://devs.artado.xyz/).

## Example Extensions

Here are a few example extensions developed by the Artado community:

- **Quick Translate**: Automatically translates search results into the user’s preferred language.
- **Dark Mode Toggle**: Adds a button to toggle between light and dark modes.
- **Search History Tracker**: Logs and displays the user's search history within Artado.

## Learn More

To build more advanced extensions, you'll need to deepen your understanding of JavaScript and web APIs:

- [JavaScript Basics](https://www.w3schools.com/js/default.asp) - Learn the fundamentals of JavaScript.
- [JavaScript.info](https://javascript.info/) - Detailed tutorials and guides.
- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript) - Comprehensive JavaScript reference.

## Upload Your Extensions

When your extension is ready, share it with the world on [Artado Devs](https://devs.artado.xyz/):

1. **Create an Account**: Sign up or log in to Artado Devs.
2. **Upload Your Extension**: Provide a description, upload your files, and share your work with the Artado community.

---

This guide should provide you with everything you need to start developing and sharing extensions for Artado Search. Enjoy building and enhancing the Artado experience!
