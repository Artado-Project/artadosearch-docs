# User Guide for Artado Search

Welcome to the Artado Search User Guide! This documentation is designed to help you make the most out of Artado Search by guiding you through its various features and functionalities.

## Table of Contents

1. [Introduction to Artado Search](#introduction-to-artado-search)
2. [Getting Started](#getting-started)
   - [How to Set Artado as Your Default Search Engine](#how-to-set-artado-as-your-default-search-engine)
   - [Basic Search](#basic-search)
   - [Using Advanced Search](#using-advanced-search)
3. [Customizing Artado Search](#customizing-artado-search)
   - [Themes](#themes)
   - [Extensions](#extensions)
4. [Managing Your Search Preferences](#managing-your-search-preferences)
   - [Setting Preferences](#setting-preferences)
   - [Saving Search Settings](#saving-search-settings)
5. [Using Artado Proxies](#using-artado-proxies)
6. [Contributing to Artado](#contributing-to-artado)
7. [FAQ](#faq)
8. [Getting Help](#getting-help)

---

## Introduction to Artado Search

Artado Search is a powerful and customizable search engine designed to provide fast, private, and accurate search results. Whether you’re looking for web pages, images, or news, Artado Search delivers what you need while respecting your privacy.

## Getting Started

### How to Set Artado as Your Default Search Engine

To make the most out of Artado Search, you might want to set it as your default search engine. Here’s how you can do it:

1. **Google Chrome**:
   - Open Chrome and go to [Artado Search](https://www.artadosearch.com).
   - Click on the three vertical dots in the top-right corner.
   - Select **Settings** > **Search engine** > **Manage search engines**.
   - Add Artado Search using the following settings:
     - **Search engine**: Artado Search
     - **Keyword**: artado
     - **URL with %s in place of query**: `https://www.artadosearch.com/search?q=%s`
   - Set Artado as the default search engine.

2. **Firefox**:
   - Open Firefox and go to [Artado Search](https://www.artadosearch.com).
   - Click on the search bar and select **Change Search Settings**.
   - Scroll down to **One-Click Search Engines** and click **Add** next to Artado.
   - Make Artado the default by selecting it from the list.

3. **Microsoft Edge**:
   - Open Edge and go to [Artado Search](https://www.artadosearch.com).
   - Click on the three horizontal dots in the top-right corner.
   - Select **Settings** > **Privacy, search, and services** > **Address bar and search**.
   - Add Artado Search as a new search engine with the following settings:
     - **Name**: Artado Search
     - **Keyword**: artado
     - **URL with %s in place of query**: `https://www.artadosearch.com/search?q=%s`
   - Set it as your default search engine.

### Basic Search

Using Artado Search is straightforward. Simply enter your search term in the search bar and hit **Enter**. Artado will return a list of relevant results sorted by relevance and date.

### Using Advanced Search

For more specific searches, you can use the advanced search features:

- **Exact Phrase**: Use quotes (`"like this"`) around your search term to find results with that exact phrase.
- **Exclude Words**: Use a minus sign (`-`) before a word to exclude results containing that word.
- **Search Specific Sites**: Use `site:example.com` to search within a specific website.

Example: `artificial intelligence site:wikipedia.org`

## Customizing Artado Search

### Themes

Artado Search allows you to customize its appearance through themes. Here’s how you can create and apply themes:

1. **Choose a Theme**: Visit the [Themes](#) page to browse available themes created by the Artado community.
2. **Create Your Own Theme**: Follow the guide in the [How to Develop an Artado Theme](/Developer%20Guide/How%20to%20Develop%20an%20Artado%20Extension.md) to create your own custom theme using CSS.

### Extensions

Extend the functionality of Artado Search by developing and installing extensions. These are JavaScript-based custom scripts that can add features like dictionary lookups, instant translation, and more.

- **Learn How to Develop Extensions**: Check out our [How to Develop an Artado Extension](/Developer%20Guide/How%20to%20Develop%20an%20Artado%20Extension.md) guide.
- **Install Extensions**: Browse and install extensions from the [Artado Devs](https://devs.artado.xyz/) community site.

## Managing Your Search Preferences

### Setting Preferences

Artado Search allows you to customize your search experience by adjusting various settings. To access the settings:

1. Click on the **Settings** icon on the menu.
2. Adjust the following options:
   - **Theme**: Select your preferred theme, you can also find more themes from Workshop.
   - **Language**: Set your preferred search language.
   - **Logo**: Select your preferred logo, you can also find more logos from Workshop.
   - **Categories**: Select your preferred location of the search categories.

### Saving Search Settings

Your search settings can be saved for future sessions. To save your settings:

1. After adjusting your settings, click **Apply**.
2. You can save your preferences with creating a [Profile](https://www.artadosearch.com/Settings/Profiles).

## Using Artado Proxies

Artado Proxies allow you to access Artado Search through different servers, enhancing privacy and access. Artado automatically
connects you to one of the proxies that is in the Artado database. To setup a proxy:

1. Host an [Artado Proxy](https://github.com/Artado-Project/ArtadoProxy).
2. Got to [Proxy](https://www.artadosearch.com/Settings/Proxy) page on settings.
3. Enter the URL of your proxy.
4. Check the "Allow other users to use this proxy." to add your proxy to the Artado database.
5. Click "Apply"

## Contributing to Artado

Artado is a community-driven project, and there are many ways you can contribute:

1. **Use Artado**: Make Artado your default search engine and recommend it to others.
2. **Donate**: Support the project by donating from [Patreon](https://www.patreon.com/artadosoft) or [Kreosus](https://kreosus.com/artadosoft).
3. **Contribute Code**: Join the development efforts by contributing to the codebase. Check out the [Contributing Guide](https://github.com/Artado-Project/artadosearch/CONTRIBUTING.md).
4. **Host a Proxy**: Host an Artado Proxy to help expand the network. Learn more [here](https://github.com/Artado-Project/ArtadoProxy).
5. **Create Themes and Extensions**: Develop themes and extensions to enhance the user experience.

## FAQ

Visit the [FAQ](faq.md) section to find answers to common questions about using Artado Search.

## Getting Help

If you need help or have questions that aren’t covered in this guide:

1. **Community Forums**: Join the discussion on the [Artado Community Forum](https://forum.artado.xyz).
2. **Contact Support**: Reach out to the support team via [email](mailto:arda@artadosearch.com).
