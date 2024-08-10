# How to Develop an Artado Extension

Artado Extensions allow you to add custom functionality to [Artado Search](https://www.artadosearch.com) using JavaScript. This guide will walk you through the basics of JavaScript and provide a step-by-step process for developing your own extensions.

## Getting Started

To create an extension for Artado Search, you’ll need to have a basic understanding of JavaScript. JavaScript is a powerful language that runs in the browser, allowing you to manipulate the content of web pages, interact with APIs, and more.

### Basic JavaScript Concepts

Before diving into extension development, let's cover some fundamental JavaScript concepts:

1. **Variables**: Used to store data.
   ```javascript
   const name = "Artado";
   let searchQuery = "JavaScript";
   ```

2. **Functions**: Blocks of code that perform specific tasks.
   ```javascript
   function greetUser() {
       console.log("Welcome to Artado Search!");
   }
   ```

3. **Conditionals**: Execute different code based on conditions.
   ```javascript
   if (searchQuery === "JavaScript") {
       console.log("You're learning JavaScript!");
   } else {
       console.log("Search for something else.");
   }
   ```

4. **Loops**: Repeat a block of code multiple times.
   ```javascript
   for (let i = 0; i < 5; i++) {
       console.log("Loop iteration " + i);
   }
   ```

5. **DOM Manipulation**: JavaScript can be used to interact with the Document Object Model (DOM) to change the content and appearance of web pages.
   ```javascript
   let heading = document.querySelector('h1');
   heading.style.color = 'blue';
   ```

### Testing JavaScript in the Browser

You can test your JavaScript code directly in the browser using the Developer Tools:

1. **Open Developer Tools**: 
   - Right-click on the webpage and select **Inspect**.
   - Navigate to the **Console** tab.

2. **Run JavaScript**:
   - Type JavaScript code in the console and press **Enter** to execute it.

   Example:
   ```javascript
   console.log("Hello from Artado Search!");
   ```

   This will print the message in the console.

## Creating an Artado Extension

Let's create a simple Artado extension that fetches data from an API and displays it on the search results page.

### Example: Dictionary Lookup Extension

This extension will take the search query and fetch the definition of the word using a dictionary API.

```javascript
// Get the "i" query string parameter
const queryString = window.location.search;
const urlParams = new URLSearchParams(queryString);
const query = urlParams.get('i');

// Check if a query is present
if (query) {
    const apiUrl = `https://api.dictionaryapi.dev/api/v2/entries/en/${query}`;

    // Create a new element for displaying results
    const resultElement = document.createElement('div');
    resultElement.id = 'result';
    resultElement.style.textAlign = 'left';
    resultElement.style.marginLeft = '100px';
    resultElement.style.maxWidth = '500px';
    resultElement.style.backgroundColor = 'transparent';
    resultElement.style.border = "1px solid #bdbdbd";
    resultElement.style.borderRadius = "10px";
    resultElement.style.lineHeight = "20px";
    resultElement.style.padding = "10px";

    // Media query for smaller screens
    const mediaQuery = window.matchMedia('(max-width: 768px)');
    if (mediaQuery.matches) {
        resultElement.style.marginRight = 'auto';
        resultElement.style.marginLeft = 'auto';
    }

    // Send a request to the API
    fetch(apiUrl)
        .then(response => response.json())
        .then(data => {
            // Process the JSON response
            const wordData = data[0];
            const word = wordData.word;
            const phonetics = wordData.phonetics;
            const meanings = wordData.meanings;

            // Generate HTML representation
            let html = `<h2>${word}</h2>`;
            
            if (phonetics && phonetics.length > 0) {
                html += '<h3>Phonetics</h3>';
                phonetics.forEach(phonetic => {
                    html += `<p>${phonetic.text}</p>`;
                    if (phonetic.audio) {
                        html += `<audio controls><source src="${phonetic.audio}" type="audio/mpeg"></audio>`;
                    }
                });
            }
            
            if (meanings && meanings.length > 0) {
                html += '<h3>Meanings</h3>';
                meanings.forEach(meaning => {
                    html += `<p><strong>${meaning.partOfSpeech}</strong></p>`;
                    meaning.definitions.forEach(definition => {
                        html += `<p>${definition.definition}</p>`;
                    });
                });
            }

            // Set the generated HTML content
            resultElement.innerHTML = html;

            // Insert the resultElement into the page
            const buttons = document.getElementById('buttons_r');
            buttons.insertAdjacentElement('afterend', resultElement);
        })
        .catch(error => {
            console.error('Error fetching data:', error);
        });
}
```

### Understanding the Code

1. **Get the Query String**: We start by getting the `i` query string parameter, which is the search term entered by the user.

2. **Check if a Query Exists**: If a search term is present, we proceed to fetch data from the dictionary API.

3. **Create a Result Element**: We create a new `div` element to display the results on the page.

4. **Fetch Data from API**: Using the `fetch` function, we send a request to the dictionary API to get the definitions.

5. **Process and Display Data**: Once we get the data, we generate HTML content and insert it into the page.

### Testing Your Extension

You can test your extension code directly in the browser console before deploying it:

1. **Open Developer Tools**: Right-click on the Artado Search page and select **Inspect**.
2. **Go to the Console**: Navigate to the **Console** tab.
3. **Paste and Run Your Code**: Copy and paste your extension code into the console and press **Enter**.

This will allow you to see how your extension works and make adjustments as needed.

## Deploying Your Extension

Once you're happy with your extension, you can deploy it to be used on Artado Search.

### Upload Your Extension

You can share your extension with the Artado community by uploading it to [Artado Devs](https://devs.artado.xyz/):

1. **Create an Account**: Sign up or log in to Artado Devs.
2. **Upload Your Extension**: Provide a description, upload your JavaScript file, and share your extension.

## Learn More

JavaScript is a versatile language, and there's always more to learn. Here are some resources to deepen your understanding:

- [JavaScript Basics](https://www.w3schools.com/js/) - Start with the basics.
- [JavaScript.info](https://javascript.info/) - Detailed tutorials and guides.
- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript) - Comprehensive JavaScript documentation.

## Conclusion

Creating extensions for Artado Search is a great way to customize your experience and add new functionality. With just a little JavaScript knowledge, you can create powerful tools that enhance your search experience and share them with the community. Happy coding!
