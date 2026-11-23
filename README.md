# restaurant-page

A multi-page website for The Leaky Cauldron, the inn from *Harry Potter*, built for [The Odin Project](https://www.theodinproject.com/) curriculum. It's a fan project and isn't affiliated with the Harry Potter franchise.

**Live demo:** https://equanimity-studio.github.io/restaurant-page/

Built with CSS and vanilla JavaScript, bundled with webpack. The HTML page is almost empty: JavaScript builds every element.

## Features

- Home, Menu, About and Contact tabs that switch without reloading the page
- Menu split into Beverages, Signature Dishes and Desserts, each with pictures, descriptions and prices in wizard currency
- Custom fonts and a fixed full-screen background image
- Layout and navigation that adapt to smaller screens

## What I learned

- **Organizing a site as JavaScript modules**, with one file per tab and a subfolder for the menu pages
- **Building and clearing page content with JavaScript**, so one HTML page acts like several
- **Bundling with webpack**, including importing images and fonts into JavaScript and CSS
- **Navigation details**: keeping the current tab highlighted, hover effects and transitions
- **Mobile background fixes**, including a workaround for iOS Safari, which doesn't support fixed backgrounds the usual way

## Looking back: what I'd do differently

- **Store content as data, not code.** Each menu item is about 15 lines of hand-written DOM code (`card1`, `card2`, `card3`…). An array of menu items (`{ name, description, price, image }`) and a single `createMenuCard()` function would cut most of that code.
- **Don't build the same thing twice.** The home page is built once in `site.js` and again in `home.js`. One function should do both.
- **One function for switching tabs.** Each tab adds and removes the `selected` class on all four buttons by hand. A shared `setActiveTab()` would do that in one place.
