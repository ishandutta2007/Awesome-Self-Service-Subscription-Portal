# Awesome Self-Service Subscription Portal

> A curated list of top Self-Service Subscription Portal platforms — both SaaS/Hosted commercial solutions and open-source alternatives for letting customers manage their own billing, subscriptions, and payment methods without support intervention.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
- [Open-Source Software](#-open-source-software)
  - [stapel-billing](#stapel-billing)
  - [Kill Bill Kaui](#kill-bill-kaui)
  - [pnlcs (WHMCS Alternative)](#pnlcs-whmcs-alternative)
  - [Entando Customer Portal](#entando-customer-portal)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Self-Service Subscription Portal platforms. These are not open-source but are included as reference points for feature comparison. Sorted in descending order by company size (valuation / revenue).

| Platform | Company Size (Valuation / Revenue) | Pricing | Free Tier / Free Trial Limits | Embeddable / Hosted | Key Capabilities |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **[Stripe Customer Portal](https://stripe.com/billing)** | $91.5B valuation (tender offer, 2025); $5.1B+ revenue (2024) | Pay-as-you-go: 0.7% on recurring billing volume (custom plans available; optional custom domain at $10/month) | Free in Test Mode with full sandbox access; 0.7% pay-as-you-go fee on live billing volume with no monthly base subscription fee | Hosted only (supports custom domains) | Self-service billing/payment management, tax ID updates, invoice history download, cancellation deflection flows with automatic discounts/coupons |
| **[Chargebee Self-Serve Portal](https://www.chargebee.com/)** | $3.5B valuation (Series H); $150M+ ARR | Starter Plan: $0/mo (up to $250k lifetime billing limit, then 0.75% overage); Performance Plan: $599/mo billed annually (up to $100k/mo billing, +0.75% overage) | Free forever on Starter Plan up to $250,000 in cumulative lifetime billing volume; free full-featured sandbox/test account | Both (in-app modal via Chargebee.js or modular embedded widgets) | In-app modal or granular widgets, account and plan switching, invoice download, payment method updates, SSO authentication |
| **[Recurly Hosted Account Management](https://recurly.com/)** | ~$100M–$200M est. valuation (majority acquired by Accel-KKR; ~$20M+ ARR) | Starter Plan: $249/mo + 0.9% of billing volume; All-Access Plan: Custom quote (typically $1M+ annual volume minimum) | 90-day free trial on Starter Plan with up to $40,000/mo included billing volume; full sandbox developer testing | Hosted (white-labeled pages or API) | White-labeled branded pages, token-based authentication (Account Login vs. Guest View), past invoice retrieval, payment method changes, gift card redemption |
| **[Lago Customer Portal](https://www.getlago.com/)** | $100M valuation ($22M total venture funding raised) | Open-Source Self-Hosted: $0/mo (AGPL-3.0); Lago Cloud / Premium: Custom quote based on event ingestion volume | Free forever self-hosted under AGPL-3.0 with complete core billing/metering engine; cloud proof-of-concept trial available via direct sales/demo request | Embeddable (iframe via `/customers/:id/portal_url`) | Embeddable iframe portal, real-time usage metering visibility, subscription management, automated invoice downloads, native API-generated access |
| **[UniBee User Portal](https://unibee.dev/)** | Early-stage private / unfunded (~$2M–$5M est.) | Open-Source Self-Hosted: $0/mo (AGPL-3.0); Cloud Starter: $99/mo; Cloud Business: $399/mo | Free forever self-hosted under AGPL-3.0; Cloud Starter & Business tiers include a free trial upon signup with full core billing and analytics features | Dedicated open-source user portal (`unibee-user-portal` web app) | Gateway-agnostic customer portal, recurring subscription overview, invoice retrieval, multi-currency support, zero revenue-share percentage fees |

---

## 🟩 Open-Source Software

Self-hosted, community-driven Self-Service Subscription Portal tools. The open-source ecosystem is **limited**—most projects are either billing platforms with portal components or niche alternatives rather than dedicated, standalone portals.

### stapel-billing
**Stack:** Python / Django | **License:** MIT
stapel-billing is a Django app providing payments and billing with per-user credit wallets, one-off credit packages, and recurring subscription plans [citation:1]. It includes **Stripe-backed checkout and a self-service customer portal**, idempotent webhooks, and a service-to-service debit endpoint [citation:1]. Part of the Stapel framework of composable Django apps, it can be deployed as a monolith or microservice. This is the most purpose-built open-source option for teams already on Django wanting an integrated portal rather than a separate billing platform.
**Best for:** Django teams wanting a billing component with a built-in self-service portal, deployable within their existing Python stack.

### Kill Bill Kaui
**Stack:** Java / Ruby (Kaui UI) | **License:** Apache-2.0 (Kill Bill) / Open Source (Kaui)
Kill Bill is a mature open-source subscription billing platform, and **Kaui** is its admin UI [citation:6][citation:12]. Kaui is a **back-office administrative interface** for managing tenants, accounts, subscriptions, invoices, and payments—not a customer-facing self-service portal [citation:6]. It handles authentication via Kill Bill's user management and is designed for operators, not end customers. For a customer-facing portal, Kill Bill does not include one out of the box; teams would need to build it using Kill Bill's APIs.
**Best for:** Teams wanting a proven open-source billing engine with a strong admin UI, accepting that the customer portal must be custom-built.

### pnlcs (WHMCS Alternative)
**Stack:** Laravel / PHP / MySQL | **License:** MIT
pnlcs is an open-source WHMCS alternative for hosting billing and client portal, covering invoicing, domains, SSL, tickets, reseller management, multi-language (30 locales), and 16 themes [citation:7]. While **specific to hosting/web services**, it provides a complete self-hosted client portal with billing workflows, making it a reference for how a customer-facing portal can be structured. It is not a generic subscription billing portal.
**Best for:** Hosting companies and web service providers wanting an open-source WHMCS replacement with an integrated client portal.

### Entando Customer Portal
**Stack:** Java / Kubernetes | **License:** Open Source
Entando's Customer Portal is a Kubernetes-native application integrated with **Jira Service Management** and Keycloak, providing role-based access control for user, customer, project, and subscription management [citation:14]. It is a reference implementation for building a customer portal on Entando's platform, not a standalone subscription billing portal. The portal connects to Jira for ticketing and uses Keycloak for identity.
**Best for:** Organizations on the Entando platform needing a customer portal reference architecture with Jira and Keycloak integration.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Hosted/Embeddable | Billing-Aware | Self-Hosted | Best For |
|----------|---------|-------|-------------------|---------------|-------------|----------|
| **Chargebee** | Proprietary | Cloud | Both (modal/widgets) | ✅ | ❌ | Embeddable in-app portal |
| **Stripe** | Proprietary | Cloud | Hosted only | ✅ | ❌ | Zero-dev hosted portal |
| **Recurly** | Proprietary | Cloud | Hosted (branded) | ✅ | ❌ | White-labeled hosted pages |
| **Lago** | AGPL-3.0 | Cloud/API | Embeddable (iframe) | ✅ | ✅ (API) | Lago billing users |
| **UniBee** | AGPL-3.0 | TypeScript | User portal | ✅ | ✅ | UniBee billing users |
| **stapel-billing** | MIT | Django | Portal included | ✅ | ✅ | Django billing + portal |
| **Kill Bill Kaui** | Apache/OSS | Java/Ruby | Admin only | ✅ | ✅ | Billing engine + admin UI |
| **pnlcs** | MIT | Laravel/PHP | Client portal | ✅ (Hosting) | ✅ | Hosting WHMCS alternative |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Self-Service Subscription Portal tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem for **dedicated customer-facing subscription portals** is very limited. Most open-source billing platforms (Kill Bill, Lago, UniBee) provide APIs or embedded portal components rather than a complete, standalone portal. **stapel-billing** is the most purpose-built option for Django teams wanting an integrated portal [citation:1]. For teams wanting full control, building a custom portal on top of an open-source billing API remains the most flexible path.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
