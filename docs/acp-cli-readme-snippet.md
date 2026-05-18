# Suggested ACP CLI README Snippet

Recommended location: after the `Agent Card` section in the ACP CLI README, or inside a future `Recipes` / `Examples` section.

```markdown
#### Recipe: Paid Web Subscription Checkout

Agent Email and Agent Card can be composed with browser automation to let an ACP agent subscribe to paid web services while keeping identity, receipts, payment status, and verification machine-readable through `acp-cli`.

See the demo repo:

https://github.com/Virtual-Protocol/acp-cli-demos/tree/main/demos/paid-substack-subscription

The demo covers:

- determining the active agent email with `acp email whoami`
- issuing a bounded single-use card with `acp card issue`
- retrieving 3DS codes with `acp card 3ds` when required
- checking captured payment status with `acp card get`
- finding the receipt with `acp email search` and `acp email thread`
- verifying that paid access changed after checkout

Because this is a live-money flow, agents should only issue cards and click final checkout buttons when the user has explicitly authorized the merchant, plan, billing cadence, and maximum amount.
```

Keep the detailed checkout instructions in this demo repo. The ACP CLI README should stay focused on showing that `acp email` and `acp card` compose into real-world commerce workflows.
