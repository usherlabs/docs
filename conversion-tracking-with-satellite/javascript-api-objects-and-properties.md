# Javascript API: Objects & Properties

This page details the possible attributes that can be used when [Installing the Usher Satellite JS library](installation.md)

### Conversion

These parameters are provided to the `convert` method.

For more detailed information, check [the typescript definition of this object](https://ts-docs.satellite.usher.so/types/types.conversion).

<table><thead><tr><th>Object Property Name/Key</th><th>Type</th><th>Description</th><th data-type="checkbox" data-hidden>Required</th></tr></thead><tbody><tr><td><strong>id</strong></td><td>string</td><td>The Identifer of the Campaign acquired during Campaign creation</td><td>true</td></tr><tr><td><strong>chain</strong></td><td>string</td><td>The blockchain identifer acquired during Campaign creation</td><td>true</td></tr><tr><td><strong>eventId</strong></td><td>integer</td><td>The identifier of the Campaign Event defined during Campaign creation. <br>This is usually <strong><code>0</code></strong> for single event Campaigns. <br>Where different rewards can be distributed at different points throughout the Referred User journey, this can <strong><code>0</code></strong> to <strong><code>X</code></strong>.</td><td>true</td></tr><tr><td><strong>nativeId</strong></td><td>string</td><td>An identifier of the User native to the Web3 Brand's Web App. <br>This can be a Web3 Wallet Address used to authorise into the Web3 Brand's Web App.<br><br>By default, assigning submitting a Native ID is a way to ensure that the Referred User can only ever be converted once.<br>Combining this with a Campaign Event <strong>Native Limit</strong> can deliver an experience where a Referred User can continue to convert until their conversions have <strong>committed</strong> enough to have reached the <strong>Native Limit</strong>.</td><td>false</td></tr><tr><td><strong>commit</strong></td><td>integer</td><td>An arbitrary value that indicates how much of the Event this Conversion consumes for the Referred (Native) User and/or whether to Event Reward Rate should be calculated.<br>This parameter is only necessary where the Event has a corresponding <strong>Native Limit</strong> or where rewards are issued <strong>Per Commit.</strong></td><td>false</td></tr><tr><td><strong>metadata</strong></td><td>object</td><td>An arbitrary record of key/values that the Brand can use.</td><td>false</td></tr><tr><td><strong>metadata.amount</strong></td><td>integer</td><td>The only <strong>special</strong> key in the <code>metadata</code> <strong></strong> property is the <code>amount</code> key.<br>This is the amount of value to be used when calculating a <strong>percentage-</strong>based reward.<br>ie. For DeFi or Commerce applications that reward commissions as percentage-based calculations.</td><td>false</td></tr></tbody></table>



### Tracked Conversion

This parameter is received when using the `onConversion` method.

For more detailed information, check [the typescript definition of this object](https://ts-docs.satellite.usher.so/types/types.conversionresponse).

<table><thead><tr><th>Object Property Name/Key</th><th>Type</th><th>Description</th><th data-type="checkbox" data-hidden>Required</th></tr></thead><tbody><tr><td><strong>conversion</strong></td><td>Conversion</td><td>The Conversion Payload as per the above.</td><td>true</td></tr><tr><td><strong>did</strong></td><td>string</td><td>The W3C compatible Decentralized Identifier that is created and/or used by the Referred User to submit the Conversion.</td><td>true</td></tr><tr><td><strong>response.conversion</strong></td><td>string</td><td>The ID of the indexed Conversion</td><td>true</td></tr><tr><td><strong>response.partnership</strong></td><td>string</td><td>The ID of the Partnership that the  Conversion was indexed in relation to.</td><td>false</td></tr></tbody></table>

