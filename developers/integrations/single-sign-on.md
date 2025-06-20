---
description: >-
  Single sign-on (SSO) is an authentication scheme that allows a user to log in
  with a single ID to any of several related, yet independent, software systems.
---

# Single Sign-On

Refer to this Wikipedia article for background information about [Single Sign-On](https://en.wikipedia.org/wiki/Single_sign-on).

Shift iQ supports two industry-standard mechanisms for SSO:

1. Learning Tools Interoperability (LTI)
2. Security Assertion Markup Language (SAML)

We do not implement or support custom SSO mechanisms due to the potential security and privacy risks associated with them.

### Learning Tools Interoperability (LTI) <a href="#learning-tools-interoperability-lti" id="learning-tools-interoperability-lti"></a>

LTI is the simplest approach to SSO with the Shift iQ platform.

While LTI is not primarily designed as a SSO mechanism, some of the data it passes in a launch request is about the user. LTI works on the basis of a trust relationship between systems, which is established by means of a key and a secret. This makes it much simpler than providing access to a common identity server.

In LTI, a user is authenticated by a primary system and then can be passed to another system (internal or external) by way of a signed launch message. The system that receives this message verifies its authenticity by inspecting its digital signature, and then implicitly trusting the data it carries; thereby eliminating the need to authenticate the user a second time or reconfirm the user’s identity.

This approach makes LTI a low-cost option for implementing SSO between systems.

Refer to this article for details: [LTI as a SSO Mechanism](https://www.imsglobal.org/learning-tools-interoperability-sso-mechanism)

An LTI launch message submitted for SSO access to Shift iQ looks something like this:

<figure><img src="../.gitbook/assets/lti-launch.png" alt=""><figcaption></figcaption></figure>

The LTI Launch message is signed with a secure digital signature, using [HMAC-SHA1](https://learn.microsoft.com/en-us/dotnet/api/system.security.cryptography.hmacsha1?view=net-7.0) or [HMAC-SHA256](https://learn.microsoft.com/en-us/dotnet/api/system.security.cryptography.hmacsha256?view=net-7.0), with a secret key that is shared between the two systems.

When Shift iQ receives this message from a user’s web browser, it validates the signature on the message to confirm it is a legitimate interoperability request from an authorized external system.

If request is valid, then Shift iQ authenticates the learner and navigates to the requested course in the Shift iQ Learning Portal.

### Security Assertion Markup Language (SAML) <a href="#security-assertion-markup-language-saml" id="security-assertion-markup-language-saml"></a>

SAML is a more powerful and more sophisticated approach to SSO with the Shift iQ platform. It is more secure than LTI, therefore it is the mechanism we prefer and recommend to customers.

Security Assertion Markup Language (SAML, pronounced SAM-el) is an open standard for exchanging authentication and authorization data between parties, in particular, between an identity provider and a service provider. SAML is an XML-based markup language for security assertions (statements that service providers use to make access-control decisions).

An important use case that SAML addresses is web-browser single sign-on. Single sign-on is relatively easy to accomplish within a security domain (using cookies, for example) but extending SSO across security domains is more difficult and resulted in the proliferation of non-interoperable proprietary technologies. The SAML Web Browser SSO profile was specified and standardized to promote interoperability.

SSO interoperability with Shift iQ is supported for the following platforms:

* [Azure Directory Federation Services](https://learn.microsoft.com/en-us/windows-server/identity/ad-fs/deployment/how-to-connect-fed-azure-adfs)
* [Azure Active Directory](https://www.microsoft.com/en-ca/security/business/identity-access/microsoft-entra-id)
* [Centrify](https://delinea.com/)
* [Facebook](https://www.facebook.com/)
* [Google](https://www.google.com/)
* [Office 365](https://www.office.com/)
* [Okta](https://www.okta.com/)
* [OneLogin](https://www.onelogin.com/)
* [PingOne](https://www.pingidentity.com/)
* [Salesforce](https://www.salesforce.com/)
* [Shibboleth](https://www.shibboleth.net/)
