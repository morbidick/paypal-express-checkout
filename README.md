# Polymer 2 wrapper for the Paypal Express Checkout button

[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/morbidick/paypal-express-checkout)

Polymer 2 paypal button. Please use with caution, there are multiple restrictions with the paypal library!

## :fire: Restrictions :fire:

The by paypal provided script

  1. doesnt work with native ShadowDOM, so you need to force the ShadyDOM polyfill
  2. needs to be loaded outside of ShadyDOM

The [open paypal issue](https://github.com/paypal/paypal-checkout/issues/353) for reference.

### Your resulting `index.html`

````html
<script>
  window.customElements = window.customElements || {};
  window.customElements.forcePolyfill = true;
  window.ShadyDOM = {force: true};
</script>
<script src="/bower_components/webcomponentsjs/webcomponents-loader.js"></script>
````

## Components

### \<paypal-button\>

````html
<paypal-button
  sandbox
  sandbox-id="my-id"
  amount="1.00"
></paypal-button>
````

## Development

```bash
# Get dependencies
$ npm install

# Demo site
$ npm start

# Run tests
$ npm test
```
