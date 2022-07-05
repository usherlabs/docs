# The Campaign Object

A Campaign on Usher can be represented as JSON Object.&#x20;

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
        "limit": 250000
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
}
```
