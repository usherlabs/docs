# Supporting Partners

### **Dashboard**

Each partner will be able to log into Usher to view their activity, commissioned rewards and claim rewards.

Inside of this User Interface, partners will also be provided with a unique Usher Invite Link once they have engaged your Campaign.

The Link can be placed on the Partner's Website, Shared on Social Media, etc.

As a Brand, you can decide where this Invite Link will redirect to.

The destination of a Campaign's Invite Links is configured when setting up the Campaign as is referred to as the Destination URL.

This Destination URL is mutable so that changes to the Brand's web application or user experience will not require an entirely new Campaign.

Ideally, this Destination URL should redirect to your Web Application, where the **🛰  UsherJS Library** should be installed to track Conversions.

![Example Campaign for ArDrive](<../.gitbook/assets/Screen Shot 2022-07-05 at 2.39.07 am.png>)

### Conversions

The Usher Invite Link incorporates security mechanisms to prevent an outcome where the Referred User is a Bot operated by a Bad Actor.

To verify that all Conversions originated from a referral where security measures were employed, each conversion must include a cryptographic signature owned by Usher (the security provider) to be considered **validated.**

Validated conversions are then syndicated to Smart Contracts on the respective compute blockchains where the Campaign and Reward allocations wallets are managed.

{% hint style="info" %}
This syndication process is designed to be handled by a decentralised network, however, at launch, there will only be a single validator for this network operated by Usher.
{% endhint %}

### Claims

Now that Rewards are allocated to Partner wallets within the Usher Smart Contract, Partners can submit withdrawal transactions directly to Smart Contract to claim their rewards.

{% hint style="warning" %}
There may be circumstances where a Smart Contract is not developed (_yet_) for a given Blockchain preventing the Brand from funding their Campaign directly with a Smart Contract.

In this case, Usher will work closely with Brands to determine a interim solution. Brands are also entitled to wait until a Smart Contract is developed that supports their desired Blockchain.
{% endhint %}
