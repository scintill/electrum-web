INDEX
=====

## Table of Contents

  * [Overview](https://docs.electrum.org)
  * [Quick Start](https://docs.electrum.org/quick-start)
  * [Installation](https://docs.electrum.org/install)
  * [Setup](https://docs.electrum.org/setup)
  * [Architecture](https://docs.electrum.org/architecture)
  * [Usage](https://docs.electrum.org/usage)
  * [Guides](https://docs.electrum.org/guides)
  * [Plugins](https://docs.electrum.org/plugins)
  * [Troubleshooting](https://docs.electrum.org/troubleshooting)
  * [Developing](https://docs.electrum.org/developing)
  * [Glossary](https://docs.electrum.org/glossary)
  * [FAQ](https://electrum.org/support/faq)
  * [Support](https://electrum.org/support)


--------------------------------------------------------------------------------

## Overview

*go to "Quick Start" for a fast-paced introduction*

#### The Story of Electrum

```
:'::.:::::.:::.::.:
: :.: ' ' ' ' : :':
:.:     _.__    '.:             Welcome to ecdsa.org
:   _,^"   "^x,   :
'  x7'        `4,
 XX7            4XX             Support this node:
 XX              XX             1NTiGdrGgQrA46x9dv7XKhznKgcHrhVxo
 Xl ,xxx,   ,xxx,XX
( ' _,+o, | ,o+,"
 4   "-^' X "^-'" 7             Electrum is free software; you may
 l,     ( ))     ,X             operate your own Electrum server.
 :Xx,_ ,xXXXxx,_,XX             See http://electrum.org
  4XXiX'-___-`XXXX'
   4XXi,_   _iXX7'
  , `4XXXXXXXXX^ _,             Help us make Electrum available in your language:
  Xx,  ""^^^XX7,xX              https://en.bitcoin.it/wiki/Electrum/Translation
W,"4WWx,_ _,XxWWX7'
Xwi, "4WW7""4WW7',W
TXXWw, ^7 Xk 47 ,WH
:TXXXWw,_ "), ,wWT:
::TTXXWWW lXl WWT:
```


#### About the Docs

This documentation will guide you through Electrum's foundational
features.

We'll begin with the essentials and move to advanced features for
expert users.


--------------------------------------------------------------------------------

## Quick Start


--------------------------------------------------------------------------------

## Installation


--------------------------------------------------------------------------------

## Setup


--------------------------------------------------------------------------------

## Architecture and Philosophy of Use


--------------------------------------------------------------------------------

## Usage


--------------------------------------------------------------------------------

## Guides


--------------------------------------------------------------------------------

## Plugins


--------------------------------------------------------------------------------

## Troubleshooting


--------------------------------------------------------------------------------

## Developing


--------------------------------------------------------------------------------

## Glossary



  * [0. Overview](#overview)
  * [1. Getting Started: Installation and First Steps](#getting-started-installation-and-first-steps)
  * [2. Forms](/styleguide/css/2.0)
  * [3. Source Code](/styleguide/css/3.0)
  * [4. Text Styling](/styleguide/css/4.0)
  * [5. Listings](/styleguide/css/5.0)
  * [6. Boxed Groups](/styleguide/css/6.0)
  * [7. Icons](/styleguide/css/7.0)
  * [8. Navigation](/styleguide/css/8.0)
  * [9. Behavior](/styleguide/css/9.0)
  * [10. Discussion](/styleguide/css/10.0)
  * [11. Colors](/styleguide/css/11.0)
  * [12. Animations](/styleguide/css/12.0)
  * [13. Select Menu](/styleguide/css/13.0)
  * [14. Blank slate](/styleguide/css/14.0)
  * [15. Alerts](/styleguide/css/15.0)
  * [16. Pagehead](/styleguide/css/16.0)
  * [17. Repo selector](/styleguide/css/17.0)

# CSS Styleguide

Welcome to the GitHub CSS Styleguide. It's pretty rad. Before
reading this, you should have a general understanding for
**specificity**, the [**SCSS**](http://sass-lang.com) syntax, and
[**KSS**](https://github.com/kneath/kss) documentation..

While we port our styles over to SCSS with KSS documentation, please
make sure to upgrade an entire element's CSS at once. Do not mix small
amounts of SCSS in with plain CSS. Do your future self a favor.

If you're visiting from the internet, feel free to learn from our
style. This is a guide we use for our own apps internally at GitHub. We
encourage you to set up one that works for your own team.

## Coding Style

  * Use soft-tabs with a two space indent.
  * Put spaces after `:` in property declarations.
  * Put spaces before `{` in rule declarations.
  * Use hex color codes `#000` unless using rgba.
  * Use `//` for comment blocks (instead of `/* */`).
  * Document styles with [KSS](https://github.com/kneath/kss).

Here is good example syntax:

    // This is a good example!
    .styleguide-format {
      border: 1px solid #0f0;
      color: #000;
      background: rgba(0,0,0,0.5);
    }


## SCSS Style

  * Any `$variable` or `@mixin` that is used in more than one file should be put in `globals/`. Others should be put at the top of the file where they're used.
  * As a rule of thumb, don't nest further than 3 levels deep. If you find yourself going further, think about reorganizing your rules (either the specificity needed, or the layout of the nesting).

## File Organization

In general, the CSS file organization should follow something like this:

    styles
    ├── components
    │   ├── comments.scss
    │   └── listings.scss
    ├── globals
    │   ├── browser_helpers.scss
    │   ├── responsive_helpers.scss
    │   ├── variables.scss
    ├── plugins
    │   ├── jquery.fancybox-1.3.4.css
    │   └── reset.scss
    ├── sections
    │   ├── issues.scss
    │   ├── profile.scss
    └── shared
        ├── forms.scss
        └── markdown.scss


Use [Sprockets](https://github.com/sstephenson/sprockets) to **require** files. However, you should explicitly **import** any scss that does not generate styles (`globals/`) in the particular SCSS file you'll be needing it's helpers in. Here's a good example:

    //= require_tree ./plugins
    //= require my_awesome_styles

    @import "../globals/basic";

    .rule { ... }


## Pixels vs. Ems

Use `px` for `font-size`, because it offers absolute control over text. Additionally, unit-less `line-height` is preferred because it does not inherit a percentage value of its parent element, but instead is based on a multiplier of the `font-size`.

## Class naming conventions

Never reference `js-` prefixed class names from CSS files. `js-` are used exclusively from JS files.

Use the `is-` prefix for state rules that are shared between CSS and JS.

## Specificity (classes vs. ids)

Elements that occur **exactly once** inside a page should use IDs, otherwise, use classes. When in doubt, use a class name.

  * **Good** candidates for ids: header, footer, modal popups.
  * **Bad** candidates for ids: navigation, item listings, item view pages (ex: issue view).

When styling a component, start with an element + class namespace (prefer class names over ids), prefer direct descendant selectors by default, and use as little specificity as possible. Here is a good example:

    <ul class="category-list">
      <li class="item">Category 1</li>
      <li class="item">Category 2</li>
      <li class="item">Category 3</li>
    </ul>


    ul.category-list { // element + class namespace

      &>li { // direct descendant selector > for list items
        list-style-type: disc;
      }

      a { // minimal specificity for all links
        color: #ff0000;
      }
    }


### CSS Specificity guidelines

  * If you must use an id selector (`#selector`) make sure that you have no more than _one_ in your rule declaration. A rule like `#header .search #quicksearch { ... }` is considered harmful.
  * When modifying an existing element for a specific use, try to use specific class names. Instead of `.listings-layout.bigger` use rules like `.listings-layout.listings-bigger`. Think about `ack/grep`ing your code in the future.
  * The class names `disabled`, `mousedown`, `danger`, `hover`, `selected`, and `active` should _always_ be namespaced by a class (`button.selected` is a good example).

### Experimental features (staff only)

We like to ship staff only and experimental features. This requires some discipline when writing CSS since the existing feature and experimental feature's CSS will be served simultaneously. Always keep these goals in mind:

  * Style new features without affecting existing features styling.
  * Easily remove experimental feature CSS if they don't work out.
  * Easily remove CSS for old features when new features ship.

When developing beta or experimental features, replace the root namespace with a `-experimental` variant and deprecate the existing root node. In general it's better to duplicate styles in experimental blocks than try and extend the existing styles.

Given an existing feature:

    <div class="notifications">
      <ul class="navigation">
        <li><a href="#">Notifications</a></li>
        <li><a href="#">Messages</a></li>
      </ul>
      <div class="notifications-listing">
        <a href="#">dragon commented on Issue #551</a>
        <a href="#">mojombo commented on Issue #91</a>
        <a href="#">defunkt uploaded a new file to defunkt/resque</a>
      </div>
    </div>


    // Deprecated: Existing notifications + messages design. To be removed when
    // notifications-next ships.
    //
    // Styleguide 4.5.1
    .notifications {
      ul.navigation {
        float: left;
        width: 200px;
        background: #eee;
      }

      .notification-listing {
        &>a {
          display: block;
          font-weight: bold;
        }
      }
    }


A good experimental version would be:

    <div class="notifications-experimental">
      <h2>New hot notifications!</h2>
      <ul class="navigation">
        <li><a href="#">Important</a></li>
        <li><a href="#">@mentions</a></li>
        <li><a href="#">Everything</a></li>
      </ul>
      <ul class="notifications-listing">
        <a href="#">dragon commented on Issue #551</a>
        <a href="#">mojombo commented on Issue #91</a>
        <a href="#">defunkt uploaded a new file to defunkt/resque</a>
      </ul>
    </div>


    // Experimental: Notifications, the new hotness version.
    //
    // Styleguide 4.5.2
    .notifications-experimental {
      ul.navigation {
        float: right;
        width: 250px;
      }

      .notification-listing {
        &>a {
          float: right;
          color: #ff0000;

        }
      }
    }


And of course, **remember to rename your rules** when experimental features ship.

  * [Status](https://status.github.com/)
  * [API](http://developer.github.com)
  * [Training](http://training.github.com)
  * [Shop](http://shop.github.com)
  * [Blog](/blog)
  * [About](/about)
[ ](/)

  * © 2014 GitHub, Inc.
  * [Terms](/site/terms)
  * [Privacy](/site/privacy)
  * [Security](/security)
  * [Contact](/contact)

Something went wrong with that request. Please try again.
post_install() {
  update-desktop-database -q
  printf "$ecdsa\n"
}

post_upgrade() {
  post_install
}

post_remove() {
  update-desktop-database -q
}
