---
title: Bitdefender
sidebarTitle: Bitdefender
---

API configuration: `bitdefender`

## Features

| Features | Status |
| - | - |
| [Auth (Basic)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the community.

## Getting started

-   [Bitdefender basic auth related docs](https://www.bitdefender.com/business/support/en/77209-125277-public-api.html#UUID-2a74c3b5-6159-831d-4f8a-ca42797ce3b0_section-idm4640170076361632655245645786)
-   [Generate a Bitdefender API key](https://www.bitdefender.com/business/support/en/77209-125277-public-api.html#UUID-2a74c3b5-6159-831d-4f8a-ca42797ce3b0_section-idm4640169987334432655171029621)
-   [Bitdefender API requests](https://www.bitdefender.com/business/support/en/77209-125277-public-api.html#UUID-2a74c3b5-6159-831d-4f8a-ca42797ce3b0_section-idm4538086884761632655021901068)

Do you need help? Please check this link.

## API gotchas

- Bitdefender uses `Basic` authentication mode to access different endpoints. Provide your `API key` as the Username value and leave the password field empty.
- When creating a new connection, you will need to add the `ACCESS_URL`, which will serve as your API base URL. To locate this field, click on your username in the upper-right corner of the console and select My Account. Then, navigate to the Control Center API section, where you will find an `Access URL` field.
- Bitdefender enforces different rate limits for different API endpoints and methods. For more details, check [Bitdefender rate limits](https://www.bitdefender.com/business/support/en/77209-394430-api-rate-limits.html)

Add Getting Started links and Gotchas by editing this page.

