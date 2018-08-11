# extstyler

**custom styles for web pages**

## About

Extstyler is an empty Chrome Extension made for one purpose: to add custom CSS and JavaScript to websites.

At least once a week I wish I could just add a little CSS to a website, or create a fix for a specific person without making a change to the whole site experience for other users. I made this chrome extension as an esy starting point every time I catch myself saying: "If you just stuck this little bit of CSS here" now I can just clone this repo, add my script, and load it into Chrome to use it.


## Why bother to load custom scripts & styles?

- you want to apply a 3rd-party fix a website you don't have control over in a way you can share with others

- you're a developer who wants to quickly test out some code on top of a site you may not have control over

- you wish to make changes to web pages visited by one (or more) users (e.g. increase contrast, font settings, spacing)

- you're an incredibly bold developer and want to demonstrate what you can do for a client's site before they hire you by demoing your code on their live site

- you are building a Chrome extension and want to use this as a quick starting point for your own extension


## How To Install

### 1) Visit Chrome's Extension page

To install `extstyler` you will need to load up Chrome and navigate to your extensions page located [chrome://extensions](chrome://extensions) (link valid in Chrome only).

You can also access this page by using the Chrome menu and selecting: **Window > Extensions**

### 2) Click on the 'Load Unpacked Extension' button

On the [chrome://extensions](chrome://extensions) page you will find a button labelled 'Load Unpacked Extension…'

This should bring up a dialog box asking you to select the `extstyler` folder on your hard drive.

### 3) Reload your chrome extension after each edit

Once you have made a change to any of your extensions and you wish to view these in your browser, we'll need to navigate once more to [chrome://extensions](chrome://extensions) and either:

- press your browser's reload button in the toolbar
- use the keyboard shortcut CTRL-R (or ⌘-R on OS X)
- click the 'Reload' link at the bottom of the extension description

## How to add styles

Extstyler has some built-in smarts that make it easy to add custom styles to just one website (instead of applying to every website you visit while the extension is enabled). Extstyler will automatically add 2 classes to the `<html>` tag of any site it loads: `extstyler` and a simple version of the domain name where the site is being accessed. This means you could target every webpage in your browser with a rule like:

```
a {
  color: green;
}
```

But if you only wanted to change the `<a>` tags on a site like https://github.com we can expect the `<html>` tag to look something like: `<html class="extstyler github"`. You could target just those pages by adding `html.extstyler.github` before your CSS rule to make it apply only to sites where the `<html>` tag includes the classes `extstyler` and `github` for example:

```
html.extstyler.github a {
  color: green;
}
```

This means within the one CSS file you have the freedom to be able to combine browser-wide style overrides that alter every page the user visits, as well as site-specific rules for one or more sites that will only apply when you are on those pages without showing up elsewhere.