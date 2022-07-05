# Installation

To start submitting conversions to Usher, simply copy and paste the snippet below before the end of the Body tag on the page that you would like to execute the conversion.&#x20;

```html
<script src="https://cdn.jsdelivr.net/npm/@usher.so/js"></script>
```

If you are producing a JS bundle using Webpack, or some alternative, you can install the JS library directly into your application:

```shell
npm i @usher.so/js
```

or

```shell
yarn add @usher.so/js
```

The library can then be imported like so:

```javascript
import { Usher } from '@usher.so/js'
```
