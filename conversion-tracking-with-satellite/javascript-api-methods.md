# Javascript API: Methods

Loading the Usher Satellite JavaScript library provides a JavaScript object that responds to a few methods. These allow you to execute on conversions, as well as listen for when conversions are successfully processed.

### `Usher('convert', conversionParams)`

To submit a conversion, you must provide parameters that identify the Campaign you are creating a conversion for, as well as provide additional data that affects the way conversions are processed.

```javascript
Usher('convert', {
	id: "ida4Pebl2uULdI_rN8waEw65mVH9uIFTY1JyeZt1PBM",
	chain: "arweave",
	eventId: 0,
	commit: 10,
	nativeId: "ksFTLgrwQGtNrhRz6MWyd3a4lvK1Oh-QF1HYcEeeFVk",
	metadata: {
		amount: 1000,
		convertType: "defi",
		action: "stake",
	}
});
```

### `Usher('onConversion')`

This method allows you to register a function that is executed after the Conversion has been successfully indexed by the Usher Network.

This could be useful if you are tracking multiple conversions on the same page for different events, or if you are tracking an event prior to a page change and would like to ensure the conversion has been successfully processed.

```javascript
Usher('onConversion', (trackedConversion) => {
    console.log(trackedConversion)
})
```

### `Usher('onLoad')`

This method allows you to register a function that is executed when the Satellite iFrame has loaded, _for whatever reason_.

```javascript
Usher('onLoad', () => {
    // do something to HTML?
})
```
