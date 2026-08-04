# Iterable (iterable)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Iterable is an AI customer engagement platform that powers unified cross-channel marketing experiences and empowers marketers to create, optimize, and measure relevant interactions across email, push, SMS, in-app, and web channels. Their developer platform provides REST APIs, export APIs, AsyncAPI webhooks, and native SDKs for web, iOS, Android, and React Native.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/iterable/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/iterable/refs/heads/main/apis.yml)

## Tags

- Cross-Channel Messaging
- Customer Engagement
- Email
- Marketing Automation
- Push Notifications
- SMS

## Timestamps

- **Created:** 2026-03-20
- **Modified:** 2026-05-19

## APIs

### Iterable REST API

The Iterable REST API provides programmatic access to the Iterable cross-channel marketing automation platform. It exposes endpoints for managing users, campaigns, lists, events, commerce tracking, catalogs, channels, templates, experiments, workflows, and message delivery across email, push, SMS, and in-app channels. The API uses standard HTTP methods, JSON request and response bodies, and supports authentication via API keys or JWT-enabled keys.

- **Human URL:** [https://api.iterable.com/api/docs](https://api.iterable.com/api/docs)
- **Base URL:** `https://api.iterable.com`

#### Tags

- Campaigns
- Cross-Channel Messaging
- Email
- Marketing Automation
- Push Notifications
- SMS
- Users

#### Properties

- [Documentation](https://api.iterable.com/api/docs)
- [OpenAPI](openapi/iterable-rest-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/iterable-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/iterable-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Iterable Export API

The Iterable Export API enables developers to extract data from Iterable projects for analytics, reporting, and data warehousing purposes. It provides asynchronous export endpoints that allow bulk retrieval of user data, event data, campaign metrics, and message engagement information. The export endpoints support filtering by date ranges and other criteria, making it possible to build custom reporting pipelines and synchronize Iterable data with external business intelligence tools.

- **Human URL:** [https://support.iterable.com/hc/en-us/articles/204780579-Iterable-API-Endpoints-and-Sample-Payloads](https://support.iterable.com/hc/en-us/articles/204780579-Iterable-API-Endpoints-and-Sample-Payloads)
- **Base URL:** `https://api.iterable.com`

#### Tags

- Analytics
- Data Export
- Marketing Data
- Reporting

#### Properties

- [Documentation](https://support.iterable.com/hc/en-us/articles/204780579-Iterable-API-Endpoints-and-Sample-Payloads)
- [OpenAPI](openapi/iterable-export-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/iterable-export-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/iterable-export-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Iterable Web SDK

The Iterable Web SDK enables developers to integrate Iterable's marketing automation capabilities directly into JavaScript and Node.js applications. It provides functions for tracking user events, managing user profiles, displaying in-app messages, and handling web push notifications.

- **Human URL:** [https://github.com/Iterable/iterable-web-sdk](https://github.com/Iterable/iterable-web-sdk)
- **Base URL:** `https://api.example.com`

#### Tags

- In-App Messaging
- JavaScript
- SDK
- User Tracking
- Web

#### Properties

- [Documentation](https://github.com/Iterable/iterable-web-sdk)
- [Postman Collection](collections/iterable-export-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/iterable-export-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/iterable-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/iterable-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Iterable iOS SDK

The Iterable iOS SDK allows developers to integrate Iterable's marketing automation features into native iOS applications built with Swift or Objective-C. It supports push notifications, in-app messages, deep links, and Mobile Inbox functionality. The SDK can be installed via Swift Package Manager, CocoaPods, or Carthage, and supports iOS 10 and higher. It enables mobile apps to track user events, display targeted in-app content, and participate in Iterable's cross-channel marketing campaigns.

- **Human URL:** [https://support.iterable.com/hc/en-us/articles/360035018152-Iterable-s-iOS-SDK](https://support.iterable.com/hc/en-us/articles/360035018152-Iterable-s-iOS-SDK)
- **Base URL:** `https://api.example.com`

#### Tags

- In-App Messaging
- iOS
- Mobile
- Push Notifications
- SDK
- Swift

#### Properties

- [Documentation](https://support.iterable.com/hc/en-us/articles/360035018152-Iterable-s-iOS-SDK)
- [Postman Collection](collections/iterable-export-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/iterable-export-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/iterable-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/iterable-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Iterable Android SDK

The Iterable Android SDK provides native integration between Android applications and the Iterable marketing automation platform. It supports push notifications, in-app messages, deep links, and Mobile Inbox features. The open-source SDK enables Android apps to track user events, manage user profiles, render in-app content, and connect with Iterable's cross-channel campaign orchestration. Developers can use it to deliver personalized marketing experiences within their Android applications.

- **Human URL:** [https://support.iterable.com/hc/en-us/articles/360028925511-Overview-of-Iterable-s-iOS-and-Android-SDKs](https://support.iterable.com/hc/en-us/articles/360028925511-Overview-of-Iterable-s-iOS-and-Android-SDKs)
- **Base URL:** `https://api.example.com`

#### Tags

- Android
- In-App Messaging
- Mobile
- Push Notifications
- SDK

#### Properties

- [Documentation](https://support.iterable.com/hc/en-us/articles/360028925511-Overview-of-Iterable-s-iOS-and-Android-SDKs)
- [Postman Collection](collections/iterable-export-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/iterable-export-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/iterable-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/iterable-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Iterable React Native SDK

The Iterable React Native SDK enables developers to integrate Iterable's marketing automation capabilities into cross-platform mobile applications built with React Native. It wraps Iterable's native iOS and Android SDKs and supports both JavaScript and TypeScript. The SDK provides access to push notifications, in-app messages, Mobile Inbox, user event tracking, and deep linking.

- **Human URL:** [https://support.iterable.com/hc/en-us/articles/360045714072-Overview-of-Iterable-s-React-Native-SDK](https://support.iterable.com/hc/en-us/articles/360045714072-Overview-of-Iterable-s-React-Native-SDK)
- **Base URL:** `https://api.example.com`

#### Tags

- Cross-Platform
- JavaScript
- Mobile
- React Native
- SDK

#### Properties

- [Documentation](https://support.iterable.com/hc/en-us/articles/360045714072-Overview-of-Iterable-s-React-Native-SDK)
- [Postman Collection](collections/iterable-export-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/iterable-export-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/iterable-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/iterable-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/iterable)
- [AsyncAPI](asyncapi/iterable-system-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [JSON-LD](json-ld/iterable-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [JSON Schema](json-schema/iterable-user-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/iterable-campaign-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/iterable-event-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/iterable-commerce-item-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Website](https://iterable.com/)
- [Documentation](https://api.iterable.com/api/docs)
- [Support](https://support.iterable.com/hc/en-us)
- [Blog](https://iterable.com/blog/)
- [Login](https://app.iterable.com/login)
- [Privacy Policy](https://iterable.com/trust/privacy-policy/)
- [Terms of Service](https://iterable.com/trust/terms-of-service/)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
