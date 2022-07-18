# Instantiating UsherJS

### `Usher(config?)`

Use `Usher(config?)` to create an instance of the **Usher object**. The Usher object is your entrypoint to the rest of the UsherJS SDK.

**Method Parameters**

| Option             | Type          | Default       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------------------ | ------------- | ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `staging`          | boolean       | false         | A flag to indicate whether to use a [Staging Environment](https://app.staging.usher.so/) for Testing/Integration Purposes, or the [Live Environment](https://app.usher.so/)                                                                                                                                                                                                                                                                    |
| `conflictStrategy` | string (enum) | "passthrough" | An enum to indicate how to handle conflicting tokens for the same campaign. The option can be either be `"passthrough"` or `"overwrite"`. In the "passthrough" scenario, referal tokens are backlogged for the same campaign. Any previously tracked referral token is saved to the browser until it expires or is used. In the "overwrite", any new referral token that is saved overwrites other saved tokens relative to the same campaign. |
