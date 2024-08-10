# How to Develop an Artado Theme

This guide will walk you through the process of creating a custom theme for [Artado Search](https://www.artadosearch.com). Whether you're new to CSS or a seasoned developer, you'll find the steps and tips you need to design a unique look for Artado.

## Getting Started

To create a theme for Artado Search, you'll primarily be working with CSS. You can use the [Stylus Editor](https://add0n.com/stylus.html) to test your theme live as you create it, allowing you to see changes in real-time.

### Installing Stylus Editor

1. **Install Stylus**: First, install the Stylus browser extension from the [Chrome Web Store](https://chrome.google.com/webstore/detail/stylus/clngdbkpkpeebahjckkjfobafhncgmne) or [Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/styl-us/).
2. **Access Stylus Editor**:
   - Click the Stylus icon in your browser's toolbar.
   - Select **Manage** to access your styles.
   - Press **Write New Style** to start creating your theme.

### Setting Up Your Theme

- **Target Artado Search**: In the Stylus Editor, change the "Applies to" setting to only apply your CSS to `https://www.artadosearch.com`. This ensures that your theme is applied only to Artado Search and not to every website you visit.

## Basics

### Adding a Background Image

Customizing the background is a great way to set the tone of your theme.

#### Main Page Background

To add a background image that only appears on the main search page:

```css
#homepage {
    background: url("Image link") no-repeat center fixed;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
}
```

#### Global Background

To apply the background image to all pages, including search results and settings:

```css
body {
    background-image: url("Image link");
}
```

### Customizing the Search Bar

The search bar is one of the most prominent elements on the page. Here’s how to customize it:

#### Search Bar Container

```css
#searchbar {
    margin-bottom: 200px;
    width: 550px !important;   /* Ensure it matches the Auto Complete List's width */
    border-radius: 10px;       /* Smooth corners */
}
```

#### Search Input Section

```css
#searchinput {
    background-color: rgb(0, 0, 0);  /* Input field background color */
    color: rgb(255, 255, 255);       /* Text color */
}
```

#### Search Button

```css
#searchbutton {
    color: rgb(255, 255, 255);       /* Color of the magnifier icon */
    background-color: rgb(0, 0, 0);  /* Button background color */
}
```

### Customizing the Bottom Bar

The bottom bar can be styled to complement the overall theme:

```css
#features .flex-wrap {
    padding-bottom: 20px;        /* Adjust the padding to your liking */
    padding-top: 20px;
    color: #fff;                 /* Text color */
    background-color: #000;      /* Background color */
}
```

### Advanced Customizations

#### Hover Effects

To add hover effects for interactive elements:

```css
#searchbutton:hover {
    background-color: rgb(255, 165, 0); /* Change button color on hover */
    color: #000;                         /* Change text/icon color on hover */
}
```

#### Typography

To customize the font and text styles:

```css
body {
    font-family: 'Arial', sans-serif;
    font-size: 16px;
    color: #333;  /* Base text color */
}

h1, h2, h3 {
    font-family: 'Georgia', serif;
    color: #444;
}
```

### Example Themes

Explore these example themes created by the Artado community for inspiration and learning:

- [Merkür Theme](https://github.com/KerimCan05/merkur-artadotheme/)
- [Atatürk Theme](https://github.com/KerimCan05/ataturk-artadorheme/)
- [HereUS UI 3.1](https://github.com/islekcaganmert/artado-hereus-ui-3.1-theme)

### Testing and Debugging

While working on your theme, use browser developer tools (`F12` or `Ctrl+Shift+I`) to inspect elements, test CSS changes, and troubleshoot any issues.

## Learn More

This is just the beginning. If you're interested in creating more sophisticated themes, dive deeper into the world of CSS:

- [CSS Basics](https://www.w3schools.com/css/css_intro.asp) - A great starting point if you're new to CSS.
- [CSS Tricks](https://css-tricks.com/) - Advanced techniques and tips for improving your styles.
- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS) - Comprehensive resource for CSS properties and best practices.

## Upload Your Themes

Once you've created your theme, share it with the community! You can upload your theme on [Artado Devs](https://devs.artado.xyz/):

1. **Create an Account**: Sign up or log in to Artado Devs.
2. **Upload Your Theme**: Navigate to the upload section, provide a description, and share your creation with the world.

---

This guide should give you a strong foundation for creating and sharing custom themes for Artado Search. Have fun experimenting with different styles and making Artado Search your own!
