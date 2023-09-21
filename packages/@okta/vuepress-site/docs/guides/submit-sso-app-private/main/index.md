---
title: Add a private SSO integration
meta:
  - name: description
    content: Use this guide to learn how to add a private SSO integration to your Okta org.
layout: Guides
---

Use this guide to add a private, custom Single Sign-On (SSO) OIDC or SAML 2.0 integration to your Okta org. Private integrations are only used by the users of the org for which they're installed on. This guide also shows you how to test the private integration in your org.

---

**Learning outcomes**

* Learn how to add a private SSO integration to your Okta org
* Learn how to test your SSO integration in your Okta org

**What you need**

* A functional SSO integration created in accordance with the [Build a Single Sign-On integration](/docs/guides/build-sso-integration/) guide
* An Okta org (such as an [Okta Developer Edition org](https://developer.okta.com/signup))

---

## Overview

To integrate your custom app for SSO with Okta, you need to first develop your app SSO integration. Then, you need to register your app with an Okta org before you can test it. The registration process is creating an app integration instance in an Okta org that provides you with the SSO credentials or metadata for your app authentication requests. This integration is considered private because it is only available in the org from where the app integration instance was created.

> **Note:** An app integration is considered public if it's available in the Okta Integration Network (OIN) catalog for all Okta customers.

This guide assumes that you've developed your SSO integration and want to add it to your Okta org for testing. The instructions in this guide are generic for two SSO standards:

* **OpenID Connect (OIDC)** (preferred)
* **Security Assertion Markup Language (SAML)**

For language, platform-specific, as well as deployment-specific instructions, see [Redirect authentication](/docs/guides/redirect-authentication/) and [Embedded authentication](/docs/guides/embedded-authentication/) guides.

> **Note:** Private integrations aren't restricted to the [OIN limitations](/docs/guides/submit-app-prereq/main/#oin-limitations). You can implement the Okta features that are available on your specific Okta org.

## Create your private integration in Okta

After you've built your SSO integration, you can use the Application Integration Wizard (AIW) in the Admin Console to create your app integration instance. This instance provides you with client credentials or metadata for you to test your SSO flows.

> **Note:** For best practices, create two or three additional administrative users in Okta to manage the integration. This ensures that your team can access the application for updates over time.

1. Sign in to your [developer-edition Okta org](/login/) as a user with administrative privileges.
1. Go to **Applications** > **Applications** in the Admin Console.
1. Click **Create App Integration**.

<StackSnippet snippet="create" />

<br>

> **Note:** Creating your app integration instance doesn't automatically make it available in the [OIN](https://www.okta.com/integrations/). See [Publish an OIN integration](/docs/guides/submit-app-overview/) for an overview of the submission process.

## Specify your integration settings

This portion of the guide takes you through the steps for configuring your specific SSO integration using the Okta Admin Console.

After you create your integration instance in the [Create your integration in Okta](#create-your-integration-in-okta) section, the main settings page appears for your new integration in the Admin Console. Specify **General Settings** and **Sign On** options, and assign the integration to users in your org. Click **Edit** if you need to change any of the options, and **Save** when you've made your changes.

<StackSnippet snippet="settings" />

## Test your integration

This portion of the guide takes you through the steps required to test your integration.

### Assign users

First, you must assign your integration to one or more test users in your org:

1. Click the **Assignments** tab.
1. Click **Assign** and then select either **Assign to People** or **Assign to Groups**.
1. Enter the appropriate people or groups that you want to have Single Sign-On into your application, and then click **Assign** for each.
1. Verify the user-specific attributes for any people that you add, and then select **Save and Go Back**.
1. Click **Done**.

### Test Single Sign-On

1. Sign out of your Okta org. Click **Sign out** in the upper-right corner of the Admin Console.
1. Sign in to the Okta End-User Dashboard as the regular user that was assigned the integration.

   > **Note:** If you sign in as a non-admin user to your Okta org from a browser, the End-User Dashboard appears. To access the End-User Dashboard from a mobile device, see [Okta End-User-Dashboard](https://help.okta.com/okta_help.htm?type=eu&id=ext_user_dashboard_overview).

1. Click the Okta tile for the integration and confirm that the user is signed in to your app.

<StackSnippet snippet="test" />

## Next steps

After you complete testing your app integration, you can communicate to your Okta org users about the custom app SSO capability.

## See also

* [Redirect authentication](/docs/guides/redirect-authentication/): for language and platform-specific redirect authentication guides
* [Embedded authentication](/docs/guides/embedded-authentication/): for language, platform-specific, and embedded-authentication use case guides

