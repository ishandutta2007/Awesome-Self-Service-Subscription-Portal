# Awesome-Self-Service-Subscription-Portal

# Awesome Self-Service Subscription Portal

> A curated list of top Self-Service Subscription Portal platforms — both SaaS/Hosted commercial solutions and open-source alternatives for letting customers manage their own billing, subscriptions, and payment methods without support intervention.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Chargebee Self-Serve Portal](#chargebee-self-serve-portal)
  - [Stripe Customer Portal](#stripe-customer-portal)
  - [Recurly Hosted Account Management](#recurly-hosted-account-management)
  - [Lago Customer Portal](#lago-customer-portal)
  - [UniBee User Portal](#unibee-user-portal)
- [Open-Source Software](#-open-source-software)
  - [stapel-billing](#stapel-billing)
  - [Kill Bill Kaui](#kill-bill-kaui)
  - [pnlcs (WHMCS Alternative)](#pnlcs-whmcs-alternative)
  - [Entando Customer Portal](#entando-customer-portal)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Self-Service Subscription Portal platforms. These are not open-source but are included as reference points for feature comparison.

### Chargebee Self-Serve Portal
**Type:** Embeddable subscription management portal
Chargebee's Self-Serve Portal lets customers manage their accounts and subscriptions without support intervention. Customers can view/edit account details, view/download invoices, view/edit subscription details, manage payment methods, edit billing/shipping addresses, and cancel/reactivate subscriptions [citation:2]. A key differentiator is that the portal can be **opened inside your app as a modal** rather than redirecting to a separate page, using Chargebee.js [citation:2][citation:8]. For teams wanting granular control, individual **widgets** (subscription details, payment methods, billing history, addresses, account info) can be embedded directly into the app layout via API-based integration [citation:2]. SSO is supported for authenticating users into the portal [citation:2].
**Best for:** Teams wanting a customizable, embeddable portal that keeps customers within their application while offloading routine billing self-service.

### Stripe Customer Portal
**Type:** Hosted billing management portal
Stripe's Customer Portal lets customers update billing information (including tax IDs), update payment methods, update subscriptions, cancel immediately or at period end, and view/download/pay invoices [citation:3]. It includes **cancellation deflection**—offering coupons when customers attempt to cancel—and localization to the customer's preferred language [citation:3]. Branding is customizable with icon, logo, colors, and business information [citation:3]. **Important limitations:** Customers cannot update subscriptions that use multiple products, metered billing, or unsupported payment methods; subscription schedules block updates; and only up to 10 products can be offered for plan changes [citation:3]. Portal sessions expire after 5 minutes (or 1 hour after activity) [citation:3].
**Best for:** Stripe-native teams wanting a zero-development hosted portal with built-in retention features, accepting the platform's configuration constraints.

### Recurly Hosted Account Management
**Type:** White-labeled hosted subscription pages
Recurly provides pre-built hosted pages or a fully custom experience via API, giving subscribers a consistent branded portal [citation:4][citation:10]. Customers can view account status, modify billing details, retrieve past invoices, change payment methods, cancel subscriptions, and redeem gift cards [citation:4]. Access is controlled via **unique secret tokens** with configurable access levels: **Account Login** (full portal with registration) or **Guest View Only** (limited details for hosted invoices) [citation:4][citation:10]. Online payments for manual invoices (credit card, PayPal, Amazon, ACH) are available on Professional/Elite plans, with an opt-in checkbox to use the selected method for future renewals [citation:4].
**Best for:** Teams wanting white-labeled hosted pages with flexible access controls and token-based security, available on all Recurly plans.

### Lago Customer Portal
**Type:** Embeddable billing portal for open-source billing
Lago provides a Customer Portal that shares billing information with end customers. It can be generated via API and displayed in your application using an iframe, with a URL pattern of `/customers/:external_customer_id/portal_url` [citation:5]. Lago is an open-source metering and usage-based billing platform, and the customer portal is a feature within that ecosystem [citation:11].
**Best for:** Teams already using Lago for billing wanting a built-in customer portal rather than building one from scratch.

### UniBee User Portal
**Type:** Open-source billing user portal
UniBee maintains a dedicated `unibee-user-portal` repository (TypeScript, AGPL-3.0) as the customer-facing portal for its open-source recurring billing system [citation:13]. The project is actively updated (last update January 2026) [citation:13]. This is part of the broader UniBee gateway-agnostic billing platform.
**Best for:** Teams using UniBee for billing wanting its native user-facing portal component.

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
