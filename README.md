# `<f-i18n>`

These elements were heavily inspired by [`<i18-n>`](https://github.com/pkaske/i18-n), written by *pkaske*.

- Try out [live demo](https://firmfirm.github.io/f-i18n/components/f-i18n/demo/).
- Learn more about elements in [component page](https://firmfirm.github.io/f-i18n/).
- [Run tests](https://firmfirm.github.io/f-i18n/components/f-i18n/test/) in your browser.

Using ES6 features, so take care in production.

## Installation

```bash
# Assuming Node.js and Bower are already installed
bower install --save f-i18n
```

## Overview

The system consists of two elements working together: `<f-i18n>` and `<f-i18n-domain>`.

`<f-i18n>` elements provides content or `value` with translated strings of locale specified in their corresponding `<f-i18n-domain>` element.

The language to display isn't set on the `<f-i18n>` elements but on the `<f-i18n-domain>`. All `<f-i18n>` elements are automatically updated after the locale was changed on corresponding `<f-i18n-domain>` element.

## Usage

1. Initialize the `<f-i18n-domain>` domains.

  ```html
  <!-- Will use the translations from `path/to/locales/default-de.json` -->
  <f-i18n-domain
    messages-url="path/to/locales"
    locale="de"></f-i18n-domain>

  <!-- Will use the translations from `other/path/foobar-en.json` -->
  <f-i18n-domain
    messages-url="other/path"
    domain="foobar"
    locale="en"></f-i18n-domain>
  ```

2. Use `<f-i18n>` to get the translations.

  ```html
  <!-- Message from "default" domain, with key "welcome".
       Will display placeholder text until translation is loaded. -->
  <f-i18n msgid="welcome" placeholder="Welcome!"></f-i18n>

  <!-- Message from "foobar" domain, with key "hello".
       Will not display any text, but set and notify "value" property. -->
  <f-i18n provider m="foobar.hello" placeholder="Hello!" value="{{msgHello}}"></f-i18n>
  <p>[[msgHello]]</p>
  ```

# Development

From here on, documentation will only concern development of this component.

## Dependencies

Element dependencies are managed via [Bower](http://bower.io/). You can
install that via:

    npm install -g bower

Then, go ahead and download the element's dependencies:

    bower install

## Playing With Your Element

If you wish to work on your element in isolation, we recommend that you use
[Polyserve](https://github.com/PolymerLabs/polyserve) to keep your element's
bower dependencies in line. You can install it via:

    npm install -g polyserve

And you can run it via:

    polyserve

Once running, you can preview your element at
`http://localhost:8080/components/f-i18n/`, where `f-i18n` is the name of the directory containing it.

## Testing Your Element

Simply navigate to the `/test` directory of your element to run its tests. If
you are using Polyserve: `http://localhost:8080/components/f-i18n/test/`

### web-component-tester

The tests are compatible with [web-component-tester](https://github.com/Polymer/web-component-tester).
Install it via:

    npm install -g web-component-tester

Then, you can run your tests on _all_ of your local browsers via:

    wct

#### WCT Tips

`wct -l chrome` will only run tests in chrome.

`wct -p` will keep the browsers alive after test runs (refresh to re-run).

`wct test/some-file.html` will test only the files you specify.
