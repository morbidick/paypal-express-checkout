# Polymer 2 wrapper for the Paypal Express Checkout button

[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/morbidick/paypal-express-checkout)

## Restrictions

To work around [paypals issue with ShadowDOM](https://github.com/paypal/paypal-checkout/issues/353) this element opens the paypal button in a new window. This takes a little bit of the "express" out of the checkout since the user has to click two times.

### Polymer build

To build include the paypal.html in your `polymer.json`.

```json
"extraDependencies": [
  "bower_components/paypal-express-checkout/paypal.html"
]
```

## Components

### \<paypal-button\>

````html
<paypal-button
  sandbox
  sandbox-id="my-id"
  amount="1.00"
  reference="your-payment-reference"
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
