# How to develop an Artado Theme

This page will show you how to create a theme for [Artado Search](https://www.artadosearch.com).

## Getting Started

You will need a CSS file for using themes. You can use [Stylus Editor](https://add0n.com/stylus.html) to test your theme live while creating it.

To access Stylus Editor, click on the extensions icon and press "Manage" button.
Then press "Write New Style" button and you can start creating themes.
Change "Applies to" setting to only for Artado Search, otherwise your theme will be applied to every website.

## Basics

### Add a background image

If you want your image to appear only on main page:

```
#homepage {
    background: url("Image link") no-repeat center fixed;
    -webkit-background-size: cover; -moz-background-size: cover; -o-background-size: cover; background-size: cover;
}
```

If you want your picture to appear on other pages (search results, settings etc.):

```
body {
    background-image: url("Image link")
}
```


### Modify search bar

#### Search Bar
```
#searchbar{
    margin-bottom:200px;
    width: 550px !important;    /* Be sure its same with Auto Complate List's width */
    border-radius: 10px;        /* Smooth corners */
}
```

#### Input Section
```
#searchinput{
    background-color:rgb(0, 0, 0);  /* Color of the input section */
}
```

#### Search Button
```
#searchbutton{
 color:rgb(255, 255, 255);          /* Color of magnifier */
 background-color:rgb(0, 0, 0);     /* Magnifier's background color */
}
```


### Modify bottom bar


```
#features .flex-wrap{
    padding-bottom:20px;       /* Change the amount of pixels */
    padding-top:20px;          /* And find the best for you */
    color:#fff;                /* Text color */
    background-color:#000;     /* Background Color */
}
```


## Example themes


This themes created by Artado Community and you can check them for more information!

- [Merkür Theme](https://github.com/KerimCan05/merkur-artadotheme/)
- [Atatürk Theme](https://github.com/KerimCan05/ataturk-artadorheme/)
- [HereUS UI 3.1](https://github.com/islekcaganmert/artado-hereus-ui-3.1-theme)

## Learn more

This is just the beginning. If you want to create great themes, you most go deeper in the world of CSS. You can learn more about CSS from [W3Schools](https://www.w3schools.com/css/default.asp).

## Upload your themes

You can share your themes from [Artado Devs](https://devs.artado.xyz/). Create an account an start uploading.
