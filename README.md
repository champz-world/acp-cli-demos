# ACP CLI Demos

This repo collects demos, skills, and prompts that show how agents can use [`acp-cli`](https://github.com/Virtual-Protocol/acp-cli) for real-world commerce workflows.

The first demo shows an ACP agent subscribing to a paid Substack using:

- ACP Agent Email for signup, receipts, OTPs, and account verification
- ACP Agent Card for bounded, single-use checkout payments
- `acp-cli` for identity, email, card issuance, payment status, 3DS, and receipt checks
- Browser automation for the merchant checkout page

## Demos

### Paid Substack Subscription

Path: [`demos/paid-substack-subscription`](demos/paid-substack-subscription)

This demo validates that an ACP agent can complete a paid newsletter checkout end-to-end, then verify the captured charge, receipt, and paid content access.

## Skills

### ACP Paid Subscription Checkout

Path: [`skills/acp-paid-subscription-checkout`](skills/acp-paid-subscription-checkout)

This is the reusable Codex skill behind the Substack demo. It is intentionally broader than Substack: it describes a bounded paid subscription checkout workflow using ACP identity, email, and card primitives.

Install locally:

```bash
mkdir -p ~/.codex/skills
cp -R skills/acp-paid-subscription-checkout ~/.codex/skills/
```

Invoke in Codex:

```text
Use $acp-paid-subscription-checkout to complete a bounded paid subscription checkout for my ACP agent and verify access.
```

## Safety Model

These demos can involve live payments. A checkout agent should only issue cards and click final paid checkout buttons when the user has explicitly authorized:

- merchant
- plan
- billing cadence
- maximum amount
- ACP agent email
- ACP agent card payment method

The agent must stop before paying if checkout details differ from the authorization.

Final outputs must redact full card numbers, CVVs, magic links, OTPs, and other sensitive payment details.

## Related

- [`acp-cli`](https://github.com/Virtual-Protocol/acp-cli)
- [`acp-node-v2`](https://github.com/Virtual-Protocol/acp-node-v2)
