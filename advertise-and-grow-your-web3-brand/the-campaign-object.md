# The Campaign Object

A Campaign on Usher can be represented as a JSON Object.&#x20;

Pieces of the object are distributed across different storage mechanisms to deliver on the immutability of Campaign Terms but mutability of Campaign Details and Brand/Advertiser Profile.

Once fully processed, a Campaign in its raw form, looks like this:

```json
{
    "id": "ida4Pebl2uULdI_rN8waEw65mVH9uIFTY1JyeZt1PBM",
    "chain": "arweave",
    "owner": "ksFTLgrwQGtNrhRz6MWyd3a4lvK1Oh-QF1HYcEeeFVk",
    "events": [
      {
        "strategy": "flat",
        "rate": 0.1,
        "nativeLimit": 250000,
        "perCommit": 1,
        "description": "files are uploaded"
      }
    ],
    "reward": {
      "name": "Arweave",
      "ticker": "AR",
      "type": "token",
      "limit": 3000
    },
    "conflict_strategy": "PASSTHROUGH",
    "details": {
      "destination_url": "https://app.ardrive.io/#/sign-in?ref=usher",
      "name": "ArDrive Referral Program",
      "description": "Refer users to ArDrive and earn when files are uploaded.",
      "image": "https://ardrive.io/wp-content/uploads/2021/07/Gallery-Angle-PS3000-scaled.jpg",
      "external_link": "https://ardrive.io/"
    },
    "advertiser": {
      "name": "ArDrive",
      "icon": "https://ardrive.io/wp-content/uploads/2021/06/AD-LOGO-PS1600-210x79.png",
      "description": "Upload files forever!",
      "external_link": "https://ardrive.io/",
      "twitter": "https://twitter.com/ardriveapp"
    },
    "disable_verification": false,
    "unlisted": false,
    "whitelist": null
}
```

All properties within the Campaign Object except for `details` and `advertiser` are stored immutably on the compute blockchain that the Brand decides to conduct the Partnership Program on.

`details` and `advertiser` are stored on the Ceramic Network, where data is mutable and write-access is owned by the Brand.

### Campaign Object Properties

