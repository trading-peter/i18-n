# dom-purify
Simple component that uses the awesome [DOMPurify](https://github.com/cure53/DOMPurify) library to sanitize it's content.
Build with Polymer ^1.0.0.

This repository also includes the `dom-purify-behavior` that can be used to use html sanitize in other elements.

## Docs & Demo

See the [component page](http://pkaske.github.io/dom-purify) for more information.

## Configure DOMPurify

The component (or better, the `dom-purify-behavior`) has a property called `sanitizeOptions`.
Use it to forward [DOMPurify](https://github.com/cure53/DOMPurify)'s configuration.

## How to install

Clone this repository or use bower:

`bower install pkaske/dom-purify --save`
