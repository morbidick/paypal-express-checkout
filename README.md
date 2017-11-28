# Polymer 2 wrapper for the Paypal Express Checkout button

[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/morbidick/paypal-express-checkout)

<p align="center">
  <img src="demo/flow.gif" alt="Button flow demo"/>
</p>

## Restrictions

To work around [paypals issue with ShadowDOM](https://github.com/paypal/paypal-checkout/issues/353) this element opens the paypal button in a new window. This takes a little bit of the "express" out of the checkout since the user has [to click two times](https://github.com/paypal/paypal-checkout/issues/287).

### Polymer build

To build include the paypal.html in your `polymer.json`.

```json
"extraDependencies": [
  "bower_components/paypal-express-checkout/paypal.html"
]
```

## Components

### \<paypal-button-express\>

````html
<paypal-button-express
  sandbox
  sandbox-id="my-id"
  amount="1.00"
  reference="your-payment-reference"
></paypal-button-express>
````

#### How does it work

  * a click on the component or calling `.open()` opens a new window and renders the button there
  * All PayPal events get send back via a postMessage bridge and fire the corresponding events on the component
  * In case the messages dont get acknowledged (for example the user closed the original app tab) the page redirects back to the app and sets url params according to the paypal response
  * In case the user also closed the button window or paypal cant find the reference (for example in tor browser) the paypal redirect url has been set to the original app url
  * On render the web component analyses the page params to detect one of the cases above and fires the corresponding events.

### \<paypal-button-form\>

Using the (older) [paypal form api](https://developer.paypal.com/docs/classic/paypal-payments-standard/integration-guide/formbasics/), an easier checkout can be accomplished. To get notified about payments you have to set `notify` to an [IPN](https://developer.paypal.com/docs/classic/products/instant-payment-notification/) url on your site.

````html
<paypal-button-form
  paypal-id="id@example.org"
  amount="1.00"
  reference="your-payment-reference"
></paypal-button-form>
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
