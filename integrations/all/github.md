---
title: GitHub  
sidebarTitle: GitHub  
---

API configuration: [`github`](https://terapi.dev/providers.yaml), [`github-app`](https://terapi.dev/providers.yaml), [`github-app-oauth`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (OAuth + App)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | ✅ |

We can implement missing features in &lt;48h, just ask for it in the [community](#).

## Getting started

-   [Difference between OAuth Apps and GitHub Apps](https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/differences-between-github-apps-and-oauth-apps)
-   [How to register a GitHub App](https://docs.github.com/en/apps/creating-github-apps/registering-a-github-app/registering-a-github-app)
-   [How to register an OAuth App](https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/creating-an-oauth-app)
-   [List of GitHub App permissions](https://docs.github.com/en/rest/overview/permissions-required-for-github-apps)
-   [List of OAuth scopes](https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/scopes-for-oauth-apps#available-scopes)
-   [OAuth-related docs](https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/authorizing-oauth-apps)

Need help getting started? Get help in the [community](#).

## API gotchas

-   When setting up a GitHub App:
    - The App ID is made of numbers (e.g. 401953)
    - The App Public Link is the URL to your Github App public page (e.g. https://github.com/apps/terapi-github-app)
    - The App Private Key needs to be generated in your GitHub App settings and starts with `-----BEGIN RSA PRIVATE KEY-----` (not to be confused with the Client Secrets)
    - The Setup URL (displayed on your integration page) needs to be added to your GitHub App configuration (not to be confused with the Callback URL that can stay empty)
-   When setting up a GitHub App OAuth:
    - The App ID is made of numbers (e.g. 401953)
    - The App Public Link is the URL to your Github App public page (e.g. https://github.com/apps/terapi-github-app)
    - The App Private Key needs to be generated in your GitHub App settings and starts with `-----BEGIN RSA PRIVATE KEY-----` (not to be confused with the Client Secrets)
    - The "Callback URL" needs to be filled in with the callback URL which unless customized will be https://api.terapi.dev/oauth/callback and the checkbox "Request user authorization (OAuth) during installation" should be checked
    - The checkbox "Redirect on update" under "Post installation" should NOT be checked and the "Setup URL (optional)" should not be accessible
-   There are certain API methods that only work with an OAuth App that will not work with an App. Please check the Github documentation and look for a "Works with Github Apps" header under the endpoint.
-   The `github-app-oauth` is a combination of a Github App and OAuth and should be used when a Github App would need approval to be installed into an organization.
-   Terapi supports initiating a connection with a GitHub App using the frontend SDK, but not directly from the [GitHub Marketplace](https://github.com/marketplace). Therefore, you should encourage users to install your GitHub App from your product, rather than from the GitHub Marketplace directly. This is a limitation we plan to fix in the future.

Add Getting Started links and Gotchas by [editing this page](#).

