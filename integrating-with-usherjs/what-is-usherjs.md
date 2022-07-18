---
cover: >-
  https://images.unsplash.com/photo-1588515603068-adb330f26e92?crop=entropy&cs=tinysrgb&fm=jpg&ixid=MnwxOTcwMjR8MHwxfHNlYXJjaHw3fHx0b29sa2l0fGVufDB8fHx8MTY1ODE2NDM4MA&ixlib=rb-1.2.1&q=80
coverY: 332.53046824887747
---

# What is UsherJS?

**UsherJS is a Javascript library used by Web3 Brands to manage and track referrals & conversions.**

Conversions can be tracked just about anywhere inside of a Javascript-enabled Web App or Browser Extension.

Examples include, when:

* a user stakes cryptocurrency
* a user registers a new account
* a user deposits funds into their Crypto wallet

**How it works**

When an Usher Invite Link is used by an end-user, a Referral Token is created and appended as a Query Parameter `_ushrt` to the Campaign's Destination URL.

This Destination URL can be a Landing Page or the dApp where Conversions are executed.

UsherJS is used to automatically parse the website URL and fetch this Referral Token before saving/caching it as first-party data to the browser storage.

When a conversion method is executed using the JS library, this saved Referral Token is used to fetch a Signature from the Usher Partner Network before being syndicated to the Usher Validator Network where it is processed as a Conversion.

{% hint style="info" %}
The Validator Network is currently in development. In the meantime, this signed referral token is sent directly to Usher where conversions are validated before resulting in Partner Reward allocations.
{% endhint %}

The Usher Network Signature Verification process ensures that the Referred User has indeed originated from an Usher Invite Link and has passed through the necessary security measures required for Referred Users, such as [Bot Prevention](../security/bot-prevention.md).&#x20;

To get started, visit the [Installation](installation.md) guide.

To view the UsherJS Source Code, visit the [Github Repository](https://github.com/usherlabs/satellite).
