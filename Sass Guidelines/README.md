Scss Guidelines
===============

**Common Guide**
----------------

* No Inline CSS, always use external file.

* Minify and gzip css file on production site.

* Separate each ruleset by a blank line.

* All CSS rules should have a space after the selector & colon and a trailing semi-colon.
Bad:
  .block
  {
  color: red;
  }

Bad:
  .block{
    color:red;
  }

Good:
  .block {
    color: red;
  }

* Include a space after each comma in comma-separated property or function values.

* Use of BEM selectors instead of camelCase OR other format.
Bad:
  .blockSearch

Good:
  .block--search

* Don't use unit if value is 0.
Bad:
  width: 0px;
Good:
  width: 0;

* Never display trailing zeros.
Bad:
padding: 0.5em;

Good:
padding: .5em;

* Don't over qualify class or ID selectors. Leads to specificity issues further down the line.
Bad:
div.block

Good:
.block
* Quote attribute values in selectors.
    eg. input[type="checkbox"]

* Use Icon fonts where possible otherwise use sprites for images.

* Don't use `!important` reactively. But it is okay to use `!important` on helper classes only. To add `!important` pre-emptively is fine, e.g. `.error { color:red!important }`, as you know you will always want this rule to take precedence.

* Use single quotes '' for strings.
Bad:
  font-family: Helvetica Neue Light, Helvetica, Arial, sans-serif;
  background-image: url(/images/kittens.jpg);

Good:
  font-family: 'Helvetica Neue Light', 'Helvetica', 'Arial', sans-serif;
  background-image: url('/images/kittens.jpg');

**Sass Guide**
--------------

* Use Scss syntax not sass.
Bad:
  .block
    color: red;

Good:
  .block {
    color: red;
  }


* Don't over nest selectors.
Bad:
  .menu {
    .menu__item {
      .menu__link {
        // something...
        }
      }
    }
  }

Good:
  .menu {
    .menu__item {
      // something...
    }
    .menu__link {
      // something...
    }
  }

* Use variable names in a format.
Bad:
  $header-bg-color: red;
  $menu-link-color: green;
  $footer-link-color: blue;

Good:
  $color-header-bg: red;
  $color-link-color: green;
  $color-footer-link: blue;

* Top-level numeric calculations should always be wrapped in parentheses.
Bad:
  width: 100% / 3;

Good:
  width: (100% / 3);



**Architecture of Sass directory structure**
--------------------------------------------

stylesheets/
|- main.scss
|- base/
|    |- _init.scss             /* @import libraries here. */
|    |- _variables.scss
|    |- _normalize.scss
|    |- _typography.scss
|- utilities/
|    |- _mixins.scss
|    |- _helpers.scss          /* utility/placeholder classes */
|    |- ...
|- layout/
|    |- _layout-default.scss
|    |- _header.scss
|    |- _page-about.scss
|    |- ...
|- components/
|    |- _nav.scss
|    |- _buttons.scss
|    |- _carousel.scss
|    |- ...
|- pages/
|    |- _front.scss
|    |- _about.scss
|    |- ...