<table><thead><tr><th>Object Property Name/Key</th><th>Type</th><th>Description</th><th data-type="checkbox" data-hidden>Required</th></tr></thead><tbody><tr><td><strong>id</strong></td><td>string</td><td>The identifier of the Campaign. This can be an ID within a Smart Contract or an Blockchain Transaction Address, depending on the <code>chain</code></td><td>true</td></tr><tr><td><strong>chain</strong></td><td>string</td><td>The blockchain identifer. ie. <code>arweave</code> , <code>ethereum</code>, <code>polygon</code></td><td>true</td></tr><tr><td><strong>owner</strong></td><td>string</td><td>The Wallet Address of the Brand/Advertiser</td><td>false</td></tr><tr><td><strong>events</strong></td><td>array</td><td>An array of Conversion Events. These Events represent points throughout the Referred User journey at which Conversions are Tracked</td><td>false</td></tr><tr><td><strong>events[].strategy</strong></td><td>string</td><td><code>flat</code> or <code>percentage</code> reward strategy for the event</td><td>false</td></tr><tr><td><strong>events[].rate</strong></td><td>float</td><td>Reward rate for the event. <br>For the <code>flat</code> strategy, this rate is flat amount of tokens rewarded to partners.<br>For the <code>percentage</code> strategy, this rate is a multiplier, multiplied by the <code>metadata.amount</code> submitted in the <a href="../conversion-tracking-with-satellite/javascript-api-objects-and-properties.md">Conversion Parameter</a></td><td>false</td></tr><tr><td><strong>events[].nativeLimit</strong></td><td>integer</td><td>An arbitrary value that limits the conversions that can be processed for this given event for the referred/native user.<br>Where a <code>Conversion.nativeId</code> is provided, rather than restricting conversions to 1 per referred/native user, the Referred User can continue triggering conversions until the sum of  all <code>Conversion.commit</code> values meets this <code>nativeLimit</code></td><td>false</td></tr><tr><td><strong>events[].perCommit</strong></td><td>integer</td><td>If no reward <code>perCommit</code> is defined, the behaviour is standard (ie. X reward rate per Conversion).<br>Otherwise, the reward amount can be relative to the <code>Conversion.commit</code> value, such that <br><code>reward = rate * (commit / perCommit)</code></td><td>false</td></tr><tr><td><strong>events[].description</strong></td><td>string</td><td>A description for <strong>when</strong> the event will trigger.<br><br>The word "when" is prepended to this description in the Usher Partner App UI</td><td>false</td></tr><tr><td><strong>reward.name</strong></td><td>string</td><td>The name of the rewarded token.<br>ie. "Ether", "Arweave", "My Cool NFT"</td><td>false</td></tr><tr><td><strong>reward.ticker</strong></td><td>string</td><td>The ticker for the rewarded token.<br>ie. "ETH", "AR", "MYCNFT"</td><td>false</td></tr><tr><td><strong>reward.type</strong></td><td>string</td><td>The type of the token rewared to Partners.<br>This is an enumerator with values: <code>token</code>, <code>nft</code>, or <code>pst</code></td><td>false</td></tr><tr><td><strong>reward.limit</strong></td><td>integer</td><td>A limit on the rewards for the entire campaign. When the amount of claimed rewards reaches this limit, the Campaign is considered complete.</td><td>false</td></tr><tr><td><strong>conflict_strategy</strong></td><td>string</td><td><code>PASSTHROUGH</code> or <code>OVERWRITE</code><br>Determines how the referral should behave when two Partners refer the same user prior to a tracked conversion.<br><code>PASSTHROUGH</code> is default, and ensures that the first Invite Link used takes precedence.<br><code>OVERWRITE</code> is optional and ensures that the last Invite Link used takes precedence. </td><td>false</td></tr><tr><td><strong>details.destination_url</strong></td><td>string</td><td>The URL that Campaign Partners will redirect users to.</td><td>false</td></tr><tr><td><strong>details.name</strong></td><td>string</td><td>Name for the Campaign to be recognisable by Partners</td><td>false</td></tr><tr><td><strong>details.description</strong></td><td>string</td><td>A description for the Campaign detailing when and how users are converted once the <code>destination_url</code> is reached</td><td>false</td></tr><tr><td><strong>details.image</strong></td><td>string</td><td>A hosted image URL to further enhance recognisability of the Campaign</td><td>false</td></tr><tr><td><strong>details.external_link</strong></td><td>string</td><td>A URL Partners can visit to receive more information about the Campaign. Can be a landing page promoting the partnership program</td><td>false</td></tr><tr><td><strong>advertiser.name</strong></td><td>string</td><td>Name of the Advertiser</td><td>false</td></tr><tr><td><strong>advertiser.icon</strong></td><td>string</td><td>A hosted image URL of the Advertiser's Brand Icon</td><td>false</td></tr><tr><td><strong>advertiser.description</strong></td><td>string</td><td>A description of the Advertiser and their related services or propositions</td><td>false</td></tr><tr><td><strong>advertiser.external_link</strong></td><td>string</td><td>A URL that Partners can visit to learn more about the Advertiser</td><td>false</td></tr><tr><td><strong>advertiser.twitter</strong></td><td>string</td><td>A Twitter URL that Partners can visit to learn more and get updates from the Advertiser</td><td>false</td></tr><tr><td><strong>disable_verification</strong></td><td>boolean</td><td>If <code>true</code>, Personhood Verification will NOT be required for Partners to start referring users and earning rewards.<br>Personhood Verification is generally recommended to be active for Campaigns.<br><a href="../security/personhood-verification.md">Learn more on whether your Campaign should include this security measure</a>.</td><td>false</td></tr><tr><td><strong>unlisted</strong></td><td>boolean</td><td>Determines whether the Campaign will show on the Usher Explore Page.<br>Partnership Programs that wish to remain private, and/or include a Whitelist of Partners can opt to set this to <code>true</code></td><td>false</td></tr><tr><td><strong>whitelist.partners</strong></td><td>string[]</td><td>An array of Partner Identifiers.<br>By default, Campaigns will not include the Whitelist feature.</td><td>false</td></tr><tr><td><strong>whitelist.url</strong></td><td>string</td><td>A URL where a Form or other form of data collection is hosted. Partners can use this URL to submit their application to participate in the Partner program.</td><td>false</td></tr></tbody></table>

