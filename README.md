# Hugo Pamphlet
A clean, somewhat minimalist [Hugo](hugo-io-url)-theme to represent a pamphlet.

The top displays a navbar with configurable buttons.\
Below is a banner with an image or a flat color and a container with a title and button in the middle.\
The center always contains the main content while the sides give the ability
to display content on every page.

## Installation

If you already have a Hugo page set up, you can simply add this theme as a submodule into your project's `themes` directory:

```bash
git submodule add https://github.com/Lithimlin/hugo-pamphlet.git themes/hugo-pamphlet
```

## Configuration
This theme can be personalized easily and in many ways by adjusting the `config.toml`, `main.css`, and through setting the `type` field in your content pages.

### Theme Colors
You can adjust the theme colors of the page by editing the `:root` segment in the theme's `static/css/main.css`.

```css
:root {
  --primary-text-color: #fff;
  --highlight-text-color: rgb(10, 138, 101);

  --primary-color: rgb(13, 189, 139);
  --secondary-color: #e9e9e9;
  --background-color: #f6f6f6;

  --primary-highlight-color: rgb(9, 153, 112);
  --secondary-highlight-color: #9c9c9c;

  --topnav-height: 70px;
  --banner-height: 450px;
}
```

### Favicon
The favicon can be chagned by adjusting the `[params]` section of your pages' `config.toml`:

```toml
[params]
  favicon = "/images/favicon.png"
```

### Navigation
The navigation bar on the top of the page can be enabled by defining the appropriate `[menus]` in the `config.toml`. There is the main menu and the right main menu.

#### Main Menu
The main menu will be displayed starting from the left. On mobile, this menu will turn into a dropdown menu.

#### Right Menu
The right main menu will be right-aligned. It will **not** turn into a dropdown menu on the mobile version.

#### Images and Custom CSS Classes
There is also the ability to use images in front of or instead of a menu button's title. For this, the `pre` property can be used (see below). Furthermore, you can add more classes to the menu by using the `classes` parameter of the entry.

```toml
[menu]
  [[menu.main]]
    # Image button for the root page
    pre = "<img src='/images/icon.png'>"
    url = "/"
    weight = -95
  [[menu.main]]
    name = "Tell me more!"
    url = "/#tell-me-more"
    weight = -90

  [[menu.mainright]]
    name = "CTA"
    url = "/call-to-action"
    weight = 100
    [menu.mainright.params]
      class = "custom-class"

```

### Banner
If you want a banner on the top of the page that contains some text and some buttons, you can achieve this in a few ways.

#### Banner Text
You can set a banner text in the `config.toml`. This will produce a flat-colored banner with a container containing the specified text.

#### Banner Image
An image can be specified as the site's banner. If nothing else is set, just the image will be displayed. Otherwise, the container will be on top of the image.

#### Banner Buttons
Buttons on the banner can be created using the `buttons` menu as seen below. As with the main menu, custom classes can be added to the button using the `classes` parameter on the button.

```toml
[params]
  bannerText = "Digitales Lernzentrum"
  bannerImage = "/images/banner.png"

[menu]
  [[menu.buttons]]
    name = "Button"
    url = "/buttons"
    weight = -90
    [menu.buttons.params]
      class = "custom-class"
```

### Warnings
On the top of the content, warning boxes can be shown. This can be done by creating a new content page and giving it the `warning` type.

```yaml
---
title: "Warning"
type: "warning"
---
Some warning text
```

### Side Content
Similarly to the warnings, content can be specified to be displayed on the sides next to the main content of the page using the `left` or `right` page type.

### Footer
A copyright can be added to the footer setting the `copyright` attribute in the `config.toml` `params`:

```toml
[params]
  copyright = "Copyleft"
```

## Feedback

You can provide feedback via the issues on this repository.
