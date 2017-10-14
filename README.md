# Polymer 2 wrapper for the Paypal Express Checkout button

[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/morbidick/paypal-express-checkout)

Polymer 2 paypal button. Please use with caution, there are multiple restrictions with the paypal library!

## Restrictions

To work around [paypals issue with ShadowDOM](https://github.com/paypal/paypal-checkout/issues/353) this element opens the paypal button in a new window. This takes a little bit of the "express" out of the checkout since the user has to click two times.

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
