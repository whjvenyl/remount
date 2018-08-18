<br>

<p align='center'><img src='docs/images/remount.png' width='500'></p>

<p align='center'>
<a href='https://codepen.io/rstacruz/pen/EpBZRv?editors=1010'>Demo</a> ⚡ <a href='https://github.com/rstacruz/remount#remount'>Docs</a>
<br>
1kb gzip'd &nbsp;&middot;&nbsp; No dependencies &nbsp;&middot;&nbsp; IE9 support
</p>

<br>

# Remount

> 🔀 Mount React components to the DOM using custom elements

Remount lets you use your React components anywhere in the page as a web component (custom element).

[![Status](https://api.travis-ci.org/rstacruz/remount.svg?branch=master)](https://travis-ci.org/rstacruz/remount 'See test builds')

## Installation

Remount is available through the [npm package repository](https://yarnpkg.com/en/package/remount).

- Via yarn: `yarn add remount`
- or npm: `npm install remount`

Be sure to use the [recommended polyfills](#polyfills) below as well!

## Usage

Let's start with any React component. Here's one:

```js
const Greeter = ({ name }) => {
  return <div>Hello, {name}!</div>
}
```

Use _define()_ to define custom elements. Let's define a `<x-greeter>` element:

```js
import { define } from 'remount'

define({ 'x-greeter': Greeter })
```

You can now use it anywhere in your HTML. :boom:

```html
<x-greeter props-json='{"name":"John"}'></x-greeter>
```

More at **[API documentation →](docs/api.md)**

## Use cases

Some ideas on why you might want to consider Remount for your project:

|                                                    |                                                                                                                                                                                                            |
| -------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <img src='http://source.unsplash.com/400x200?sea'> | ✨ **Adding React to non-SPA apps** <br> You can use React components on any page of a "regular" HTML site. Great for adding React to apps built on Rails or Phoenix.                                      |
|                                                    |                                                                                                                                                                                                            |
| <img src='http://source.unsplash.com/400x200?sun'> | 💞 **Interop with other frameworks** <br> Remount lets you use your React components just like any other HTML element. This means you can use React with Vue, Angular, or any other DOM library/framework. |
|                                                    |                                                                                                                                                                                                            |

## Custom properties

> `<x-greeter name="John"></x-greeter>`

Only the `props-json` attribute is supported by default. To support custom properties like above, pass the names of attributes you want Remount to use.

```js
import { define } from 'remount'

define({
  'x-greeter': {
    component: Greeter,
    attributes: ['name']
  }
})
```

More at **[API documentation →](docs/api.md)**

## Browser support

Remount supports all browsers [supported by React](https://reactjs.org/docs/react-dom.html#browser-support), which includes IE9. Use the polyfills below to ensure the best compatibility.

## Polyfills

We recommend these two polyfills provided by the [@webcomponents/webcomponentsjs][@webcomponents/webcomponentsjs] package. Load it via JavaScript in your app's entry point:

```js
// Add the package via: yarn add @webcomponents/webcomponentsjs
import '@webcomponents/webcomponentsjs/custom-elements-es5-adapter.js'
import '@webcomponents/webcomponentsjs/webcomponents-loader.js'
```

Or you can load it via CDN:

```html
<script crossorigin src='https://cdn.jsdelivr.net/npm/@webcomponents/webcomponentsjs@2.0.4/custom-elements-es5-adapter.js'></script>
<script crossorigin src='https://cdn.jsdelivr.net/npm/@webcomponents/webcomponentsjs@2.0.4/webcomponents-loader.js'></script>
```

[@webcomponents/webcomponentsjs]: https://yarn.pm/@webcomponents/webcomponentsjs

More info at the [Polyfills documentation](./docs/polyfills.md).

## More info

- [Builds](./docs/builds.md) &mdash; ES2015+ and ES Module builds are also provided.
- [API documentation](./docs/api.md)
- [Frequently-asked questions](./docs/faq.md)
- [Comparison with alternatives](./docs/comparison.md)
- [Polyfills](./docs/polyfills.md)

## Thanks

**remount** © 2018, Rico Sta. Cruz. Released under the [MIT] License.<br>
Authored and maintained by Rico Sta. Cruz with help from contributors ([list][contributors]).

> [ricostacruz.com](http://ricostacruz.com) &nbsp;&middot;&nbsp;
> GitHub [@rstacruz](https://github.com/rstacruz) &nbsp;&middot;&nbsp;
> Twitter [@rstacruz](https://twitter.com/rstacruz)

[mit]: http://mit-license.org/
[contributors]: http://github.com/rstacruz/remount/contributors

<br>

[![](https://img.shields.io/github/followers/rstacruz.svg?style=social&label=@rstacruz)](https://github.com/rstacruz) &nbsp;
[![](https://img.shields.io/twitter/follow/rstacruz.svg?style=social&label=@rstacruz)](https://twitter.com/rstacruz) <br>
