---
cover: >-
  https://images.unsplash.com/photo-1460186136353-977e9d6085a1?crop=entropy&cs=tinysrgb&fm=jpg&ixid=MnwxOTcwMjR8MHwxfHNlYXJjaHwxfHxzYXRlbGxpdGV8ZW58MHx8fHwxNjU2OTI4OTE4&ixlib=rb-1.2.1&q=80
coverY: 0
---

# What is Usher Satellite?

🛰  **Usher Satellite is a Javascript library used by Web3 Brands to track conversions.**

Conversions can be tracked just about anywhere inside of a Javascript-enabled Web App or Browser Extension.

Examples include, when:

* a user stakes cryptocurrency
* a user registers a new account
* a user deposits funds into their Crypto wallet

We've prescribed the name "Satellite" to the Library because of the way it works.

When a conversion event is submitted via the JS API, an iFrame (_ie. the Satellite_) is rendered to the Web App. The iFrame behaves as a bridge between Usher and the Web App.

The iFrame securely reads from the browser storage (such as LocalStorage and Cookies) and then processes this data against the Usher Network.

This processing involves ensuring that the Referred User has indeed originated from an Usher Invite Link and has therefore passed through the security measures in place for Referred Users, before being distributed to the Usher Network for Conversion management.

To get started, visit the [Installation](installation.md) guide.

To view the Satellite JS Source Code, visit the [Github Repository](https://github.com/usherlabs/satellite).
